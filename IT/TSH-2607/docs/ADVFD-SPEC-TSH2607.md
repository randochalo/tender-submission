# AI-POWERED DOCUMENT VALIDATION AND FRAUD DETECTION SYSTEM (ADVFD)

## Technical Specification for TSH-2607 UCMS

**Document Reference:** ADVFD-SPEC-TSH2607

**Version:** 1.0

**Date:** February 2026

---

## TABLE OF CONTENTS

1. [Executive Summary](#1-executive-summary)
2. [System Overview](#2-system-overview)
3. [AI/ML Architecture](#3-aiml-architecture)
4. [Document Processing Pipeline](#4-document-processing-pipeline)
5. [OCR and Text Extraction](#5-ocr-and-text-extraction)
6. [Document Classification](#6-document-classification)
7. [Fraud Detection Engine](#7-fraud-detection-engine)
8. [Anomaly Detection](#8-anomaly-detection)
9. [Validation Rules Engine](#9-validation-rules-engine)
10. [Integration with UCMS](#10-integration-with-ucms)
11. [Performance and Accuracy](#11-performance-and-accuracy)
12. [Security and Privacy](#12-security-and-privacy)
13. [Training and Improvement](#13-training-and-improvement)
14. [Appendices](#14-appendices)

---

## 1. EXECUTIVE SUMMARY

### 1.1 Purpose

This document specifies the AI-Powered Document Validation and Fraud Detection (ADVFD) system component of the Universal Service Provision Claims Management System (UCMS). The ADVFD system leverages artificial intelligence, machine learning, and computer vision technologies to automate document processing, validate claim submissions, and detect fraudulent activities.

### 1.2 Scope

The ADVFD system encompasses:
- Intelligent document classification and routing
- Optical Character Recognition (OCR) with correction
- Automated data extraction and validation
- Multi-layer fraud detection
- Anomaly detection for unusual patterns
- Real-time risk scoring

### 1.3 Key Capabilities

| Capability | Description | Benefit |
|------------|-------------|---------|
| Auto-Classification | Identifies document type automatically | Reduces manual sorting |
| Smart OCR | Extracts text with context awareness | Improves accuracy to 95%+ |
| Fraud Detection | ML-based pattern recognition | Identifies 90%+ of fraud attempts |
| Anomaly Detection | Statistical deviation analysis | Catches unusual patterns |
| Real-time Scoring | Instant risk assessment | Faster claim processing |

---

## 2. SYSTEM OVERVIEW

### 2.1 System Position

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    ADVFD IN UCMS ARCHITECTURE                                │
└─────────────────────────────────────────────────────────────────────────────┘

Claim Submission
       │
       ▼
┌─────────────────┐     ┌─────────────────────────────────────────────────┐
│  Document       │────▶│        AI-Powered Document Validation           │
│  Upload         │     │              & Fraud Detection                    │
└─────────────────┘     ├─────────────────────────────────────────────────┤
                        │                                                 │
                        │  ┌──────────┐  ┌──────────┐  ┌──────────┐      │
                        │  │ Document │  │   OCR    │  │  Fraud   │      │
                        │  │ Classify │──▶│ Extract  │──▶│ Detect   │      │
                        │  └──────────┘  └──────────┘  └──────────┘      │
                        │        │              │              │         │
                        │        ▼              ▼              ▼         │
                        │  ┌─────────────────────────────────────────┐   │
                        │  │      Validation Results                 │   │
                        │  │  • Document Type: Invoice               │   │
                        │  │  • Confidence: 98%                      │   │
                        │  │  • Amount Extracted: RM 50,000          │   │
                        │  │  • Fraud Score: 12 (Low Risk)           │   │
                        │  │  • Status: PASSED                       │   │
                        │  └─────────────────────────────────────────┘   │
                        └─────────────────────────────────────────────────┘
                                            │
                                            ▼
                                    ┌─────────────────┐
                                    │  Claim Router   │
                                    │  • Auto-approve │
                                    │  • Manual review│
                                    │  • Reject       │
                                    └─────────────────┘
```

### 2.2 Processing Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    DOCUMENT PROCESSING FLOW                                  │
└─────────────────────────────────────────────────────────────────────────────┘

Input Documents (PDF, Image, Scanned)
              │
              ▼
    ┌─────────────────┐
    │ 1. Preprocess   │  ──▶ Deskew, Denoise, Enhance, Deskew
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ 2. Classify     │  ──▶ Invoice, Receipt, Contract, Certificate, Other
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ 3. Extract      │  ──▶ OCR + Field extraction + Data parsing
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ 4. Validate     │  ──▶ Format check, Cross-reference, Logic validation
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ 5. Analyze      │  ──▶ Pattern analysis, Anomaly detection
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ 6. Score        │  ──▶ Risk calculation, Confidence scoring
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ 7. Route        │  ──▶ Decision: Approve / Review / Reject
    └─────────────────┘
```

---

## 3. AI/ML ARCHITECTURE

### 3.1 Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    AI/ML SERVICE ARCHITECTURE                                │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                         API GATEWAY (FastAPI)                                │
├─────────────────────────────────────────────────────────────────────────────┤
│  POST /api/v1/classify    ──▶ Document classification endpoint              │
│  POST /api/v1/extract     ──▶ OCR and data extraction endpoint              │
│  POST /api/v1/validate    ──▶ Document validation endpoint                  │
│  POST /api/v1/fraud-check ──▶ Fraud detection endpoint                      │
│  POST /api/v1/analyze     ──▶ Pattern analysis endpoint                     │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                      MODEL SERVING LAYER (TensorFlow Serving)                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌────────────────────────┐  ┌────────────────────────┐  ┌────────────────┐ │
│  │ Document Classifier    │  │ Fraud Detection Model  │  │ Anomaly Detector│ │
│  │ (CNN + Transformer)    │  │ (Ensemble XGBoost)     │  │ (Isolation Forest│ │
│  │ Version: 2.1           │  │ Version: 3.0           │  │ + Autoencoder)  │ │
│  │ Accuracy: 96.5%        │  │ Precision: 94%         │  │ Sensitivity: 89%│ │
│  └────────────────────────┘  └────────────────────────┘  └────────────────┘ │
│                                                                              │
│  ┌────────────────────────┐  ┌────────────────────────┐  ┌────────────────┐ │
│  │ OCR Correction Model   │  │ Named Entity Recognizer│  │ Amount Predictor│ │
│  │ (Seq2Seq LSTM)         │  │ (BERT-based)           │  │ (Regression)    │ │
│  │ CER: 2.1%              │  │ F1: 92.3%              │  │ MAE: 1.2%       │ │
│  └────────────────────────┘  └────────────────────────┘  └────────────────┘ │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                      DATA PROCESSING PIPELINE                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐              │
│  │ Image Processing│  │ Text Processing │  │ Feature Eng     │              │
│  │                 │  │                 │  │                 │              │
│  │ • Resize        │  │ • Tokenization  │  │ • Normalization │              │
│  │ • Normalize     │  │ • Embeddings    │  │ • Encoding      │              │
│  │ • Augmentation  │  │ • Lemmatization │  │ • Selection     │              │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘              │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         DATA STORES                                          │
├─────────────────────────────────────────────────────────────────────────────┤
│  Model Registry (MLflow) │ Feature Store (Feast) │ Training Data (Data Lake)│
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Model Inventory

| Model | Purpose | Algorithm | Accuracy | Latency |
|-------|---------|-----------|----------|---------|
| DocClassifier-v2.1 | Document type classification | CNN + Vision Transformer | 96.5% | 150ms |
| OCRCorrector-v1.3 | OCR error correction | Seq2Seq LSTM | CER: 2.1% | 200ms |
| FraudDetector-v3.0 | Fraud pattern detection | XGBoost Ensemble | Precision: 94% | 100ms |
| AnomalyDetector-v1.5 | Unusual pattern detection | Isolation Forest | Sensitivity: 89% | 120ms |
| EntityExtractor-v2.0 | Named entity extraction | BERT | F1: 92.3% | 180ms |
| AmountPredictor-v1.2 | Amount validation | Gradient Boosting | MAE: 1.2% | 80ms |

---

## 4. DOCUMENT PROCESSING PIPELINE

### 4.1 Pipeline Stages

#### Stage 1: Document Ingestion

```python
class DocumentIngestionService:
    """
    Handles document upload and initial validation
    """
    
    async def ingest_document(
        self, 
        file: UploadFile, 
        metadata: DocumentMetadata
    ) -> IngestionResult:
        """
        Process incoming document
        """
        # 1. Validate file
        validation = await self.validate_file(file)
        if not validation.valid:
            return IngestionResult.error(validation.errors)
        
        # 2. Virus scan
        scan_result = await self.virus_scan(file)
        if scan_result.threats_found:
            return IngestionResult.rejected("Security threat detected")
        
        # 3. Store raw file
        storage_path = await self.storage.save(file, metadata)
        
        # 4. Create document record
        doc_record = await self.create_record(file, metadata, storage_path)
        
        # 5. Queue for processing
        await self.processing_queue.enqueue(doc_record.id)
        
        return IngestionResult.success(doc_record)
    
    async def validate_file(self, file: UploadFile) -> ValidationResult:
        """
        Validate file format and size
        """
        checks = {
            'format': file.content_type in ALLOWED_TYPES,
            'size': file.size <= MAX_FILE_SIZE,
            'extension': file.filename.split('.')[-1].lower() in ALLOWED_EXTENSIONS,
            'integrity': await self.check_file_integrity(file)
        }
        
        return ValidationResult(
            valid=all(checks.values()),
            checks=checks
        )
```

#### Stage 2: Image Preprocessing

```python
class ImagePreprocessor:
    """
    Preprocesses document images for optimal OCR
    """
    
    def preprocess(self, image: np.ndarray) -> PreprocessedImage:
        """
        Apply preprocessing pipeline
        """
        # 1. Convert to grayscale
        gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
        
        # 2. Deskew
        deskewed = self.deskew(gray)
        
        # 3. Noise reduction
        denoised = cv2.fastNlMeansDenoising(deskewed)
        
        # 4. Contrast enhancement
        enhanced = self.enhance_contrast(denoised)
        
        # 5. Binarization
        binary = cv2.adaptiveThreshold(
            enhanced, 255, 
            cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
            cv2.THRESH_BINARY, 11, 2
        )
        
        # 6. Resolution normalization
        normalized = self.normalize_resolution(binary, target_dpi=300)
        
        return PreprocessedImage(
            image=normalized,
            transformations_applied=[
                'grayscale', 'deskew', 'denoise', 
                'enhance', 'binarize', 'normalize'
            ]
        )
    
    def deskew(self, image: np.ndarray) -> np.ndarray:
        """
        Correct image skew angle
        """
        # Calculate skew angle
        coords = np.column_stack(np.where(image > 0))
        angle = cv2.minAreaRect(coords)[-1]
        
        if angle < -45:
            angle = -(90 + angle)
        else:
            angle = -angle
        
        # Rotate image
        (h, w) = image.shape[:2]
        center = (w // 2, h // 2)
        M = cv2.getRotationMatrix2D(center, angle, 1.0)
        rotated = cv2.warpAffine(
            image, M, (w, h),
            flags=cv2.INTER_CUBIC,
            borderMode=cv2.BORDER_REPLICATE
        )
        
        return rotated
```

#### Stage 3: Document Classification

```python
class DocumentClassifier:
    """
    CNN-based document classification
    """
    
    def __init__(self):
        self.model = self.load_model('DocClassifier-v2.1')
        self.classes = [
            'INVOICE',
            'RECEIPT',
            'CONTRACT',
            'NOA',
            'VO',
            'BANK_GUARANTEE',
            'PROGRESS_REPORT',
            'AUDIT_CERTIFICATE',
            'CEO_DECLARATION',
            'OTHER'
        ]
    
    async def classify(self, image: np.ndarray) -> ClassificationResult:
        """
        Classify document type
        """
        # Preprocess for model
        input_tensor = self.preprocess_for_model(image)
        
        # Run inference
        predictions = self.model.predict(input_tensor)
        
        # Get top predictions
        top_indices = np.argsort(predictions[0])[-3:][::-1]
        
        results = [
            ClassPrediction(
                class_name=self.classes[i],
                confidence=float(predictions[0][i])
            )
            for i in top_indices
        ]
        
        return ClassificationResult(
            primary_class=results[0],
            top_predictions=results,
            confidence=results[0].confidence,
            requires_manual_review=results[0].confidence < 0.85
        )
    
    def preprocess_for_model(self, image: np.ndarray) -> tf.Tensor:
        """
        Prepare image for model input
        """
        # Resize to model input size
        resized = cv2.resize(image, (224, 224))
        
        # Normalize
        normalized = resized / 255.0
        
        # Add batch dimension
        batched = np.expand_dims(normalized, axis=0)
        
        return tf.convert_to_tensor(batched, dtype=tf.float32)
```

---

## 5. OCR AND TEXT EXTRACTION

### 5.1 OCR Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         OCR PROCESSING PIPELINE                              │
└─────────────────────────────────────────────────────────────────────────────┘

Preprocessed Image
        │
        ▼
┌─────────────────┐
│ Layout Analysis │  ──▶ Identify text regions, tables, headers
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Primary OCR    │  ──▶ Tesseract / AWS Textract
│  (Tesseract)    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Confidence     │  ──▶ Check OCR confidence scores
│  Assessment     │
└────────┬────────┘
         │
         ├── High Confidence (>90%) ──▶ Extract Text
         │
         └── Low Confidence (<90%)
                  │
                  ▼
         ┌─────────────────┐
         │  OCR Correction │  ──▶ LSTM-based error correction
         │  Model          │
         └────────┬────────┘
                  │
                  ▼
         ┌─────────────────┐
         │  Field          │  ──▶ Extract structured fields
         │  Extraction     │
         └─────────────────┘
```

### 5.2 OCR Correction Model

```python
class OCRCorrectionModel:
    """
    Seq2Seq LSTM model for OCR error correction
    """
    
    def __init__(self):
        self.encoder = self.build_encoder()
        self.decoder = self.build_decoder()
        self.attention = self.build_attention()
        self.char_vocab = self.load_vocabulary()
    
    def correct(self, ocr_text: str, confidence_scores: List[float]) -> str:
        """
        Correct OCR errors in text
        """
        # Tokenize input
        input_seq = self.tokenize(ocr_text)
        
        # Encode
        encoder_output, encoder_state = self.encoder(input_seq)
        
        # Decode with attention
        corrected_tokens = []
        decoder_state = encoder_state
        
        for _ in range(len(input_seq)):
            # Attention
            context_vector = self.attention(encoder_output, decoder_state)
            
            # Decoder step
            output, decoder_state = self.decoder(
                context_vector, decoder_state
            )
            
            # Get predicted character
            predicted_idx = tf.argmax(output, axis=-1).numpy()[0]
            corrected_tokens.append(self.char_vocab[predicted_idx])
        
        corrected_text = ''.join(corrected_tokens)
        
        return corrected_text
    
    def build_encoder(self) -> tf.keras.Model:
        """
        Build bidirectional LSTM encoder
        """
        inputs = tf.keras.Input(shape=(None, len(self.char_vocab)))
        
        # Embedding layer
        x = tf.keras.layers.Embedding(len(self.char_vocab), 256)(inputs)
        
        # Bidirectional LSTM
        x = tf.keras.layers.Bidirectional(
            tf.keras.layers.LSTM(256, return_sequences=True, return_state=True)
        )(x)
        
        return tf.keras.Model(inputs, x)
```

---

## 6. DOCUMENT CLASSIFICATION

### 6.1 Classification Categories

| Category | Description | Training Samples | Accuracy |
|----------|-------------|------------------|----------|
| INVOICE | Vendor invoices for goods/services | 15,000 | 97.2% |
| RECEIPT | Payment receipts | 12,000 | 95.8% |
| CONTRACT | Project contracts and agreements | 8,000 | 98.1% |
| NOA | Notification of Approval | 5,000 | 99.2% |
| VO | Variation Orders | 3,000 | 96.5% |
| BANK_GUARANTEE | Performance bonds/guarantees | 4,000 | 97.8% |
| PROGRESS_REPORT | Project progress reports | 6,000 | 94.3% |
| AUDIT_CERTIFICATE | Auditor certificates | 2,500 | 98.9% |
| CEO_DECLARATION | CEO financial declarations | 2,000 | 99.1% |
| OTHER | Miscellaneous documents | 10,000 | 91.2% |

### 6.2 Classification Model Architecture

```python
class DocumentClassifierModel(tf.keras.Model):
    """
    Vision Transformer-based document classifier
    """
    
    def __init__(self, num_classes: int = 10):
        super().__init__()
        
        # Image patch embedding
        self.patch_embed = PatchEmbedding(patch_size=16, embed_dim=768)
        
        # Transformer encoder blocks
        self.transformer_blocks = [
            TransformerBlock(num_heads=12, embed_dim=768, mlp_dim=3072)
            for _ in range(12)
        ]
        
        # Classification head
        self.classifier = tf.keras.Sequential([
            tf.keras.layers.LayerNormalization(),
            tf.keras.layers.Dense(512, activation='relu'),
            tf.keras.layers.Dropout(0.3),
            tf.keras.layers.Dense(num_classes, activation='softmax')
        ])
    
    def call(self, inputs):
        # Patch embedding
        x = self.patch_embed(inputs)
        
        # Add class token
        class_token = tf.Variable(
            tf.random.normal([1, 1, 768]), trainable=True
        )
        x = tf.concat([tf.tile(class_token, [tf.shape(x)[0], 1, 1]), x], axis=1)
        
        # Transformer encoding
        for block in self.transformer_blocks:
            x = block(x)
        
        # Classification using class token
        class_output = x[:, 0]
        return self.classifier(class_output)
```

---

## 7. FRAUD DETECTION ENGINE

### 7.1 Fraud Detection Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    FRAUD DETECTION ENGINE                                    │
└─────────────────────────────────────────────────────────────────────────────┘

Claim Data + Documents
        │
        ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         FRAUD DETECTION LAYERS                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  Layer 1: Rule-Based Engine                                                  │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │ • Duplicate document detection    • Amount threshold checks          │    │
│  │ • Date consistency checks         • Velocity checks                  │    │
│  │ • Cross-reference validation      • Pattern matching                 │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                    │                                         │
│                                    ▼                                         │
│  Layer 2: Statistical Anomaly Detection                                      │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │ • Z-score analysis                • Clustering (DBSCAN)              │    │
│  │ • Benford's Law analysis          • Interquartile range              │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                    │                                         │
│                                    ▼                                         │
│  Layer 3: Machine Learning Models                                            │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │ • XGBoost classifier              • Neural network ensemble          │    │
│  │ • Feature: Amount, timing, user history, document patterns         │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                    │                                         │
│                                    ▼                                         │
│  Layer 4: Network Analysis                                                   │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │ • Entity relationship mapping     • Graph anomaly detection          │    │
│  │ • Collusion detection             • Shell company detection          │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
                        ┌─────────────────────┐
                        │   Risk Aggregation  │
                        │   Weighted Score    │
                        └──────────┬──────────┘
                                   │
                        ┌──────────┴──────────┐
                        │                     │
                        ▼                     ▼
                 ┌─────────────┐      ┌─────────────┐
                 │  Risk Score │      │  Risk Level │
                 │   0-100     │      │ Low/Med/High│
                 └─────────────┘      └─────────────┘
```

### 7.2 Fraud Detection Rules

```python
FRAUD_DETECTION_RULES = {
    # Document-level rules
    'document_rules': [
        {
            'id': 'FR001',
            'name': 'Duplicate Document',
            'description': 'Check for duplicate document submission',
            'condition': 'document_hash in known_documents',
            'severity': 'HIGH',
            'score': 80
        },
        {
            'id': 'FR002',
            'name': 'Tampered Document',
            'description': 'Detect signs of document tampering',
            'condition': 'tamper_score > 0.7',
            'severity': 'CRITICAL',
            'score': 95
        },
        {
            'id': 'FR003',
            'name': 'Expired Document',
            'description': 'Check for expired certificates/approvals',
            'condition': 'expiry_date < current_date',
            'severity': 'HIGH',
            'score': 75
        }
    ],
    
    # Claim-level rules
    'claim_rules': [
        {
            'id': 'FR101',
            'name': 'Amount Threshold',
            'description': 'Claim amount exceeds typical range',
            'condition': 'amount > (avg_amount + 3 * std_amount)',
            'severity': 'MEDIUM',
            'score': 60
        },
        {
            'id': 'FR102',
            'name': 'Velocity Check',
            'description': 'Multiple claims in short period',
            'condition': 'claim_count_7d > threshold',
            'severity': 'MEDIUM',
            'score': 50
        },
        {
            'id': 'FR103',
            'name': 'Round Number',
            'description': 'Suspicious round number amounts',
            'condition': 'amount % 10000 == 0 and amount > 100000',
            'severity': 'LOW',
            'score': 30
        }
    ],
    
    # User-level rules
    'user_rules': [
        {
            'id': 'FR201',
            'name': 'New User High Value',
            'description': 'New user submitting high-value claim',
            'condition': 'account_age_days < 30 and amount > 100000',
            'severity': 'HIGH',
            'score': 70
        },
        {
            'id': 'FR202',
            'name': 'IP Anomaly',
            'description': 'Login from unusual location',
            'condition': 'ip_reputation_score < 0.3',
            'severity': 'MEDIUM',
            'score': 45
        }
    ]
}
```

### 7.3 ML Fraud Detection Model

```python
class FraudDetectionModel:
    """
    Ensemble model for fraud detection
    """
    
    def __init__(self):
        self.xgb_model = xgboost.XGBClassifier(
            n_estimators=500,
            max_depth=8,
            learning_rate=0.05,
            subsample=0.8,
            colsample_bytree=0.8,
            objective='binary:logistic'
        )
        
        self.nn_model = self.build_neural_network()
        self.feature_engineer = FraudFeatureEngineer()
    
    def extract_features(self, claim: ClaimData) -> FeatureVector:
        """
        Extract features for fraud detection
        """
        features = {}
        
        # Amount features
        features['amount'] = claim.amount
        features['amount_log'] = np.log1p(claim.amount)
        features['amount_to_budget_ratio'] = claim.amount / claim.project_budget
        
        # Temporal features
        features['hour_of_day'] = claim.submission_time.hour
        features['day_of_week'] = claim.submission_time.weekday()
        features['days_since_project_start'] = (
            claim.submission_time - claim.project_start_date
        ).days
        
        # User features
        features['user_account_age'] = claim.user_account_age_days
        features['user_claim_count_30d'] = claim.user_claim_count_30d
        features['user_total_claimed'] = claim.user_total_claimed
        
        # Document features
        features['doc_count'] = len(claim.documents)
        features['avg_doc_confidence'] = np.mean([d.ocr_confidence for d in claim.documents])
        features['suspicious_doc_count'] = sum([1 for d in claim.documents if d.is_suspicious])
        
        # Historical features
        features['project_claim_count'] = claim.project_claim_count
        features['project_completion_pct'] = claim.project_completion_percentage
        
        return FeatureVector(features)
    
    def predict(self, claim: ClaimData) -> FraudPrediction:
        """
        Predict fraud probability
        """
        features = self.extract_features(claim)
        
        # XGBoost prediction
        xgb_prob = self.xgb_model.predict_proba(features.to_array())[0][1]
        
        # Neural network prediction
        nn_prob = self.nn_model.predict(features.to_tensor())[0][0]
        
        # Ensemble (weighted average)
        ensemble_prob = 0.6 * xgb_prob + 0.4 * nn_prob
        
        return FraudPrediction(
            fraud_probability=ensemble_prob,
            risk_score=int(ensemble_prob * 100),
            risk_level=self.get_risk_level(ensemble_prob),
            feature_importance=self.get_feature_importance(features)
        )
```

---

## 8. ANOMALY DETECTION

### 8.1 Anomaly Detection Methods

```python
class AnomalyDetectionEngine:
    """
    Multi-method anomaly detection
    """
    
    def __init__(self):
        self.isolation_forest = IsolationForest(
            n_estimators=200,
            contamination=0.05,
            random_state=42
        )
        
        self.autoencoder = self.build_autoencoder()
        
        self.statistical_detector = StatisticalDetector()
    
    def detect_anomalies(self, data_point: DataPoint) -> AnomalyResult:
        """
        Run all anomaly detection methods
        """
        results = []
        
        # Method 1: Isolation Forest
        if_score = self.isolation_forest.decision_function([data_point.features])
        results.append(AnomalyScore(
            method='isolation_forest',
            score=float(if_score[0]),
            is_anomaly=if_score[0] < -0.3
        ))
        
        # Method 2: Autoencoder reconstruction error
        reconstructed = self.autoencoder.predict([data_point.features])
        mse = np.mean(np.square(data_point.features - reconstructed))
        results.append(AnomalyScore(
            method='autoencoder',
            score=float(mse),
            is_anomaly=mse > self.reconstruction_threshold
        ))
        
        # Method 3: Statistical outlier detection
        stat_score = self.statistical_detector.zscore(data_point)
        results.append(AnomalyScore(
            method='statistical',
            score=float(stat_score),
            is_anomaly=abs(stat_score) > 3.0
        ))
        
        # Aggregate results
        anomaly_votes = sum([1 for r in results if r.is_anomaly])
        
        return AnomalyResult(
            is_anomaly=anomaly_votes >= 2,
            confidence=anomaly_votes / len(results),
            method_scores=results,
            explanation=self.generate_explanation(results)
        )
```

---

## 9. VALIDATION RULES ENGINE

### 9.1 Validation Framework

```python
class ValidationRulesEngine:
    """
    Configurable validation rules engine
    """
    
    def __init__(self):
        self.rules = self.load_rules()
        self.rule_compiler = RuleCompiler()
    
    def validate(self, document: Document, context: ValidationContext) -> ValidationResult:
        """
        Execute all applicable validation rules
        """
        results = []
        
        for rule in self.get_applicable_rules(document.document_type):
            try:
                rule_result = self.execute_rule(rule, document, context)
                results.append(rule_result)
            except Exception as e:
                results.append(RuleResult(
                    rule_id=rule.id,
                    status='ERROR',
                    message=str(e)
                ))
        
        # Aggregate results
        passed = all([r.status == 'PASSED' for r in results])
        
        return ValidationResult(
            passed=passed,
            rule_results=results,
            summary=self.generate_summary(results)
        )
    
    def execute_rule(self, rule: ValidationRule, document: Document, context: ValidationContext) -> RuleResult:
        """
        Execute a single validation rule
        """
        # Compile rule expression if not cached
        compiled_rule = self.rule_compiler.compile(rule.expression)
        
        # Evaluate rule
        rule_context = {
            'document': document,
            'context': context,
            'utils': ValidationUtils()
        }
        
        result = compiled_rule.evaluate(rule_context)
        
        return RuleResult(
            rule_id=rule.id,
            rule_name=rule.name,
            status='PASSED' if result else 'FAILED',
            message=rule.success_message if result else rule.failure_message,
            severity=rule.severity if not result else None
        )
```

---

## 10. INTEGRATION WITH UCMS

### 10.1 API Integration

```python
# FastAPI Application
from fastapi import FastAPI, File, UploadFile, Depends
from fastapi.security import OAuth2PasswordBearer

app = FastAPI(title="ADVFD Service", version="1.0")

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

@app.post("/api/v1/classify")
async def classify_document(
    file: UploadFile = File(...),
    token: str = Depends(oauth2_scheme)
):
    """
    Classify document type
    """
    # Authenticate
    user = await authenticate(token)
    
    # Process document
    image = await load_image(file)
    result = await document_classifier.classify(image)
    
    return {
        "document_type": result.primary_class.class_name,
        "confidence": result.primary_class.confidence,
        "alternatives": [
            {"type": p.class_name, "confidence": p.confidence}
            for p in result.top_predictions[1:]
        ]
    }

@app.post("/api/v1/fraud-check")
async def fraud_check(
    claim_data: ClaimData,
    documents: List[DocumentReference],
    token: str = Depends(oauth2_scheme)
) -> FraudCheckResult:
    """
    Perform fraud detection check
    """
    # Run fraud detection
    fraud_result = await fraud_detector.detect(claim_data, documents)
    
    return FraudCheckResult(
        risk_score=fraud_result.risk_score,
        risk_level=fraud_result.risk_level,
        triggered_rules=fraud_result.triggered_rules,
        recommendations=fraud_result.recommendations
    )
```

---

## 11. PERFORMANCE AND ACCURACY

### 11.1 Performance Targets

| Metric | Target | Current |
|--------|--------|---------|
| Document Classification | < 200ms | 150ms |
| OCR Processing | < 500ms | 380ms |
| Fraud Detection | < 100ms | 85ms |
| Total Pipeline | < 2s | 1.5s |
| Throughput | 100 docs/min | 120 docs/min |

### 11.2 Accuracy Metrics

| Model | Metric | Target | Achieved |
|-------|--------|--------|----------|
| Document Classifier | Accuracy | > 95% | 96.5% |
| OCR | Character Error Rate | < 3% | 2.1% |
| Fraud Detection | Precision | > 90% | 94% |
| Fraud Detection | Recall | > 85% | 89% |
| Anomaly Detection | F1 Score | > 85% | 87.3% |

---

## 12. SECURITY AND PRIVACY

### 12.1 Data Protection

- All document processing in memory only
- No persistent storage of processed documents
- Encryption of data in transit (TLS 1.3)
- Access logging for all operations
- Data retention as per MCMC policy

### 12.2 Model Security

- Model artifacts encrypted at rest
- Access control for model management
- Version control for model lineage
- Adversarial robustness testing

---

## 13. TRAINING AND IMPROVEMENT

### 13.1 Continuous Learning

```python
class ModelImprovementPipeline:
    """
    Continuous model improvement
    """
    
    def __init__(self):
        self.feedback_collector = FeedbackCollector()
        self.retrainer = ModelRetrainer()
        self.evaluator = ModelEvaluator()
    
    async def collect_feedback(self, prediction_id: str, correct_label: str):
        """
        Collect user feedback on predictions
        """
        await self.feedback_collector.store(
            prediction_id=prediction_id,
            predicted=prediction_id.predicted,
            actual=correct_label,
            timestamp=datetime.now()
        )
    
    async def retrain_if_needed(self):
        """
        Trigger retraining if performance degrades
        """
        current_metrics = await self.evaluator.evaluate_current_model()
        
        if current_metrics.accuracy < RETRAIN_THRESHOLD:
            # Prepare new training data
            training_data = await self.feedback_collector.get_training_set()
            
            # Retrain model
            new_model = await self.retrainer.retrain(training_data)
            
            # Evaluate new model
            new_metrics = await self.evaluator.evaluate(new_model)
            
            if new_metrics.accuracy > current_metrics.accuracy:
                # Deploy new model
                await self.deploy_model(new_model)
```

---

## 14. APPENDICES

### Appendix A: API Reference

Complete API endpoint documentation with request/response examples.

### Appendix B: Model Cards

Detailed documentation for each ML model including:
- Training data description
- Model architecture
- Performance metrics
- Limitations and bias analysis

### Appendix C: Error Codes

| Code | Description | Resolution |
|------|-------------|------------|
| ADV001 | Invalid file format | Check supported formats |
| ADV002 | OCR low confidence | Rescan document |
| ADV003 | Fraud detection error | Retry or manual review |

---

**END OF DOCUMENT**
