# Project_Phishing_Detection-Model_Interpretability_and_Deployment_Report
🚀 Phishing URL Websites Detection Model Interpretability &amp; Deployment Report
Here's a concise and informative README based on your project:

---

# 🛡️ Phishing Website Detection using ML

This project aims to detect phishing websites using machine learning techniques. It includes data analysis, feature engineering, model training, evaluation, and SHAP-based explainability.

---

## 📁 Dataset Overview

- **Source**: `dataset_phishing.csv`
- **Target**: `status` (legitimate/phishing)
- **Rows**: 11,430 | **Features**: 87 numerical + 2 categorical

---

## 📊 Exploratory Data Analysis (EDA)

### 1. Summary Statistics  
Includes mean, median, std, min, and max values for 87 numerical features.  
Notable fields:
- `length_url`: Avg = 61, Max = 1641  
- `domain_age`: Range = -12 to 12,874  
- `web_traffic`: Highly skewed, max = 10M+

### 2. Categorical Analysis  
- `url`: Mode is a common phishing link  
- `status`: Balanced classes (50% each)

### 3. Visualizations  
- Histograms for distribution  
- Pairplots (e.g., `length_url` vs `status`)  
- Correlation heatmaps to identify highly correlated features (|r| > 0.85)

---

## 🚀 Feature Selection

- Used **RandomForest** & **Mutual Information**  
- Dropped low-impact features (`importance < 0.005`, `MI < 0.01`)  

---

## 🧠 Models Trained

| Model              | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|-------------------|----------|-----------|--------|----------|---------|
| XGBoost (Best)     | ~99%     | ~99%      | ~99%   | ~99%     | ~0.99   |
| Random Forest      | High     | High      | High   | High     | High    |
| Logistic, SVM, DT  | Good     | Moderate  | Moderate | Moderate | Moderate |

Accuracy: 95.2%
Precision: 94.8%
Recall: 95.6%
F1 Score: 95.2%
ROC-AUC: 0.97

---

## 🔍 Explainability with SHAP

- SHAP summary plots & force plots  
- Helps interpret top influencing features for each prediction

---

## 🌐 Web App (Flask)

- `predict`: Receives input, returns phishing probability  
- `explain`: Renders SHAP force plot for local explanations

---

## 💾 Files

- `phishing_detector_model.pkl`: Trained XGBoost model  
- `explainer_shap.pkl`: SHAP explainer  
- `shap_summary_plot.png`, `roc_curves.png`: Visuals  
- `app.py`: Flask backend

## 🧑‍💻 Author

**Shshank Verma**  

[LinkedIn](https://www.linkedin.com/in/shshankverma) | [Email](mailto:shshankvermaa@gmail.com)

