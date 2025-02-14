# 📊 Credit Card Approval - Machine Learning Project

## Overview
This project focuses on **automating the classification of credit scores** for a **global finance company**. The company currently relies on **manual credit score assessments**, which are **time-consuming and error-prone**. By leveraging **machine learning**, we aim to improve **accuracy and efficiency**, reducing **manual effort** while ensuring **consistent and reliable** results.

---

## 📌 Objective
The goal is to **develop a machine learning model** that classifies individuals into **credit score brackets** (Good, Standard, or Poor) based on their financial information. To achieve this, we:
1. **Analyze the dataset** to uncover key patterns.
2. **Preprocess and clean the data** to ensure high model performance.
3. **Train and evaluate machine learning models**, including:
   - ✅ **Random Forest**
   - ✅ **XGBoost**
   - ✅ **Logistic Regression**
4. **Interpret model results using LIME** to improve explainability.
5. **Create a robust prediction pipeline** for real-world usage.

---

## 📂 Dataset Description
The dataset consists of **15,000 records and 28 columns**, providing detailed **financial and behavioral information** of individuals.

### **Key Features:**
- **Income & Salary:**
  - `Annual_Income`
  - `Monthly_inhand_salary`
- **Payment Behavior:**
  - `Delay_from_due_date`
  - `Num_of_delayed_payment`
  - `Payment_of_Min_Amount`
- **Demographics:**
  - `Name`
  - `Age`
  - `SSN`
  - `Occupation`
- **Banking & Credit Information:**
  - `Num_Bank_Accounts`
  - `Num_Credit_Card`
  - `Interest_Rate`
  - `Num_of_Loan`
  - `Type_of_loan`
- **Credit Behavior:**
  - `Changed_Credit_Limit`
  - `Num_Credit_Inquiries`
  - `Credit_Mix`
  - `Outstanding_Debt`
  - `Credit_Utilization_Ratio`
  - `Credit_History_Age`
- **Investments & Financial Planning:**
  - `Total_EMI_per_month`
  - `Amount_invested_monthly`
- **Target Variable:**
  - `Credit_Score` (Good, Standard, Poor)

---

## 📊 Exploratory Data Analysis (EDA)
To improve the dataset quality:
- **Incorrect data types** were corrected.
- **Null values** were handled.
- **Outliers and missing entries** were identified and replaced with appropriate values.
- **Text data** was cleaned and encoded into numerical format.
- **Feature engineering** was applied to extract more meaningful insights.

#### **Key Insights from EDA**
- **Users with good credit scores tend to:**
  - Be **older**.
  - Have **fewer** bank accounts.
  - Have **less outstanding debt**.
  - Have **longer** credit history age.
  - **Pay on time** and invest slightly more.

- **Users with poor credit scores tend to:**
  - Be **younger**.
  - Have **higher outstanding debt**.
  - Have **shorter credit history**.
  - **Miss payments** frequently.
  - Have **higher interest rates**.

---

## 🔧 Data Preprocessing
The dataset was **transformed** for better machine learning model performance:
1. **Feature Separation:**  
   - Splitting into **X (features)** and **y (target variable)**.
2. **Handling Categorical & Numerical Data:**  
   - **Categorical** features → **One-Hot Encoding**.  
   - **Numerical** features → **Standardization** with `StandardScaler`.
3. **Preprocessing Pipeline:**  
   - Used `ColumnTransformer` to ensure **consistent data processing**.

---

## 🤖 Model Training & Evaluation
We trained and compared the following models:

| Model             | Accuracy  | F1-Score (Weighted Avg) |
|------------------|-----------|-------------------------|
| **Random Forest** | **80.5%** | **81.0%** |
| **Logistic Regression** | 67.6% | 68.0% |
| **XGBoost** | 73.5% | 74.0% |

### **Hyperparameter Tuning (Grid Search)**
Each model was optimized for **maximum performance**:
- **Random Forest:** `n_estimators` (50, 100), `criterion` (gini, entropy)
- **Logistic Regression:** `solver` (lbfgs, liblinear), `C` (regularization strength)
- **XGBoost:** `n_estimators` (50, 100), `learning_rate` (0.01, 0.1), `max_depth` (3, 5)

### **Key Insights**
- **Random Forest** outperformed the other models in terms of **accuracy and F1-score**.
- **Logistic Regression** struggled with convergence but improved after tuning.
- **XGBoost** showed strong potential and could be improved with further tuning.

---

## 🔍 Feature Importance
The most **important features** affecting credit score classification were:
1. **Outstanding Debt** (11%)
2. **Interest Rate** (8.2%)
3. **Credit History Age** (7.3%)
4. **Changed Credit Limit** (6.4%)
5. **Delay from Due Date** (6.5%)
6. **Amount Invested Monthly** (5.6%)
7. **Credit Inquiries** (5.7%)

🔹 **Credit behavior has the most significant impact on credit scores!**  
🔹 **Higher outstanding debt and delayed payments reduce credit score.**  
🔹 **Longer credit history and consistent investments improve credit score.**  

---

## 📌 Model Interpretability with LIME
To ensure transparency, we used **LIME (Local Interpretable Model-agnostic Explanations)**:
- Helped explain individual predictions.
- Identified key features contributing to each classification.
- Confirmed that **Credit_History_Age, Num_Bank_Accounts, and Credit_Utilization_Ratio** had the highest influence.

---

## 🏆 Best Model & Prediction Pipeline
- **Random Forest** was selected as the **best-performing model**.
- The final prediction pipeline can classify new individuals into **Good, Standard, or Poor** credit score categories.

---

## 🔮 Future Improvements
To further enhance the model:
1. **Fine-tune hyperparameters** for XGBoost.
2. **Expand LIME analysis** for batch-level explanations.
3. **Combine models using ensemble techniques** for higher accuracy.

---

## 🚀 How to Use
1. **Clone this repository:**
   ```sh
   git clone https://github.com/<your-username>/credit-card-approval.git
   cd credit-card-approval
