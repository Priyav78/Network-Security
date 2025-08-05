# Network Security Threat & Anomaly Detection (Capstone)

This capstone project builds an end-to-end threat detection framework using supervised and unsupervised machine learning on real-world network traffic datasets. It integrates bivariate/multivariate statistical analysis, dimensionality reduction, and clustering to detect anomalies and identify attack patterns for intrusion detection systems (IDS).

---

## 🧠 Project Objective

To detect and characterize cyberattack anomalies in network traffic using both labeled and unlabeled data. The project aims to model threats from different angles: user behavior, packet-level data, and full attack sequences.

---

## 📁 Datasets

| Dataset       | Description                                   | Target            | Goal                                     |
|---------------|-----------------------------------------------|--------------------|------------------------------------------|
| **BETH**       | Session-level logs with user activity labels   | `sus`              | Flag suspicious behavior                 |
| **UNSW-NB15**  | Realistic attack traffic across 10 categories | `label` (0 = benign, 1 = attack) | Build classifier for intrusion detection |
| **NS**         | Protocol-level severity mapping (exploratory) | `Severity Level`   | Understand protocol-specific severity    |

---

## 🧪 Techniques Used

### ➤ Preprocessing & Analysis
- Missing value imputation, scaling (`StandardScaler`)
- Categorical encoding (`get_dummies`, `LabelEncoder`)
- Chi-Square, ANOVA for bivariate relationships
- PCA for variance analysis and dimensionality reduction

### ➤ Supervised Models
- **K-Nearest Neighbors (KNN)**
- **Gradient Boosting**
- **Random Forest**
- **Logistic Regression**
- **LightGBM**
- **XGBoost**

### ➤ Unsupervised Models
- **K-Means Clustering**
- **DBSCAN (Density-Based Clustering)**
- **Hierarchical Agglomerative Clustering (HAC)**
- **Isolation Forest (Anomaly Detection)**

---

## 📊 Evaluation Metrics

- Classification: Accuracy, Precision, Recall, F1-Score, Confusion Matrix
- Clustering: Silhouette Score, Visual PCA Clusters
- PCA: Variance explained and component inspection

---

## 💡 Key Findings

- **PCA** helped reveal cluster structure and variance drivers across all datasets.
- **KNN & Gradient Boosting** showed strong classification performance in supervised settings.
- **DBSCAN** effectively identified high-density anomalies but was sensitive to `eps` and `min_samples`.
- **UNSW-NB15** produced highest classification accuracy (~87%) with LightGBM.

---

## ⚠️ Limitations

- Class imbalance not fully resolved in some classifiers
- Clustering interpretability limited without feature attribution
- DBSCAN parameter sensitivity not thoroughly grid searched

---

## 🛠 Project Structure

