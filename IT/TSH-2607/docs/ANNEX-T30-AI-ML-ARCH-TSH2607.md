# ANNEX T30: AI/ML ARCHITECTURE

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the Artificial Intelligence and Machine Learning architecture for the USP Claims Management System, detailing how AI/ML capabilities enhance automation, decision support, fraud detection, and predictive analytics.

### 1.1 KRISA Compliance
- **KRISA Section 16**: Emerging technology adoption
- **AI Governance Framework**: Responsible AI principles
- **Data Protection**: PDPA compliance for AI processing

---

## 2. AI/ML STRATEGY

### 2.1 AI Use Cases

| Use Case ID | Use Case | AI Technique | Business Value |
|-------------|----------|--------------|----------------|
| AI-001 | Document Classification | Computer Vision | 80% auto-routing |
| AI-002 | Data Extraction | NLP/OCR | 70% less manual entry |
| AI-003 | Fraud Detection | Anomaly Detection | 90% fraud catch rate |
| AI-004 | Claim Scoring | Classification | Risk-based prioritization |
| AI-005 | Processing Time Prediction | Regression | Accurate SLAs |
| AI-006 | Amount Validation | Outlier Detection | Flag anomalies |
| AI-007 | Chatbot Assistant | LLM/NLP | 24/7 support |
| AI-008 | Duplicate Detection | Similarity | 99% match accuracy |
| AI-009 | Approval Routing | Recommendation | Optimal assignment |
| AI-010 | Trend Forecasting | Time Series | Budget planning |

### 2.2 ML Maturity Model

| Level | Description | Target Timeline |
|-------|-------------|-----------------|
| L1 - Descriptive | Historical reporting | Month 1 |
| L2 - Diagnostic | Root cause analysis | Month 3 |
| L3 - Predictive | Future forecasting | Month 6 |
| L4 - Prescriptive | Action recommendations | Month 9 |
| L5 - Autonomous | Self-optimizing systems | Month 12 |

---

## 3. AI/ML ARCHITECTURE

### 3.1 Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       AI/ML ARCHITECTURE                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      ML PLATFORM (Oracle ML)                         │   │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌───────────┐  │   │
│  │  │   OML4SQL   │  │   OML4Py    │  │   AutoML    │  │   ONNX    │  │   │
│  │  │  (In-DB)    │  │  (Python)   │  │  (Auto-tune)│  │  (Models) │  │   │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └───────────┘  │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│       ┌────────────────────────────┼────────────────────────────┐          │
│       │                            │                            │          │
│       ▼                            ▼                            ▼          │
│  ┌──────────┐               ┌──────────┐               ┌──────────┐       │
│  │  NLP     │               │  Vision  │               │  Analytics│       │
│  │  Engine  │               │  Engine  │               │  Engine   │       │
│  │          │               │          │               │           │       │
│  │ • LLM    │               │ • OCR    │               │ • Anomaly │       │
│  │ • NER    │               │ • Classify│              │ • Predict │       │
│  │ • Sentiment│             │ • Extract│               │ • Cluster │       │
│  └──────────┘               └──────────┘               └──────────┘       │
│       │                            │                            │          │
│       └────────────────────────────┼────────────────────────────┘          │
│                                    │                                       │
│                                    ▼                                       │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                         MODEL REPOSITORY (MLOps)                     │   │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌────────┐ │   │
│  │  │ Version  │  │  Train   │  │  Deploy  │  │ Monitor  │  │ Retrain│ │   │
│  │  │ Control  │  │  Pipeline│  │  Pipeline│  │  & Alert │  │ Trigger│ │   │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘  └────────┘ │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Technology Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| ML Platform | Oracle Machine Learning | In-database ML |
| NLP | Hugging Face Transformers | Text processing |
| Computer Vision | Tesseract + Custom CNN | Document OCR |
| Deep Learning | TensorFlow/PyTorch | Complex models |
| MLOps | MLflow + Custom | Model lifecycle |
| Vector DB | Oracle Vector DB | Semantic search |

---

## 4. AI/ML MODELS

### 4.1 Document Processing Models

#### Model: DOC-CLASS-001 (Document Classification)

