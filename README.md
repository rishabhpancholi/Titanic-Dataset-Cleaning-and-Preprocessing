# Titanic-Dataset-Cleaning-and-Preprocessing

This repository contains the preprocessing pipeline for the Titanic dataset. The goal was to clean and prepare the data for machine learning models by handling missing values, outliers, categorical encoding, and feature scaling.

---

## 📌 Steps Performed

### 1. **Data Inspection**
- Loaded the Titanic dataset.
- Separated the features into:
  - **Categorical columns**: e.g., `Sex`, `Embarked`
  - **Numerical columns**: e.g., `Age`, `Fare`, `Pclass`, etc.
- Checked for:
  - Missing values
  - Duplicated records

---

### 2. **Train-Test Split**
- Separated the features (`X`) and target (`y`).
- Split the dataset into training and testing sets using an 70-30 split.

---

### 3. **Data Cleaning & Imputation**
- Dropped unnecessary or irrelevant columns.
- Imputed missing values:
  - **`Age`**: Imputed using **K-Nearest Neighbors (KNN)**.
  - **`Embarked`**: Imputed using **Mode imputation** (most frequent value).

---

### 4. **Outlier Removal**
- Used the **IQR (Interquartile Range)** method to detect and remove outliers.
- Calculated IQR bounds **on the training set** and removed outliers from both training and testing data based on these bounds (to prevent data leakage).

---

### 5. **Encoding and Scaling**
- Used **`ColumnTransformer`** to handle preprocessing in a pipeline:
  - **One-Hot Encoding** for categorical columns (`drop='first'` to avoid dummy variable trap).
  - **StandardScaler** for numerical columns.

---

### 6. **DataFrame Conversion**
- Converted the transformed NumPy arrays (`X_train_encoded` and `X_test_encoded`) back into pandas DataFrames:
  - Preserved meaningful column names after transformation.
  - Ensured clean, labeled data for modeling.

---

## ✅ Final Output
- `X_train_df`: Preprocessed training features as a DataFrame.
- `X_test_df`: Preprocessed testing features as a DataFrame.

These datasets are now ready to be used in modeling pipelines for classification or survival prediction.

---

## 🚀 Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn

---
