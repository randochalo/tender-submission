---
name: pdf-ocr
description: Convert scanned PDF documents to text/markdown using Tesseract OCR and poppler-utils
homepage: https://github.com/tesseract-ocr/tesseract
metadata:
  clawd:
    emoji: "📄"
    requires:
      bins:
        - tesseract
        - pdftoppm
    install:
      - id: apt
        kind: apt
        packages:
          - tesseract-ocr
          - tesseract-ocr-eng
          - poppler-utils
        label: Install Tesseract OCR and poppler-utils
---

# PDF OCR Skill

Convert scanned/image-based PDF documents to searchable text or markdown using Tesseract OCR.

## Overview

This skill provides tools to extract text from scanned PDF documents that cannot be processed by standard text extraction tools. It uses:

- **pdftoppm** (from poppler-utils) - Convert PDF pages to images
- **Tesseract OCR** - Extract text from images

## When to Use This Skill

| Scenario | Solution |
|----------|----------|
| PDF contains selectable text | Use `pdftotext` directly (no OCR needed) |
| PDF is scanned/images only | Use this OCR skill |
| PDF has mixed text and images | Try `pdftotext` first, use OCR if needed |

### Check if PDF is scanned:

```bash
pdfinfo "document.pdf"
# Look for: Creator/Producer showing scanner model (e.g., "Canon iR-ADV")
# Or: pdftotext produces empty output
```

## Prerequisites

### System Installation (Recommended)

```bash
sudo apt-get update
sudo apt-get install -y tesseract-ocr tesseract-ocr-eng poppler-utils
```

### Manual Setup (No sudo access)

If you cannot install system packages, download and extract:

```bash
# Create working directory
mkdir -p /tmp/ocr-tools
cd /tmp/ocr-tools

# Download packages
apt download tesseract-ocr tesseract-ocr-eng poppler-utils libtesseract5 liblept5 libarchive13t64

# Extract packages
for deb in *.deb; do dpkg -x "$deb" ./; done

# Set library path
export LD_LIBRARY_PATH=/tmp/ocr-tools/usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH
export PATH=/tmp/ocr-tools/usr/bin:$PATH
export TESSDATA_PREFIX=/tmp/ocr-tools/usr/share/tesseract-ocr/5/tessdata
```

## Quick Start

### Basic OCR Conversion

```bash
# 1. Convert PDF to images (150 DPI is good balance of quality/speed)
pdftoppm "input.pdf" output -png -r 150

# 2. OCR each image to text
for img in output*.png; do
    tesseract "$img" stdout -l eng >> output.txt
done
```

### Convert to Markdown with Page Breaks

```bash
#!/bin/bash
PDF="input.pdf"
OUTPUT="output.md"
DPI=150

# Initialize markdown file
echo "# OCR Output: $(basename "$PDF")" > "$OUTPUT"
echo "" >> "$OUTPUT"
echo "**Source:** $PDF" >> "$OUTPUT"
echo "" >> "$OUTPUT"
echo "---" >> "$OUTPUT"
echo "" >> "$OUTPUT"

# Convert PDF to images
mkdir -p /tmp/pdf_pages
pdftoppm "$PDF" /tmp/pdf_pages/page -png -r $DPI

# OCR each page
page=1
for img in /tmp/pdf_pages/page*.png; do
    echo "## Page $page" >> "$OUTPUT"
    echo "" >> "$OUTPUT"
    tesseract "$img" stdout -l eng >> "$OUTPUT" 2>/dev/null
    echo "" >> "$OUTPUT"
    echo "---" >> "$OUTPUT"
    echo "" >> "$OUTPUT"
    ((page++))
done

# Cleanup
rm -rf /tmp/pdf_pages

echo "Conversion complete: $OUTPUT"
```

## Detailed Usage

### Step 1: PDF to Images

```bash
# Basic conversion (all pages)
pdftoppm "document.pdf" output -png

# Specific DPI (higher = better quality but slower)
pdftoppm "document.pdf" output -png -r 300    # High quality
pdftoppm "document.pdf" output -png -r 150    # Good balance
pdftoppm "document.pdf" output -png -r 72     # Fast, lower quality

# Specific page range
pdftoppm "document.pdf" output -png -f 1 -l 5  # Pages 1-5 only

# JPEG format (smaller files)
pdftoppm "document.pdf" output -jpeg -r 150
```

### Step 2: OCR Images

```bash
# Single image
tesseract image.png output -l eng

# Output to stdout
tesseract image.png stdout -l eng

# Multiple languages
tesseract image.png stdout -l eng+msa  # English + Malay

# Different output formats
tesseract image.png output -l eng txt     # Plain text (default)
tesseract image.png output -l eng pdf     # Searchable PDF
tesseract image.png output -l eng tsv     # TSV with coordinates
```

### Batch Processing

```bash
#!/bin/bash
# Process multiple PDFs

for pdf in *.pdf; do
    echo "Processing: $pdf"
    
    # Create output filename
    base=$(basename "$pdf" .pdf)
    output="${base}.md"
    
    # Convert to images
    mkdir -p "/tmp/ocr_${base}"
    pdftoppm "$pdf" "/tmp/ocr_${base}/page" -png -r 150
    
    # OCR and combine
    echo "# ${base}" > "$output"
    for img in "/tmp/ocr_${base}"/*.png; do
        tesseract "$img" stdout -l eng >> "$output" 2>/dev/null
        echo "" >> "$output"
    done
    
    # Cleanup
    rm -rf "/tmp/ocr_${base}"
    
    echo "Complete: $output"
done
```