| Attribute | Specification |
|-----------|--------------|
| Type | CNN + Transformer |
| Input | Document images (PDF/JPG/PNG) |
| Output | Document type (Invoice, Receipt, Certificate, etc.) |
| Classes | 25 document types |
| Accuracy | 96% |
| Inference Time | < 500ms |
| Training Data | 50,000 labeled documents |

```python
# Document Classification Inference
class DocumentClassifier:
    def __init__(self, model_path):
        self.model = load_model(model_path)
        self.classes = ['invoice', 'receipt', 'contract', 
                       'certificate', 'statement', ...]
    
    def classify(self, document_image):
        # Preprocess
        processed = self.preprocess(document_image)
        
        # Inference
        predictions = self.model.predict(processed)
        
        # Return top-3 with confidence
        return {
            'document_type': self.classes[top_idx],
            'confidence': float(confidence),
            'alternatives': alt_predictions
        }
```

#### Model: DATA-EXTRACT-001 (Information Extraction)

| Field | Extraction Method | Accuracy |
|-------|------------------|----------|
| Invoice Number | Regex + NER | 94% |
| Date | Date parser | 96% |
| Amount | Numeric extraction | 98% |
| Vendor | Named Entity | 89% |
| Line Items | Table detection | 85% |

### 4.2 Fraud Detection Models

#### Model: FRAUD-DETECT-001 (Anomaly Detection)

| Component | Algorithm | Purpose |
|-----------|-----------|---------|
| Amount Anomaly | Isolation Forest | Unusual claim amounts |
| Pattern Matching | Clustering | Similar fraud patterns |
| Network Analysis | Graph Neural Network | Collusion detection |
| Temporal Analysis | LSTM | Time-based anomalies |

#### Fraud Risk Scoring

