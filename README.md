![Home Credit Risk](https://github.com/user-attachments/assets/b3942190-0798-4e15-a025-7296ab5baa69)

## Home Credit Risk Prediction - Machine Learning Project

### 📌 Project Overview
This project focuses on predicting loan default risk using machine learning techniques. Financial institutions need accurate models to assess credit risk and minimize losses due to loan defaults. We built and evaluated multiple models—including Logistic Regression, Random Forest, and XGBoost—to determine the best-performing model for predicting loan status.

### 🚀 Goal:<br> 
Develop a robust classification model that helps lenders decide whether to approve or reject loan applications based on risk assessment.

### ⚡ Challenges Faced
Imbalanced Dataset:<br>

The dataset had 78% non-default (0) and 22% default (1) cases. This imbalance could lead models to favor predicting non-defaulters, hurting recall.<br>
Feature Selection & Engineering:<br>

Some features were highly correlated, while others had little impact on predictions. Determining which features to retain was critical.<br>
Outlier Handling & Scaling:<br>

The dataset contained outliers, requiring careful handling using IQR, Winsorization, and Log Transformations.<br>
Features had different ranges, necessitating Standardization for normally distributed features and Normalization for skewed features.<br>
Model Selection & Evaluation:<br>

While Logistic Regression was a strong baseline, it underperformed compared to tree-based models.<br>
Choosing the best model required analyzing AUC-ROC, Precision, Recall, and F1-score rather than just accuracy.<br>
### 🔬 Step-by-Step Approach<br>
### 🟢 Step 1: Data Preparation<br>
Loaded & explored the dataset to understand its structure.<br>
Handled missing values using median imputation (for skewed distributions).<br>
Checked for duplicates and removed 165 duplicate rows.<br>
### 🟢 Step 2: Feature Engineering & Selection
Identified numerical and categorical features.<br>
Encoded categorical variables:<br>
Used Label Encoding for Ordinal variables (loan_grade).<br>
Used One-Hot Encoding for Nominal features (loan_intent, home_ownership).<br>
Dropped least important feature (cb_person_cred_hist_length) based on feature importance analysis.<br>
### 🟢 Step 3: Handling Outliers & Scaling
Applied IQR, Log Transformations, and Winsorization to handle outliers.<br>
Used Standardization (Z-score) for normally distributed features.<br>
Used Min-Max Normalization for skewed distributions.<br>
### 🟢 Step 4: Addressing Class Imbalance
Detected class imbalance (78%-22%) and applied SMOTE oversampling to balance the dataset.<br>
Ensured the training set had a more balanced distribution to improve model learning.<br>
### 🟢 Step 5: Model Training & Evaluation
Trained three models:<br>
✅ Logistic Regression (Baseline)<br>
✅ Random Forest<br>
✅ XGBoost (Best Model)<br>

Evaluated models based on:<br>

AUC-ROC (Most important metric)<br>
Precision (To avoid rejecting too many good customers)<br>
Recall (To avoid missing risky borrowers)<br>
F1-Score (Balance between Precision & Recall)<br>
### 📊 Results: Model Performance Comparison

####🔹 Logistic Regression:<br>
Accuracy: 79.04%<br>
Precision: 51.17%<br>
Recall: 77.52% (Highest Recall)<br>
F1 Score: 61.65%<br>
AUC-ROC: 86.56%<br>

#### 🔹 Random Forest:<br>
Accuracy: 92.78%<br>
Precision: 91.43%<br>
Recall: 73.68%<br>
F1 Score: 81.60%<br>
AUC-ROC: 93.19%<br>

#### 🔹XGBoost (Best Model):<br>
Accuracy: 93.18% (Highest)<br>
Precision: 93.90% (Highest)<br>
Recall: 73.39%<br>
F1 Score: 82.39% (Highest)<br>
AUC-ROC: 94.31% (Highest - Best at distinguishing default risk)<br>

### 🚀 Final Decision: XGBoost is the best model based on:<br>
✅ Highest Accuracy (93.18%)<br>
✅ Highest AUC-ROC (94.31%) → Best at distinguishing defaulters from non-defaulters.<br>
✅ Highest Precision (93.90%) → Reduces false positives, ensuring good borrowers aren’t wrongly classified as risky.<br>
✅ Balanced Recall (73.39%) → Identifies a significant portion of risky borrowers.<br>

### 🚀 Future Improvements & Recommendations

💡 1. Hyperparameter Tuning:<br>
Use Grid Search or Bayesian Optimization to fine-tune XGBoost parameters for even better performance.<br>

💡 2. Model Explainability (SHAP Analysis):<br>
Implement SHAP (SHapley Additive Explanations) to interpret how each feature affects loan decisions.<br>

💡 3. Deploy Model as an API:<br>
Use Flask or FastAPI to deploy the model and make real-time predictions.<br>
Alternatively, use Streamlit to create an interactive web dashboard for lenders.<br>

💡 4. Feature Engineering Enhancements:<br>
Include additional external credit bureau data or borrower behavioral insights.<br>
Engineer new features such as debt-to-income ratio trends over time.<br>
