# MIE1628-Project-5 - Phishing Website Detection
This project develops and evaluates a machine learning pipeline for **detecting phishing websites** using structured website behavior data.

---

## Objective
Phishing websites imitate legitimate sites to steal user credentials. The goal is to:
- Identify phishing behavior using machine learning
- Evaluate several models for effectiveness
- Deploy the solution via Azure ML Studio

---
## Dataset Overview
- Source: UCI Phishing Websites Dataset (`.arff` format)
- Features: 30 categorical attributes (`-1`, `0`, `1`)
- Original labels:
  - `1` is Legitimate
  - `0` is Suspicious
  - `-1` is Phishing

### Label Conversion
Converted to binary classification:
- `1` is **Not Phishing (0)**
- `0`, `-1` are **Phishing (1)**

---

## Exploratory Data Analysis

- Key correlated features with phishing behavior:
  - `SFH`: +0.67
  - `popUpWindow`: +0.49
  - `SSLfinal_State`: +0.48
  - `Request_URL`: +0.32

- Visualizations:
  - Label distribution before/after conversion
  - Feature-based bar charts
  - Heatmap of feature correlation

---

## Data Preprocessing
- Converted to DataFrame
- Checked for missing values and ensured correct types
- All features remained in categorical integer format

---
## Models Implemented
### 1. Logistic Regression
- Accuracy: **87%**
- Baseline performance
- Good interpretability

### 2. Decision Tree
- Accuracy: **88.9%**
- Handles non-linearity
- Lower RMSE than Logistic Regression

### 3. Random Forest
- Accuracy: **90.04%**
- Ensemble model with good generalization
- Reduced overfitting

### 4. XGBoost (Best)
- Accuracy: **91%**
- Best precision, recall, and RMSE
- Robust for deployment
---

## Azure ML Deployment
- Used Azure ML Designer to build full pipeline
- Models: Logistic Regression, Boosted Decision Tree
- Pipeline Modules:
  - Upload Data
  - Split Data
  - Train Model
  - Score Model
  - Evaluate Model
### Evaluation
- Accuracy and AUC visualized in Azure
- Deployment-ready workflow
- Easy to plug into production pipelines

---

## Conclusion

- Developed a strong phishing detection model pipeline
- **XGBoost** is the best-performing model (91% accuracy)
- Critical features identified (e.g., SFH, SSL, pop-ups)

---

## Files Included

- `MIE1628_A5.ipynb`: Complete code and analysis
- `MIE1628_A5_B.pdf`: Final report with visualizations
- `README.md`: GitHub summary (this file)

---
