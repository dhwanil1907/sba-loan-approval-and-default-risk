SBA Loan Approval Analysis & Prediction
Team: Dhwanil Ranpura and Santhosh Ravindrabharathy

📚 Project Overview
This project analyzes historical SBA loan data (1987–2014) and predicts whether a loan will be Paid In Full (PIF) or Charged-Off (ChgOff).
The goal is to help banks and the SBA better assess borrower risk, improve loan approval processes, and ultimately enhance small business credit efficiency.

🛠️ Workflow Summary
Data Cleaning:

Removed duplicates

Handled missing values

Corrected data types and addressed outliers

Dropped irrelevant/leaky features (e.g., ChgOffDate, LoanNr_ChkDgt)

Feature Engineering:

One-hot encoding of categorical features

Created new features (IsFranchise, SameState, Industry)

Standardized loan amount columns

Exploratory Data Analysis (EDA):

Identified patterns between loan performance and variables like loan term, SBA guarantee amount, and franchise status

Discovered key insights:

Higher SBA guarantees → Lower default probability

Borrower and Bank in same state → Lower risk

Franchise businesses → More likely to repay loans

Modeling Approaches:
Trained and compared multiple machine learning models:

Logistic Regression (with and without class balancing)

Random Forest Classifier

k-Nearest Neighbors (kNN)

Decision Tree

Neural Network (TensorFlow/Keras)

Model Evaluation:

Metrics: Accuracy, Precision, Recall, F1-Score, ROC-AUC

Addressed class imbalance using class weights and feature selection

Top performance: Random Forest (93% accuracy, ROC-AUC 0.97)

🧩 Dataset Details
Source: U.S. Small Business Administration (SBA)

Records: 899,164 loans

Features: 27 columns → Reduced to 17 relevant features

Target Variable: MIS_Status (Paid In Full vs Charged-Off)

Key Features after cleaning:

Business details (State, NAICS, NewExist, NoEmp, IsFranchise)

Loan details (DisbursementGross, Term, LowDoc, RevLineCr)

Bank information (BankState, SameState)

📊 Key Findings
Longer loan terms and higher disbursement amounts increase repayment likelihood.

Loans where borrower and bank are in different states have higher default rates.

Franchise businesses tend to have stronger repayment performance.

Higher SBA-guaranteed loan amounts correlate with lower loan defaults.

🔥 Results

Model	Accuracy	Precision (Charged Off)	Recall (Charged Off)	ROC-AUC
Logistic Regression	91%	Moderate	Moderate	84.4%
Random Forest	93%	84%	77%	97%
k-Nearest Neighbors	91%	80%	67%	85%
Neural Networks	91%	79%	70%	86%
Decision Tree	91%	75%	75%	85%
📦 Tech Stack
Python (Pandas, NumPy, scikit-learn, TensorFlow/Keras)

Matplotlib, Seaborn (for visualization)

Machine Learning techniques (classification, feature selection, balancing)

🚀 Future Improvements
Perform hyperparameter tuning for Random Forest and Neural Network models

Apply resampling techniques like SMOTE for better minority class handling

Explore ensemble learning methods (e.g., XGBoost, LightGBM)

Incorporate economic indicators for enhanced prediction accuracy

📎 References
U.S. Small Business Administration (SBA) Loan Data

scikit-learn documentation

TensorFlow/Keras documentation