```
┌─────────────────────────────────────────────────────────────────┐
│              FRAUD RISK SCORING MODEL                           │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Input Features:                                                │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐ │
│  │   Historical    │  │   Claim         │  │   External      │ │
│  │   Features      │  │   Features      │  │   Features      │ │
│  │                 │  │                 │  │                 │ │
│  │ • Past rejections│  │ • Amount       │  │ • SSM status    │ │
│  │ • Claim frequency│ │ • Category     │  │ • Credit score  │ │
│  │ • Avg amounts   │  │ • Documents    │  │ • News sentiment│ │
│  │ • Delays        │  │ • Timing       │  │ • Peer comparison│ │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘ │
│           │                   │                   │             │
│           └───────────────────┼───────────────────┘             │
│                               ▼                                 │
│                    ┌─────────────────┐                          │
│                    │  Ensemble Model │                          │
│                    │  (XGBoost + NN) │                          │
│                    └────────┬────────┘                          │
│                             │                                   │
│                             ▼                                   │
│                    ┌─────────────────┐                          │
│                    │  Risk Score     │                          │
│                    │  0-100          │                          │
│                    │  + Explanation  │                          │
│                    └─────────────────┘                          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 4.3 Predictive Models

#### Model: TIME-PREDICT-001 (Processing Time Estimation)

| Feature | Weight | Description |
|---------|--------|-------------|
| Claim Complexity | 0.25 | Document count, categories |
| Historical Patterns | 0.30 | Past processing times |
| Current Queue | 0.20 | Pipeline depth |
| SP History | 0.15 | Past accuracy |
| Seasonality | 0.10 | Time of year effects |

**Model Performance:**
- MAE: 1.2 days
- RMSE: 2.1 days
- R²: 0.84

#### Model: VOLUME-FORECAST-001 (Claim Volume Prediction)

| Horizon | Algorithm | Accuracy |
|---------|-----------|----------|
| Weekly | Prophet + ARIMA | 92% |
| Monthly | LSTM | 88% |
| Quarterly | Ensemble | 85% |
| Annual | Trend Analysis | 82% |

---

## 5. NLP CAPABILITIES

### 5.1 Chatbot Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    CHATBOT ARCHITECTURE                         │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  User Query                                                     │
│     │                                                           │
│     ▼                                                           │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              INTENT CLASSIFICATION                       │   │
│  │  (Fine-tuned BERT model for UCMS domain)                │   │
│  │                                                          │   │
│  │  Intents:                                                │   │
│  │  • check_status      • submit_document                  │   │
│  │  • payment_query     • policy_question                  │   │
│  │  • technical_help    • escalate_human                   │   │
│  └─────────────────────────────────────────────────────────┘   │
│     │                                                           │
│     ▼                                                           │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              ENTITY EXTRACTION                           │   │
│  │  • Claim numbers    • Dates    • Amounts                │   │
│  │  • Service Provider names                                │   │
│  └─────────────────────────────────────────────────────────┘   │
│     │                                                           │
│     ▼                                                           │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              RESPONSE GENERATION                         │   │
│  │                                                          │   │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐   │   │
│  │  │   Database   │  │   Template   │  │   LLM        │   │   │
│  │  │   Query      │  │   Response   │  │   (GPT-4)    │   │   │
│  │  │              │  │              │  │   Fallback   │   │   │
│  │  └──────────────┘  └──────────────┘  └──────────────┘   │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 5.2 Document Understanding

| Capability | Model | Use Case |
|------------|-------|----------|
| Named Entity Recognition | spaCy + Custom | Extract SP names, project codes |
| Sentiment Analysis | BERT | Analyze SP feedback |
| Text Classification | BERT | Categorize queries |
| Summarization | T5 | Generate claim summaries |
| Question Answering | RoBERTa | Policy Q&A |

---

## 6. MLOPS PIPELINE

### 6.1 Model Lifecycle

```
┌─────────────────────────────────────────────────────────────────┐
│                    MLOPS LIFECYCLE                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐     │
│  │   Data   │──▶│  Feature │──▶│  Train   │──▶│ Evaluate │     │
│  │  Ingest  │   │  Eng.    │   │  Model   │   │  Model   │     │
│  └──────────┘   └──────────┘   └──────────┘   └────┬─────┘     │
│                                                    │            │
│                         ┌──────────────────────────┘            │
│                         ▼                                       │
│              ┌─────────────────┐                               │
│              │  Performance    │                               │
│              │  Acceptable?    │                               │
│              └────────┬────────┘                               │
│                       │                                         │
│            ┌──────────┴──────────┐                            │
│            ▼                     ▼                            │
│     ┌──────────┐          ┌──────────┐                        │
│     │   YES    │          │    NO    │                        │
│     └────┬─────┘          └────┬─────┘                        │
│          │                     │                               │
│          ▼                     ▼                               │
│     ┌──────────┐          ┌──────────┐                        │
│     │  Deploy  │          │  Retrain │                        │
│     │  to Prod │          │  Iterate │                        │
│     └────┬─────┘          └──────────┘                        │
│          │                                                     │
│          ▼                                                     │
│     ┌──────────┐                                              │
│     │  Monitor │◀─────────────────────────────┐               │
│     │  & Alert │                              │               │
│     └────┬─────┘                              │               │
│          │                                    │               │
│          ▼                                    │               │
│     ┌──────────┐   Drift Detected?           │               │
│     │  Drift?  │─────────────────────────────┘               │
│     └──────────┘                                              │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 6.2 Model Monitoring

| Metric | Threshold | Action |
|--------|-----------|--------|
| Accuracy Drop | > 5% | Alert + Review |
| Latency | > 2s | Scale resources |
| Prediction Drift | PSI > 0.2 | Retrain trigger |
| Data Drift | KS > 0.1 | Investigation |
| Error Rate | > 2% | Rollback |

---

## 7. AI GOVERNANCE

### 7.1 Responsible AI Principles

| Principle | Implementation |
|-----------|----------------|
| Fairness | Bias testing across SP categories |
| Transparency | Explainable predictions |
| Accountability | Human-in-the-loop for critical decisions |
| Privacy | PDPA-compliant data usage |
| Safety | Adversarial testing |

### 7.2 Explainability

| Model | Explanation Method |
|-------|-------------------|
| Fraud Detection | SHAP values + Feature importance |
| Document Classification | Attention visualization |
| Time Prediction | Feature contribution breakdown |
| Chatbot | Intent confidence + Source attribution |

---

## 8. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T28-VALUE-ADDED | AI Features |
| CR-002 | ANNEX-T31-SECURITY-FRAMEWORK | AI Security |
| CR-003 | ANNEX-T24-REPORT-CATALOG | AI Analytics |
| CR-004 | ANNEX-T27-SELF-SERVICE | Chatbot |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
