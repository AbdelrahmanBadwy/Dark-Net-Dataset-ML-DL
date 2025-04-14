# 🔐 Network Traffic Classification using Machine Learning and Deep Learning 

## 📘 Overview

This project focuses on **network traffic classification** using machine learning. It leverages the **Darknet dataset**, a rich source of network traffic metadata labeled by traffic type (e.g., VPN, Tor) and application type (e.g., P2P, Streaming, Chat). The notebook covers **data preprocessing, feature engineering, class balancing, model training**, and **evaluation** using various classification algorithms.

## 📁 Dataset

- **Source**: Google Drive shared file ([Darknet.csv](https://drive.google.com/file/d/1xiKff5CXwZ74iKbMcoFk5I_9QCQn_-OY/view))
- **Size**: ~73MB
- **Shape**: 158,616 rows × 85 columns
- **Targets**:
  - `traffic`: {VPN, NonVPN, Tor, Non-Tor}
  - `application`: {Browsing, Email, Chat, File Transfer, etc.}

## 🛠️ Key Steps

### 1. Data Cleaning & Preprocessing
- Removed missing and infinite values
- Removed duplicates
- Encoded categorical variables
- Converted IP addresses to numeric format
- Final cleaned shape: **119,562 rows × 85 features**

### 2. Exploratory Data Analysis
- Visualized distributions of `traffic` and `application` labels
- Identified severe class imbalance
- Generated interactive reports using **Sweetviz**

### 3. Label Encoding
- `traffic` and `application` classes converted to numeric
- Created label maps for interpretability

### 4. Feature Engineering
- Dropped constant and highly correlated features using feature importance
- Final feature count after selection: **41**

### 5. Data Balancing
Used **SMOTE** and **ADASYN** to address imbalance:
- Resampled to 30,000 samples per class for applications
- Saved balanced datasets to CSV

### 6. Model Training & Evaluation
Five classifiers were trained and evaluated:
- ✅ **Random Forest**
- ✅ **XGBoost**
- ✅ **LightGBM**
- ✅ **K-Nearest Neighbors (KNN)**
- ❌ Linear Discriminant Analysis (LDA) underperformed

Metrics reported:
- Accuracy
- F1 Score
- Precision
- Recall
- Confusion Matrix

#### 📊 Best Model
**XGBoost with SMOTE**
- Accuracy: **0.92**
- F1-score: **0.89**
- Precision: **0.87**
- Recall: **0.89**

## 📈 Feature Selection
- Removed uninformative features
- Reduced multicollinearity using correlation and feature importance
- Accuracy improved marginally after selection

## 📦 Output Files
- `cleaned_data.csv`: Cleaned raw dataset
- `train_data.csv`, `test_data.csv`: Pre-split sets
- `balancedAppDarknet.csv`: Balanced dataset via SMOTE
- Classification reports and confusion matrices for each model

## 🧠 Future Work
- Explore **GANs** and **VAEs** for synthetic data generation
- Apply **real-time intrusion detection** techniques
- Implement **model interpretability** with SHAP or LIME

---

## 🚀 Usage

### Clone & Run

```bash
git clone <repo_url>
cd network-traffic-classification
pip install -r requirements.txt
jupyter notebook Network_Security_Project.ipynb
```

### Requirements

- Python 3.10+
- scikit-learn
- xgboost
- lightgbm
- imbalanced-learn
- sweetviz
- matplotlib, seaborn

---

## 📬 Contact

For questions or collaboration opportunities, feel free to reach out via ([email](abdelrahmanelbadawy9@gmail.com)).
