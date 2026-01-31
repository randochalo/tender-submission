# TOOLS.md - PDF OCR Configuration

## Manual Setup (Used for TSH-2604 and TSH-2605)

Since system installation wasn't available, we used extracted .deb packages:

### Downloaded Packages

Location: `/tmp/` (working directory)

```bash
# Core OCR tools
tesseract-ocr_5.3.4-1build5_amd64.deb
tesseract-ocr-eng_1%3a4.1.0-2_all.deb

# Libraries
libtesseract5_5.3.4-1build5_amd64.deb
liblept5_1.82.0-3build4_amd64.deb
libarchive13t64_3.7.2-2ubuntu0.5_amd64.deb
libgif7_5.2.2-1ubuntu1_amd64.deb
libwebp7_1.3.2-0.4build3_amd64.deb
libwebpmux3_1.3.2-0.4build3_amd64.deb
libopenjp2-7_2.5.0-2ubuntu0.4_amd64.deb
libcurl4t64_8.5.0-2ubuntu10.6_amd64.deb
libtiff6_4.5.1+git230720-4ubuntu2.4_amd64.deb
libnspr4_2%3a4.35-1.1build1_amd64.deb

# PDF tools
poppler-utils_22.02.0-2_amd64.deb
libpoppler118_22.02.0-2_amd64.deb
libpoppler-glib8_22.02.0-2_amd64.deb
```

### Extraction Process

```bash
# Create directories
mkdir -p /tmp/tesseract /tmp/poppler-full

# Extract all packages
for deb in *.deb; do
    dpkg -x "$deb" ./tesseract 2>/dev/null || dpkg -x "$deb" ./poppler-full 2>/dev/null
done

# Fix library symlinks
cd /tmp/tesseract/usr/lib/x86_64-linux-gnu/
ln -sf liblept.so.5 liblept.so
ln -sf liblept.so.5 libleptonica.so
ln -sf libtiff.so.6 libtiff.so.5
```

### Environment Variables

```bash
export LD_LIBRARY_PATH=/tmp/poppler-full/usr/lib/x86_64-linux-gnu:/tmp/tesseract/usr/lib/x86_64-linux-gnu
export TESSDATA_PREFIX=/tmp/tesseract/usr/share/tesseract-ocr/5/tessdata
```

### Verification

```bash
# Test tesseract
LD_LIBRARY_PATH=/tmp/poppler-full/usr/lib/x86_64-linux-gnu:/tmp/tesseract/usr/lib/x86_64-linux-gnu \
    /tmp/tesseract/usr/bin/tesseract --version

# Test pdftoppm
LD_LIBRARY_PATH=/tmp/poppler-full/usr/lib/x86_64-linux-gnu \
    /tmp/poppler-full/usr/bin/pdftoppm --version
```

## Conversion Command (TSH-2604 & TSH-2605)

```bash
# Step 1: PDF to images
LD_LIBRARY_PATH=/tmp/poppler-full/usr/lib/x86_64-linux-gnu \
    /tmp/poppler-full/usr/bin/pdftoppm "Tender Document.pdf" output -png -r 150

# Step 2: OCR each page to markdown
for i in $(seq -w 1 78); do
    echo "## Page $i" >> output.md
    TESSDATA_PREFIX=/tmp/tesseract/usr/share/tesseract-ocr/5/tessdata \
        LD_LIBRARY_PATH=/tmp/poppler-full/usr/lib/x86_64-linux-gnu:/tmp/tesseract/usr/lib/x86_64-linux-gnu \
        /tmp/tesseract/usr/bin/tesseract "output-$i.png" stdout -l eng >> output.md 2>/dev/null
    echo "---" >> output.md
done
```

## Results

| Tender | Pages | Output Lines | Time |
|--------|-------|--------------|------|
| TSH-2604 | 78 | 3,899 | ~8 minutes |
| TSH-2605 | 60 | 2,691 | ~6 minutes |

## Cleanup

```bash
# Remove temporary files
rm -rf /tmp/pdf_images
rm -f /tmp/tsh2604.md /tmp/tsh2605.md

# Keep tools for future use, or remove:
rm -rf /tmp/tesseract /tmp/poppler-full /tmp/*.deb
```

## Notes

- 150 DPI provides good OCR accuracy with reasonable processing time
- Higher DPI (300) improves accuracy but doubles processing time
- PNG format recommended over JPEG for better OCR results
- Total processing time: ~1 page per 6-8 seconds
