# SYSTEM ARCHITECTURE – Integrated AI Dashboard

This document defines the locked architecture and engineering standards for the Elevvo ML Internship repository.

The system is designed as a unified AI Dashboard integrating five Machine Learning and Deep Learning modules under a single Streamlit application.

This architecture must be followed consistently across all projects.

---

# 1️⃣ Overall System Design

Architecture Type:
Integrated Modular Monolithic Dashboard

Frontend:
- Streamlit Master Dashboard (Single app.py)

Backend:
- Modular project-based structure under src/
- Saved trained models in models/
- Reusable preprocessing and training pipelines

Environment:
- CPU-based execution
- Python ecosystem

---

# 2️⃣ Integrated Projects (Locked)

1. Forest Cover Type Classification
2. Loan Approval Prediction
3. Movie Recommendation System
4. Sales Forecasting
5. Traffic Sign Recognition (Deep Learning)

These five modules are integrated into a single dashboard with separate functional sections.

---

# 3️⃣ Standard ML Workflow (For All ML Projects)

Each ML project must follow:

1. Data Pipeline
2. Preprocessing Module using:
   - sklearn Pipeline
   - ColumnTransformer
3. Model Training Module
4. Cross-Validation
5. Hyperparameter Tuning using GridSearchCV
6. Evaluation Metrics (appropriate per task)
7. Model Serialization using joblib
8. Inference on New Data
9. Integration into Streamlit Dashboard

No standalone notebook-only implementation is allowed as final output.

---

# 4️⃣ Deep Learning Workflow (Traffic Sign Recognition)

The DL project must follow:

1. Image Preprocessing
2. Transfer Learning (MobileNet or similar lightweight model)
3. Fine-tuning strategy
4. EarlyStopping
5. ModelCheckpoint (save best model)
6. Training curve visualization
7. Evaluation using accuracy + confusion matrix
8. Saved model file (.h5 or .keras)
9. Integration into Streamlit dashboard with image upload

CPU-compatible training strategy required.

---

# 5️⃣ Folder Structure (Locked)

Root Structure:

Elevvo-ML-Internship/

- README.md
- ARCHITECTURE.md
- app.py
- requirements.txt

- models/
    - forest_model.pkl
    - loan_model.pkl
    - recommender.pkl
    - sales_model.pkl
    - traffic_sign_model.h5

- src/
    - forest/
    - loan/
    - recommender/
    - sales/
    - traffic/

Each module inside src/ must contain:
- preprocessing.py
- train.py
- predict.py
- utils.py (if required)

---

# 6️⃣ Streamlit Integration Strategy

Single Master Dashboard (app.py):

Sidebar Navigation:
- Forest Cover Classification
- Loan Approval
- Recommendation System
- Sales Forecasting
- Traffic Sign Recognition

Each section:
- Loads saved model
- Accepts user input
- Performs prediction
- Displays output
- Shows visualization (if applicable)

---

# 7️⃣ Engineering Principles

- Modular code structure
- No hardcoded preprocessing in UI
- Reproducible pipelines
- Clean separation of training and inference
- Production-style model persistence
- Clear evaluation reporting
- Scalable folder organization

---

# 8️⃣ Deployment Strategy

Target Deployment:
- Streamlit Cloud (Primary)
- Render (Optional)

App must run from:
streamlit run app.py

---

# 9️⃣ Version Control Rule

Architecture is locked unless intentionally refactored.
All future development must follow this document.

---

Author:
Ahmad Gul
Machine Learning & Applied AI Systems
