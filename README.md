
# 🛡️ Network Security - Multivariate Analysis with Machine Learning

This project performs multivariate statistical analysis and machine learning modeling to detect and classify cyberattacks using real and synthetic network datasets. It explores dimensionality reduction, interpretable modeling, and advanced tree-based classifiers for intrusion detection.

---

## 🎯 Project Objective

To build an effective machine learning framework that detects anomalous or malicious network behavior by leveraging multivariate relationships across diverse datasets. The project compares model types, identifies key features and patterns, and provides insight into severity and structure of cyber threats.

---

## 📁 Datasets Used

| Dataset           | Purpose                                                                 | Source |
|------------------|-------------------------------------------------------------------------|--------|
| **BETH**          | Analyze user/session-based anomalies and classify suspicious activity   | [BETH on Kaggle](https://www.kaggle.com/datasets/katehighnam/beth-dataset) |
| **UNSW_NB15**     | Detect and classify real-world attack types (e.g., DoS, Exploits)        | [UNSW NB15 on Kaggle](https://www.kaggle.com/datasets/mrwellsdavid/unsw-nb15) |
| **NetworkSecurity** | Predict severity levels of traffic from simulated cyber event logs      | [Cybersecurity Attacks on Kaggle](https://www.kaggle.com/datasets/teamincribo/cyber-security-attacks) |

---

## 🔄 Workflow

### 1. **Preprocessing**
- Dropped unused or sparse categorical fields
- One-hot encoded protocol, service, and state features
- Scaled numerical fields using StandardScaler
- Cleaned datasets were stored for modeling

### 2. **Multivariate Analysis**
- Correlation heatmaps and bubble plots used to visualize attack patterns
- PCA applied:
  - **BETH**: 11 components explained ~78% of variance
  - **UNSW_NB15**: 30 components explained ~32% variance (expected due to sparsity)
  - **NetworkSecurity**: 16 components explained ~75% variance
- PCA insights revealed redundancy, guiding model feature selection

### 3. **Modeling**
Three models were trained and evaluated on the UNSW_NB15 dataset using selected features:

| Model                | Accuracy | Recall (Normal) | Recall (Attack) | F1 Score | Rank |
|---------------------|----------|------------------|------------------|----------|------|
| Logistic Regression | 80.9%    | 0.63             | 0.96             | 0.80     | 3rd  |
| Random Forest       | 85.6%    | —                | —                | —        | 2nd  |
| LightGBM            | 86.7%    | 0.87             | 0.87             | 0.87     | 1st  |

- LightGBM outperformed others with the most balanced and highest scores
- Random Forest showed strong non-linear performance
- Logistic Regression served as a high-recall baseline

---

## 📊 Key Visual Insights

- Bubble plots exposed attack concentration on specific services like DNS
- PCA revealed high feature redundancy, guiding dimensionality decisions
- Confusion matrices highlighted trade-offs between false positives and recall

---

## 🧠 Skills Demonstrated

- Feature engineering (scaling, encoding, filtering)
- Dimensionality reduction via PCA
- Supervised modeling (Logistic Regression, Random Forest, LightGBM)
- Model selection and hyperparameter tuning (RandomizedSearchCV, GridSearchCV)
- Visual interpretation of attack patterns

---

## 🚀 How to Run

```bash
# Clone repo and install requirements
pip install -r requirements.txt

# Follow notebook order: BETH → NS → UNSW_NB15
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
```

---

## 👩‍💻 Author

**Priya Verma** — M.S. Data Science Candidate  
This project models multivariate network data to build and compare cyberattack detection systems using machine learning.
