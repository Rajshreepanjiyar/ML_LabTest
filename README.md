#  Loan Default Prediction – FinSecure

##  Overview
This project was developed as part of FinSecure’s initiative to build a **data-driven system** that predicts whether a borrower will **repay or default** on a loan.  
Accurate prediction of loan defaults helps FinSecure:
- Reduce financial risk for investors
- Improve lending decisions
- Enhance customer trust and operational efficiency

The project uses **machine learning** to analyze borrower information and predict the probability of loan repayment.

---

##  Objective
To build a predictive model that estimates the **probability of a loan being paid back** (`loan_paid_back = 1`)  
and to maximize the **Area Under the ROC Curve (AUC)** for better discrimination between repayers and defaulters.

Additionally, the model’s fairness was evaluated across:
- **Education levels**  
- **Loan purposes**

---

##  Project Structure

### **Section 1: Problem Formulation & Target Variable Analysis**
- Defined “loan default” and analyzed the target variable `loan_paid_back`.
- Performed Exploratory Data Analysis (EDA) to understand key predictors like:
  - `credit_score`, `annual_income`, `debt_to_income_ratio`, `loan_amount`, and `interest_rate`.
- Observed strong correlation between **credit score** and **loan repayment behavior**.

### **Section 2: Feature Engineering & Preprocessing Pipeline**
- Dropped non-predictive columns (`id`).
- Handled missing values using **median/mode imputation**.
- Encoded categorical features (`education_level`, `loan_purpose`, etc.) using **One-Hot Encoding**.
- Scaled numeric features using **StandardScaler**.
- Split dataset into **80% training** and **20% testing** sets with stratification.
- Built a unified **preprocessing pipeline** using `ColumnTransformer` and `Pipeline`.

### **Section 3: Model Development and Tuning**
- Trained a **Logistic Regression** model to predict the probability of loan repayment.
- Achieved **AUC = 0.9119**, indicating excellent model performance.
- Plotted the **ROC Curve**, showing strong separation between repayers and defaulters.
- Generated probability predictions for each test sample.

### **Section 4: Subgroup Fairness Analysis**
- Evaluated AUC across different **education levels** and **loan purposes** to ensure model fairness.

| Education Level | AUC |
|------------------|-----|
| Other | 0.9126 |
| High School | 0.9105 |
| Bachelor’s | 0.9098 |
| Master’s | 0.9075 |
| PhD | 0.9056 |

| Loan Purpose | AUC |
|---------------|-----|
| Vacation | 0.9169 |
| Debt Consolidation | 0.9105 |
| Medical | 0.9103 |
| Car | 0.9080 |
| Business | 0.9074 |
| Home | 0.9058 |

The small variation (< 0.01) across groups confirms **model fairness and stability**.

---

##  Tech Stack
- **Language:** Python  
- **Libraries:** pandas, numpy, scikit-learn, matplotlib, seaborn, xgboost  
- **Environment:** Jupyter Notebook  
- **Version Control:** Git + GitHub  

---

##  Results Summary
| Metric | Value |
|---------|--------|
| Model | Logistic Regression |
| AUC | **0.9119** |
| ROC Curve | High performance, smooth curve |
| Fairness | Consistent AUC across all subgroups |

---

##  Key Insights
- Borrowers with **higher credit scores**, **lower debt-to-income ratios**, and **moderate interest rates** are more likely to repay loans.  
- The model performs **fairly across different education levels and loan purposes**.  
- Logistic Regression provided strong performance with high interpretability — making it ideal for financial decision support systems.

---

##  Author
**[Raj Shree]**  


