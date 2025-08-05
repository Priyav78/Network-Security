# Network Security Threat & Anomaly Detection (Capstone)

This capstone project implements an advanced end-to-end framework for threat and anomaly detection using real-world network traffic datasets (BETH, UNSW-NB15). It integrates statistical testing, dimensionality reduction, supervised learning, and clustering-based anomaly detection, designed with real-world deployment and interpretability in mind.

## Objective

To design a scalable and explainable system for identifying suspicious network traffic patterns, leveraging machine learning and statistical techniques to strengthen intrusion detection capabilities.

## Performance Improvements Achieved

- **UNSW-NB15 dataset**: Gradient Boosting achieved a classification accuracy of ~87% with minimal feature engineering, outperforming Logistic Regression and KNN models.
- **Dimensionality reduction using PCA** improved clustering interpretability by isolating principal components explaining >95% variance, leading to better separation in DBSCAN and HAC results.
- **Regularization (Lasso)** helped identify redundant features and reduce multicollinearity, enhancing generalization in supervised models.
- **Customized hyperparameter tuning** for `eps` and `min_samples` in DBSCAN improved anomaly recall on both datasets.

## Novel Feature Engineering & Preprocessing Insights

- **Cross-dataset variable normalization** enabled meaningful comparison between BETH and UNSW despite different scales and feature spaces.
- **Log transformations** and clipping were used to handle heavy-tailed distributions (e.g., `rate`, `sttl`, `swin`), reducing skewness and stabilizing model gradients.
- **Univariate + Chi-Square/ANOVA** feature filtering pipelines narrowed down core predictors, reducing noise and improving model convergence.

## Computational Optimizations

- Dimensionality reduction via PCA significantly reduced training time for clustering models on BETH dataset from ~40s to <10s.
- Sampling strategy applied to HAC and DBSCAN avoided full-matrix computation for 100K+ samples.
- Reused encoded matrices and scaled features across pipelines to avoid redundant computation and memory overhead.

## Business Relevance

- **Real-world deployment scenario**: This project simulates an internal IDS system in an enterprise or telecom setting, where real-time packet monitoring flags abnormal user behavior or protocol activity.
- **False positive mitigation**: By combining supervised and unsupervised methods, the system is tuned for both high precision (to avoid alert fatigue) and recall (to detect hidden patterns).
- **Cost-effective threat detection**: The framework avoids deep packet inspection and instead relies on statistical signals and behavior, lowering compute cost while remaining effective.

## Unique Approaches & Design Decisions

- Combined **supervised (KNN, Gradient Boosting)** and **unsupervised (DBSCAN, HAC)** approaches to cross-validate anomalies and uncover both known and unknown attack vectors.
- Used **bivariate and multivariate statistics** (Chi-Square, ANOVA) not just for analysis but as a gating step for feature selection.
- Applied **clustering on PCA-reduced dimensions** to isolate high-signal regions, improving silhouette scores and interpretability.
- Segmented modeling by dataset and use-case (BETH: user anomaly; UNSW: packet attack classification) instead of merging heterogenous sources, leading to more reliable model results.

## Skills Demonstrated

- Statistical modeling and feature testing
- Multivariate dimensionality reduction with PCA
- Anomaly detection through DBSCAN, HAC, Isolation Forest
- Binary classification for IDS use-cases
- Model interpretability and real-world alignment

## Project Structure

```
/notebooks
  ├── BETH_6.ipynb             # Preprocessing and EDA
  ├── UNSW_NB15_6.ipynb        # Full feature pipeline for UNSW
  ├── NetworkSecurity_6.ipynb  # Statistical and visual analysis
  ├── BETH.ipynb               # PCA + Clustering Models
  ├── UNSW_NB15.ipynb          # Supervised Modeling & Tuning
  ├── NetworkSecurity.ipynb    # Final summaries and insights
/data
  └── Download instructions for BETH, UNSW-NB15
README.md
```

## Author

**Priya Verma**  
M.S. Data Science Candidate  
Capstone in Machine Learning for Cybersecurity Applications