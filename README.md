# SBA Loan Approval Analysis & Prediction

> **Team:** Dhwanil Ranpura and Santhosh Ravindrabharathy

## 📚 Project Overview
This project analyzes historical SBA loan data (1987–2014) and predicts whether a loan will be **Paid In Full (PIF)** or **Charged-Off (ChgOff)**.  
The goal is to help banks and the SBA better assess borrower risk, improve loan approval processes, and enhance small business credit efficiency.

---

## 🛠️ Workflow Summary

- **Data Cleaning:**
  - Removed duplicates
  - Handled missing values
  - Corrected data types and addressed outliers
  - Dropped irrelevant or leaky features (e.g., `ChgOffDate`, `LoanNr_ChkDgt`)

- **Feature Engineering:**
  - One-hot encoded categorical features
  - Created new features (`IsFranchise`, `SameState`, `Industry`)
  - Standardized monetary values

- **Exploratory Data Analysis (EDA):**
  - Analyzed relationships between loan terms, SBA guarantees, and repayment behavior
  - Key findings:
    - Higher SBA guarantee → Lower default risk
    - Same-state borrower-bank pairs → Higher repayment likelihood
    - Franchise businesses → Higher loan repayment rates

- **Modeling:**
  - Trained and evaluated:
    - Logistic Regression
    - Random Forest Classifier
    - k-Nearest Neighbors (kNN)
    - Decision Tree Classifier
    - Neural Network (TensorFlow/Keras)

- **Evaluation:**
  - Metrics used: Accuracy, Precision, Recall, F1-Score, ROC-AUC
  - Addressed class imbalance using class weights and feature selection
  - Best model: **Random Forest** with 93% accuracy and ROC-AUC 0.97

---

## 🧩 Dataset Details

- **Source:** U.S. Small Business Administration (SBA)
- **Records:** 899,164 loans
- **Features:** 27 columns → Reduced to 17 selected features
- **Target Variable:** `MIS_Status` (`Paid In Full` vs `Charged-Off`)

Key features:
- Business details (`State`, `NAICS`, `NewExist`, `NoEmp`, `IsFranchise`)
- Loan details (`DisbursementGross`, `Term`, `LowDoc`, `RevLineCr`)
- Bank information (`BankState`, `SameState`)

---

## 📊 Key Insights

- Longer-term loans tend to be repaid more often.
- Loans with higher SBA guarantees show lower default rates.
- Borrowers located in the same state as their banks have higher repayment success.
- Franchise businesses are more likely to repay loans in full.

---

## 🔥 Model Results

| Model                | Accuracy | Precision (Charged Off) | Recall (Charged Off) | ROC-AUC |
|----------------------|----------|-------------------------|----------------------|---------|
| Logistic Regression  | 91%      | Moderate                | Moderate             | 84.4%   |
| Random Forest        | 93%      | 84%                     | 77%                  | **97%** |
| k-Nearest Neighbors  | 91%      | 80%                     | 67%                  | 85%     |
| Neural Networks      | 91%      | 79%                     | 70%                  | 86%     |
| Decision Tree        | 91%      | 75%                     | 75%                  | 85%     |

---

## 📦 Tech Stack

- Python (Pandas, NumPy, scikit-learn, TensorFlow/Keras)
- Matplotlib, Seaborn for data visualization
- Machine Learning techniques: Classification, Feature Selection, Class Imbalance Handling

---

## 🚀 Future Work

- Perform hyperparameter tuning on models
- Apply resampling techniques (e.g., SMOTE) for better minority class prediction
- Experiment with advanced ensemble methods like XGBoost or LightGBM
- Integrate macroeconomic factors for improved loan default predictions

---

## 📎 References

- U.S. Small Business Administration (SBA) Loan Data
- [scikit-learn documentation](https://scikit-learn.org/stable/)
- [TensorFlow/Keras documentation](https://www.tensorflow.org/)

---
