
# 🛡️ Network Security Project: Multivariate & Machine Learning Analysis of Cyberattacks

This project performs a complete machine learning and multivariate statistical analysis pipeline on three cybersecurity datasets. It includes preprocessing, bivariate and multivariate analysis, dimensionality reduction (PCA), and modeling using supervised and unsupervised techniques to detect and classify cyber threats.

---

## 🎯 Project Objective

To explore, analyze, and model cyberattack behavior using different types of network datasets for the purpose of detecting anomalies, assessing threat severity, and building an effective intrusion detection system (IDS).

---

## 📁 Datasets Overview

| Dataset       | Purpose                                             | Target Variable | Primary Goal |
|---------------|-----------------------------------------------------|------------------|--------------|
| **BETH**       | User/session behavioral analysis                   | `sus`            | Detect suspicious user activity |
| **NS**         | Packet-level threat severity classification        | `Severity Level` | Predict threat level (low/med/high) |
| **UNSW-NB15**  | Full-scale intrusion detection (binary & multiclass) | `label` (0/1)    | Classify and understand attacks |

---

## 🔄 Workflow

### 1. Preprocessing
- Handled missing values with `SimpleImputer`
- Dropped redundant or irrelevant features
- Categorical variables encoded via `get_dummies` and `LabelEncoder`
- Numerical variables scaled using `StandardScaler`
- Final cleaned DataFrames saved for further analysis

### 2. Bivariate Analysis
- **BETH**: Explored relationship between `sus` and user/session features
- **NS**: Visualized how severity level correlates with protocol/service
- **UNSW-NB15**: Attack category frequency by service visualized via bubble plots
- Statistical tests:
  - Chi-Square and ANOVA applied to categorical-numeric pairings

### 3. Multivariate Analysis
- **Correlation Analysis** to find multicollinearity and key features
- **PCA** performed:
  - **BETH**: 11 components ≈ 78% variance
  - **NS**: 16 components ≈ 75% variance
  - **UNSW-NB15**: 30 components ≈ 32% variance (expected for sparse, encoded data)
- PCA used to understand variance structure, but not applied for tree-based modeling

---

## 🤖 Modeling Results

| Dataset      | Model               | Type        | Use Case                                                    | Test Accuracy | Model Ranking |
|--------------|---------------------|-------------|--------------------------------------------------------------|----------------|----------------|
| **BETH**     | Random Forest        | Supervised  | High-performance threat detection                            | —              | 1st            |
|              | Logistic Regression  | Supervised  | Interpretable baseline classifier                            | —              | 2nd            |
|              | Isolation Forest     | Unsupervised| Anomaly pre-screening or hybrid flagging                    | —              | 3rd            |
| **NS**       | Random Forest        | Supervised  | High-capacity ensemble model, moderate tuning               | ~33%           | 1st            |
|              | Logistic Regression  | Supervised  | Interpretable baseline classifier                           | ~33%           | 2nd            |
|              | XGBoost              | Supervised  | Boosted trees with advanced tuning, no improvement          | ~33%           | 3rd            |
| **UNSW-NB15**| LightGBM             | Supervised  | Best overall performance; production-ready IDS              | 86.7%          | 1st            |
|              | Random Forest        | Supervised  | Non-linear learner capturing threat patterns                | 85.6%          | 2nd            |
|              | Logistic Regression  | Supervised  | Baseline classifier with strong recall on attacks           | 80.9%          | 3rd            |

---

## 📊 Visual Insights

- Bubble plots showed attack types like Generic, Exploits, and DoS were service-specific
- PCA visualizations showed that a small set of components captured most of the variance in BETH and NS
- Confusion matrices from models showed high recall for attacks, especially in UNSW-NB15

---

## 🧠 Skills Demonstrated

- Data cleaning and preprocessing
- Statistical bivariate testing
- PCA-based dimensionality reduction
- Supervised learning: Random Forest, Logistic Regression, LightGBM, XGBoost
- Unsupervised detection: Isolation Forest
- Model evaluation: Accuracy, Precision, Recall, F1-Score, Confusion Matrices

---

## 🚀 How to Run

```bash
pip install -r requirements.txt
# Open and run notebooks in order:
# Preprocessing → Bivariate Analysis → Multivariate Analysis → Modeling
```

---

## 🛠️ Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
lightgbm
xgboost
```

---

## 👩‍💻 Author

**Priya Verma** — M.S. Data Science Candidate  
This project was completed as part of a cybersecurity-focused machine learning research initiative.
