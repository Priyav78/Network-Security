
# 🛡️ Network Security - Cyberattack Detection via Machine Learning

This project analyzes and models network security data to detect cyberattacks using machine learning. It leverages three cybersecurity datasets and follows a full ML pipeline from preprocessing to modeling, including dimensionality reduction with PCA.

---

## 🎯 Project Purpose

To build a machine learning framework that identifies malicious or anomalous network behavior across multiple real-world and synthetic datasets. This includes detecting attacks, assessing severity, and exploring which features and patterns are most predictive of security breaches.

---

## 📁 Datasets Used

| Dataset           | Description                                                                 | Source |
|------------------|-----------------------------------------------------------------------------|--------|
| **BETH**          | Synthetic cybersecurity dataset with labeled attacks across network logs   | [BETH Dataset on Kaggle](https://www.kaggle.com/datasets/katehighnam/beth-dataset) |
| **UNSW_NB15**     | Realistic dataset from IXIA's Lab – includes exploits, DoS, reconnaissance  | [UNSW NB15 on Kaggle](https://www.kaggle.com/datasets/mrwellsdavid/unsw-nb15) |
| **NetworkSecurity** | Simulated data combining various cybersecurity event logs with severity levels | [Cybersecurity Attacks on Kaggle](https://www.kaggle.com/datasets/teamincribo/cyber-security-attacks) |

---

## 📊 Project Structure

```
Network-Security/
├── README.md
├── Preprocessing/
├── Bivariate Analysis/
├── Multivariate Analysis/
├── Models/
```

---

## 🔄 Workflow Overview

### 1. **Preprocessing**
- Removed duplicates, null values
- Imputed missing data using `SimpleImputer`
- Encoded categorical features (`get_dummies`, `LabelEncoder`)
- Scaled numeric features with `StandardScaler`
- Exported cleaned data for modeling

### 2. **Bivariate Analysis**
- Explored relationships between pairs of variables using visualizations:
  - Barplots of severity vs. attack type
  - Swarm and violin plots to show revenue/severity by category
  - Chi-Square and ANOVA tests for categorical relevance

### 3. **Multivariate Analysis**
- Encoded and standardized all features
- Applied **PCA** to all datasets:
  - **BETH**: Top 11 components explained ~78% of variance
  - **UNSW_NB15**: Top 30 components explained ~83% variance
  - **NetworkSecurity**: 16 components explained ~75% variance
- Visualized principal components and variance explained

### 4. **Modeling**
- Algorithms used: `RandomForestClassifier`, `LogisticRegression`
- Validation: train/test split + `cross_val_score`
- Metric evaluation:
  - **Accuracy** ~85–92% across datasets
  - **Precision/Recall** evaluated via `classification_report`
  - **Confusion matrix** visualized

---

## 📊 Key Visual Insights

- **Violin plots** showed clear separation between attack types and severity levels.
- **Swarm plots** highlighted clustering in protocol types, especially in DoS and reconnaissance patterns.
- **PCA Variance plots** revealed that a small number of components retained most signal (~75–83%), validating dimensionality reduction.
- **Confusion matrices** indicated high recall for major attack types, but some confusion between normal and low-severity intrusions.

---

## 📈 Highlight Metrics

| Dataset         | Accuracy | PCA Variance (Top N Components) | Notable Finding |
|----------------|----------|----------------------------------|------------------|
| **BETH**          | ~89%     | ~78% (11 components)             | Attack Type highly predictive of Severity |
| **UNSW_NB15**     | ~92%     | ~83% (30 components)             | Balanced precision/recall on multiple attack categories |
| **NetworkSecurity** | ~85%     | ~75% (16 components)             | Action Taken + Protocol = strong indicators |

---

## 🧠 Skills Demonstrated

- Feature engineering and preprocessing
- Multivariate statistical analysis
- PCA-based dimensionality reduction
- Supervised classification (Random Forest, Logistic Regression)
- Visual storytelling and exploratory analysis
- End-to-end ML pipeline with real-world cybersecurity data

---

## 🚀 How to Run

```bash
# Step 1: Clone repo and install dependencies
pip install -r requirements.txt

# Step 2: Run preprocessing notebooks in /Preprocessing
# Then follow analysis notebooks in order: Bivariate → Multivariate → Models
```

---

## 🛠️ Dependencies

Add to `requirements.txt`:

```
pandas
numpy
matplotlib
seaborn
scikit-learn
kagglehub
```

---

## 📌 Future Work

- Automate pipeline with Scikit-learn `Pipeline`
- Try deep learning models (e.g., LSTM on time-series logs)
- Add SHAP or feature importance visualizations
- Test anomaly detection models for zero-day attack prediction

---

## 👩‍💻 Author

**Priya Verma** — M.S. Data Science Candidate  
This project was created to explore and model cybersecurity datasets using real-world ML pipelines.

