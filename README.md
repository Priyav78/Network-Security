
# 🛡️ Network Security - Cyberattack Detection via Machine Learning

This project analyzes and models network security data to detect cyberattacks using machine learning. It is structured around three distinct cybersecurity datasets and takes a modular approach through preprocessing, exploratory data analysis, and classification modeling.

---

## 📁 Datasets Used

| Dataset           | Description                                                                 | Source |
|------------------|-----------------------------------------------------------------------------|--------|
| **BETH**          | Synthetic cybersecurity dataset with labeled threat features                | Internal or academic (e.g., synthetic) |
| **UNSW_NB15**     | Realistic dataset from IXIA's Lab – includes exploits, DoS, reconnaissance  | [UNSW NB15 Kaggle](https://www.kaggle.com/datasets/mrwellsdavid/unsw-nb15) |
| **NetworkSecurity** | Custom/combined dataset with labeled network event logs                     | User-provided |

Each dataset contains a mix of categorical, boolean, and continuous features, often with missing data or redundancy, requiring significant preprocessing.

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
- Removed duplicates and nulls
- Encoded categorical features using `get_dummies` or `LabelEncoder`
- Applied `StandardScaler` for numeric standardization
- Saved clean data versions (recommend `.csv`)

### 2. **Bivariate Analysis**
- Explored relationships between pairs of variables (e.g., Attack Type vs. Severity)
- Visualized distributions using boxplots, barplots, and swarm plots

### 3. **Multivariate Analysis**
- One-hot encoded or label-encoded all non-numeric columns
- Applied PCA (Principal Component Analysis) to reduce dimensionality
- Identified most significant components for model input
- Standardized features before applying PCA

### 4. **Modeling**
- Used **Logistic Regression** and **Random Forest**
- Evaluation metrics: Accuracy, Confusion Matrix, Classification Report
- Applied cross-validation and hyperparameter tuning (`GridSearchCV`/`RandomizedSearchCV`)

---

## 🔍 Key Findings

- PCA reduced dimensionality with up to **70–80% variance explained** by fewer than 15 components.
- Random Forest performed consistently well, especially on high-dimensional data.
- BETH and UNSW showed different threat profiles, requiring tailored preprocessing pipelines.

---

## 🧠 Skills Demonstrated

- **Data wrangling**: feature selection, null handling, encoding
- **Visualization**: seaborn/matplotlib for EDA and PCA interpretation
- **Modeling**: logistic regression, ensemble trees, pipeline thinking
- **Dimensionality reduction**: PCA with `StandardScaler`
- **Real-world domain alignment**: network security logs, threat severity, IP/Port handling

---

## 🚀 How to Run

```bash
# Step 1: Clone repo and install dependencies
pip install -r requirements.txt

# Step 2: Open notebooks in each folder
# Start with: Preprocessing/UNSW_NB15.ipynb

# Step 3: Run EDA and modeling notebooks in order
```

---

## 🛠️ Dependencies

Add these to a `requirements.txt`:

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

- Automate pipeline using Scikit-learn `Pipeline` or `ColumnTransformer`
- Train ensemble models with cross-dataset validation
- Use deep learning on unstructured payloads (if available)

---

## 👩‍💻 Author

**Priya Verma** — M.S. Data Science Candidate  
This project was created as part of a security-focused machine learning portfolio.

