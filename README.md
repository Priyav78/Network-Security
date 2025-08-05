# Network Security Threat & Anomaly Detection (Capstone)

This capstone project presents a complete data science pipeline to detect network intrusions and cyber anomalies using real-world datasets (BETH, UNSW-NB15). It spans end-to-end preprocessing, univariate/bivariate statistical analysis, dimensionality reduction, and multiple supervised and unsupervised ML techniques.

## Objective

Build a robust machine learning framework for identifying suspicious network activity and attack patterns using labeled and unlabeled traffic data.

## Datasets

| Dataset       | Description                                   | Target            | Purpose                                  |
|---------------|-----------------------------------------------|--------------------|------------------------------------------|
| BETH          | Session-level user activity logs               | `sus`              | Flag suspicious behavior                 |
| UNSW-NB15     | Intrusion detection traffic with 10 attack types| `label` (0/1)      | Train classifiers for attack detection  |
| NS (Exploratory) | Protocol severity mapping                   | `Severity Level`   | Examine protocol-level anomalies         |

## Project Workflow

### 1. Preprocessing
- Dataset inspection, handling nulls, duplicates
- Data type fixing, standardization (`StandardScaler`)
- Categorical encoding (`LabelEncoder`, `get_dummies`)

### 2. Exploratory Data Analysis (EDA)
- Distribution plots, histograms, boxplots
- Correlation matrices
- Feature class distributions

### 3. Univariate & Bivariate Analysis
- Chi-Square Tests (Categorical)
- ANOVA & F-statistics (Numerical)
- Interaction plots by attack type & severity

### 4. Dimensionality Reduction
- **Principal Component Analysis (PCA)** to reduce dimensionality and visualize separability

### 5. Supervised Learning
- **K-Nearest Neighbors (KNN)**
- **Gradient Boosting Classifier**
- **Logistic Regression**
- **Random Forest**
- **LightGBM**, **XGBoost** (UNSW-specific)

### 6. Unsupervised Learning
- **K-Means Clustering**
- **DBSCAN** (Density-Based Clustering)
- **Hierarchical Agglomerative Clustering (HAC)** with dendrograms
- **Isolation Forest** for anomaly detection

### 7. Model Evaluation
- Accuracy, Precision, Recall, F1-Score
- Confusion Matrix
- Silhouette Score, PCA visual clusters

## Key Findings

- **PCA** identified latent structure and separated key attack types in lower dimensions.
- **KNN & Boosting models** were highly effective with UNSW-NB15 labeled data.
- **DBSCAN** revealed high-density anomalous zones but required careful tuning.
- The combination of feature-level statistical tests and ML led to better understanding of attack surface characteristics.

## Folder Structure

```
/notebooks
  ├── BETH_6.ipynb             # Full preprocessing and EDA
  ├── UNSW_NB15_6.ipynb        # Full preprocessing and EDA for UNSW
  ├── NetworkSecurity_6.ipynb  # Univariate/bivariate analysis across datasets
  ├── BETH.ipynb               # PCA and modeling (KNN, clustering)
  ├── UNSW_NB15.ipynb          # Supervised model training and evaluation
  ├── NetworkSecurity.ipynb    # Final synthesis and insight summary
/data
  └── Instructions to download datasets (BETH, UNSW-NB15)
README.md
```

## Skills Demonstrated

- Data cleaning, transformation, and feature engineering
- Dimensionality reduction using PCA
- Supervised and unsupervised model development
- Statistical testing for feature relevance
- Evaluation and interpretation of clustering results
- Modular notebook organization and end-to-end ML lifecycle

## Author

**Priya Verma**  
M.S. Data Science Candidate  
Capstone in Machine Learning for Cybersecurity Applications