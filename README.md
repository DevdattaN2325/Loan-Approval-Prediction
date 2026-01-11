## LOAN_APPROVAL_PREDICTION
This repository contains a machine learning project designed to automate the loan eligibility process. The model predicts whether a loan application will be approved based on several customer attributes provided during the application process.

## Key Performance Values
## Logistic Regression (Baseline Model)
Accuracy: ~85%.
Recall (Approved Loans): 98%.
ROC-AUC: ~0.80.

## Business Impact: This model ensures that almost all eligible applicants are approved, minimizing the rejection of qualified customers.

## Random Forest (Advanced Model)
Risk Detection: Enhanced ability to capture non-linear patterns in borrower behavior.
Recall (Rejected Loans): Higher performance in identifying high-risk or ineligible loans compared to the baseline.
Balance: Provides a more robust trade-off between loan approval volume and risk mitigation.

## Understanding the Model & Pipeline
1. Data Preprocessing
To ensure the model receives clean data, the following steps are implemented:
Imputation: Missing values are handled using SimpleImputer.
Encoding: Categorical variables (e.g., Gender, Education, Property Area) are transformed using OneHotEncoder.
Scaling: Numerical features are normalized using StandardScaler.

2. Addressing Class Imbalance
The dataset contains more approved loans than rejected ones. To prevent the model from becoming biased toward the majority class (approvals), SMOTE (Synthetic Minority Over-sampling Technique) is applied during training. This 
improves the recall for rejected loans, making the model better at identifying financial risk.

3. Strategic Business Logic
The model is designed to support two different business strategies:
Growth Strategy: Focuses on high recall for approvals (Logistic Regression) to maximize customer acquisition.
Risk-Averse Strategy: Focuses on capturing non-linear risk patterns (Random Forest) to prevent defaults in volatile economic conditions.