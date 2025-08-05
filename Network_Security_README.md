# Network Security Threat & Anomaly Detection (Capstone)

This capstone project presents a comprehensive machine learning pipeline for detecting cyber threats and anomalies in real-world network traffic datasets (BETH, UNSW-NB15). The solution spans data preparation, feature engineering, statistical testing, dimensionality reduction, classification, and clustering, offering both academic and applied security value.

## Objective

Design and implement an effective anomaly detection framework for cyber intrusion monitoring, integrating supervised learning, unsupervised clustering, and statistical signal analysis.

## Datasets

| Dataset       | Description                                   | Target            | Purpose                                  |
|---------------|-----------------------------------------------|--------------------|------------------------------------------|
| BETH          | Session-level logs of user behavior            | `sus`              | Detect session anomalies and misuse      |
| UNSW-NB15     | Attack/benign traffic with engineered features | `label` (0/1)      | Classify known attack vectors            |
| NS (Exploratory) | Protocol-level event severity               | `Severity Level`   | Analyze and segment protocol traffic     |

## Pipeline Workflow

### Preprocessing & Feature Engineering
- Null value handling, type fixes, deduplication
- Standard scaling and label encoding
- Chi-square and ANOVA tests for feature-target association
- PCA for dimensionality reduction (>95% variance explained)
- Log and power transforms for highly skewed metrics

### Exploratory & Statistical Analysis
- Univariate analysis: histograms, boxplots, log distributions
- Bivariate relationships: attack type vs metrics
- Multivariate plots and heatmaps
- PCA projection plots with color-coded clusters

### Supervised Learning Models (UNSW-Focused)
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Gradient Boosting Classifier
- Random Forest
- LightGBM
- XGBoost

### Unsupervised Learning Models (BETH & NS)
- K-Means Clustering
- DBSCAN (Density-Based Spatial Clustering)
- Hierarchical Agglomerative Clustering (HAC)
- Isolation Forest

## Performance Highlights

- Gradient Boosting on UNSW-NB15 achieved ~87% accuracy, outperforming KNN and Logistic Regression.
- DBSCAN parameter tuning (eps/min_samples) significantly improved recall on outlier detection tasks.
- PCA reduced training and clustering time from 40s to under 10s per model, with clearer cluster separation.
- Lasso regularization identified irrelevant or redundant variables improving model stability.

## Novel Contributions & Unique Approaches

- Separate treatment of labeled (UNSW) vs. unlabeled (BETH) datasets enabled more tailored preprocessing and model choice.
- Combined statistical testing (chi-square, ANOVA) and PCA to define a signal-aware reduced feature space.
- Used Isolation Forest to benchmark unsupervised anomaly detection performance across datasets.
- Conducted multistage analysis including exploratory stats, dimensionality reduction, model building, and cluster evaluation.

## Business Relevance

- Mimics enterprise-grade network IDS systems by flagging both known and unknown malicious activity.
- Balances model precision and anomaly recall to support cost-effective alerting and investigation.
- Provides an interpretable and modular framework for integrating with security monitoring platforms.
- Can be extended for telecom, cloud security, or enterprise firewall monitoring use cases.

## Project Structure

```
/notebooks
  ├── BETH_6.ipynb             # Preprocessing, EDA, bivariate stats
  ├── UNSW_NB15_6.ipynb        # Feature engineering + supervised prep
  ├── NetworkSecurity_6.ipynb  # Comparative statistical analysis
  ├── BETH.ipynb               # PCA + KMeans + DBSCAN + HAC
  ├── UNSW_NB15.ipynb          # Supervised modeling (KNN, GBC, RF, XGB)
  ├── NetworkSecurity.ipynb    # Final insights and synthesis
/data
  └── Access details for BETH and UNSW-NB15
README.md
```

## Skills Demonstrated

- Full machine learning pipeline development
- Statistical testing and dimensionality reduction
- Model evaluation and tuning across classification/clustering
- Data visualization and interpretability of high-dimensional data
- Scalability and optimization of computational analysis

## Author

**Priya Verma**  
M.S. Data Science Candidate  
Capstone in Machine Learning for Cybersecurity Applications