## Configuration

### Language Support

```bash
# List installed languages
tesseract --list-langs

# Install additional languages
sudo apt-get install tesseract-ocr-msa  # Malay
sudo apt-get install tesseract-ocr-chi-sim  # Chinese Simplified
sudo apt-get install tesseract-ocr-chi-tra  # Chinese Traditional

# Use multiple languages
tesseract image.png stdout -l eng+msa
```

### Environment Variables

```bash
# Set tessdata directory (if not in default location)
export TESSDATA_PREFIX=/usr/share/tesseract-ocr/5/tessdata

# Or for custom installation
export TESSDATA_PREFIX=/path/to/tessdata
```

## Integration Examples

### With Git Workflow

```bash
#!/bin/bash
# ocr-pdf.sh - OCR PDFs in git repo and commit

pdf_file="$1"
if [ -z "$pdf_file" ]; then
    echo "Usage: ocr-pdf.sh <pdf-file>"
    exit 1
fi

# Generate markdown output
output="${pdf_file%.pdf}.md"

# Run OCR (using this skill's methodology)
echo "# OCR: $(basename "$pdf_file")" > "$output"
pdftoppm "$pdf_file" /tmp/ocr_temp -png -r 150
for img in /tmp/ocr_temp*.png; do
    tesseract "$img" stdout -l eng >> "$output" 2>/dev/null
    echo "" >> "$output"
done
rm -f /tmp/ocr_temp*.png

# Git operations
git add "$output"
git commit -m "Add OCR text for $pdf_file"
git push

echo "OCR complete: $output"
```

### With Tender Processing

```bash
#!/bin/bash
# process-tender.sh

TENDER_DIR="$1"
TENDER_ID=$(basename "$TENDER_DIR")

echo "Processing tender: $TENDER_ID"

# Find PDF in documents folder
pdf_file=$(find "$TENDER_DIR/documents" -name "*.pdf" | head -1)

if [ -z "$pdf_file" ]; then
    echo "No PDF found in $TENDER_DIR/documents"
    exit 1
fi

# OCR to markdown
output="$TENDER_DIR/Tender-Document.md"

echo "# $TENDER_ID: Tender Document" > "$output"
echo "" >> "$output"
echo "**Source:** $(basename "$pdf_file")" >> "$output"
echo "" >> "$output"
echo "**Processed:** $(date)" >> "$output"
echo "" >> "$output"
echo "---" >> "$output"
echo "" >> "$output"

# Convert and OCR
pdftoppm "$pdf_file" /tmp/tender_ocr -png -r 150
page=1
for img in /tmp/tender_ocr*.png; do
    echo "## Page $page" >> "$output"
    echo "" >> "$output"
    tesseract "$img" stdout -l eng >> "$output" 2>/dev/null
    echo "" >> "$output"
    echo "---" >> "$output"
    echo "" >> "$output"
    ((page++))
done
rm -f /tmp/tender_ocr*.png

echo "Tender document processed: $output"
```

## Troubleshooting

### "Failed loading language 'eng'"

```bash
# Install English language pack
sudo apt-get install tesseract-ocr-eng

# Or set correct tessdata path
export TESSDATA_PREFIX=/usr/share/tesseract-ocr/5/tessdata
```

### OCR accuracy is poor

```bash
# Increase DPI for better quality
pdftoppm "document.pdf" output -png -r 300  # Instead of 150

# Or preprocess images
# Convert to grayscale, increase contrast, etc.
```

### pdftoppm is slow on large PDFs

```bash
# Process in batches
pdftoppm "document.pdf" output -png -r 150 -f 1 -l 10   # Pages 1-10
pdftoppm "document.pdf" output -png -r 150 -f 11 -l 20  # Pages 11-20
# etc.
```

### Library errors (libtesseract.so.5 not found)

```bash
# Set library path
export LD_LIBRARY_PATH=/usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH

# Or for custom installation
export LD_LIBRARY_PATH=/path/to/libs:$LD_LIBRARY_PATH
```

## Performance Tips

| Factor | Recommendation |
|--------|----------------|
| **DPI** | 150-200 for good balance; 300 for best quality |
| **Format** | PNG for best quality; JPEG for smaller files |
| **Batch size** | Process 10-20 pages at a time for large PDFs |
| **Language** | Specify only needed languages (eng vs eng+msa) |

## References

- Tesseract OCR: https://github.com/tesseract-ocr/tesseract
- Poppler utils: https://poppler.freedesktop.org/
- Language data: https://github.com/tesseract-ocr/tessdata

## Example Output

Sample markdown output structure:

```markdown
# TSH-2604: Tender Document

**Source:** Tender Document.pdf
**Pages:** 78

---

## Page 1

MODA
MULTIMODAL FREIGHT SDN. BHD.
174274-D

TENDER NO : MMFSBITD 01/2026

TENDER FOR THE SUPPLY AND DEVELOP NEW IT SYSTEM
...

---

## Page 2

[OCR text from page 2]

---

[Continues for all pages...]
```

---
*Skill created: 2026-01-31*
