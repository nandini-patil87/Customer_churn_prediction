# Telecom Customer Churn Prediction

This machine learning project aims to help a telecom company identify which customers are most likely to churn  and why so they can take action to reduce customer loss.

---

##  What is Churn?

**Customer churn** refers to customers leaving or discontinuing a service. Reducing churn is crucial because acquiring new users is much more expensive than retaining existing ones.

---

## Business Questions Answered

1. What percentage of users have churned?
2. What features are most common among churned customers?
3. Can we predict churn accurately using ML?
4. What business actions can help retain users?

---

## Dataset Summary

- **Rows:** 7043
- **Target column:** `Churn` (Yes/No)
- **Features include:**
  - Demographics (gender, SeniorCitizen, Partner, etc.)
  - Service details (InternetService, StreamingTV, TechSupport)
  - Account info (Contract, PaymentMethod, Tenure, Charges)

**link**-https://www.kaggle.com/datasets/blastchar/telco-customer-churn
---

##  Exploratory Data Analysis (EDA)

- Visualized and studied all categorical & numerical features.
- Identified patterns in churn behavior.
- Found several strong and weak predictors of churn.

### Key Drivers of Churn:
- **High churn risk:**  
  `Month-to-month contracts`, `High Monthly Charges`, `Fiber optic Internet`, `Electronic check`
- **Low churn risk:**  
  `Two-year contracts`, `Dependents`, `Long tenure`, `Automatic payments`

Features like `Gender` and `PhoneService` were found to be **not significant**.

---

##  Preprocessing Steps

- Handled missing values and data types
- Label encoded categorical columns
- Scaled numerical features using `StandardScaler`
- Balanced target classes using `SMOTE`

---

##  Models Used

| Model               | Status              |
|---------------------|---------------------|
| Logistic Regression | Baseline model      |
| Decision Tree       | Simple tree model   |
| Random Forest       | Best performing model |
| XGBoost             | Tuned boosting model |
| GridSearchCV        | Hyperparameter tuning |

---

##  Evaluation Metrics

To evaluate model performance, the following metrics were used:

| Metric        | Explanation                                                                 |
|---------------|-----------------------------------------------------------------------------|
| Accuracy      | Overall correct predictions                                                 |
| Precision     | How many predicted churns were actually churns                              |
| Recall        | Most important — how many actual churns were caught                         |
| F1 Score      | Harmonic mean of precision and recall                                       |
| ROC-AUC       | How well model separates churn vs non-churn                                 |
| Confusion Matrix | Breakdown of TP, TN, FP, FN                                              |
| Cross Validation | Generalization performance across folds                                  |

###  Model Performance Comparison

| Model               | Accuracy | Precision | Recall | F1 Score | AUC    |
|---------------------|----------|-----------|--------|----------|--------|
| Logistic Regression | 72.5%    | 48.9%     | 79.4%  | 60.5%    | 0.83   |
| Decision Tree       | 79.2%    | 65.1%     | 69.8%  | 67.3%    | 0.76   |
| Random Forest       | 85.0%    | 82.2%     | 85.3%  | 83.7%    | 0.91   |
| XGBoost             | 84.1%    | 80.5%     | 83.9%  | 82.2%    | 0.89   |

 **Random Forest performed the best** in terms of overall metrics, especially recall and AUC.

---

##  Final Observations

- Churn is significantly influenced by **contract type**, **tenure**, and **billing method**.
- **Short-term users**, **high payers**, and **manual payers** are at risk.
- Models with proper tuning and preprocessing reached **high performance** (up to 85% accuracy and AUC > 0.90).

---

##  Recommendations

Based on model insights, here are actionable steps for the telecom company:

 **Encourage Long-Term Contracts**  
 Offer discounts for 1 or 2-year contracts to reduce churn.

 **Bundle Services with Discounts**  
  Customers using more services (TV, internet, phone) are less likely to churn.

 **Loyalty Benefits for Dependents/Partners**  
  Promote family plans with incentives for existing users.

 **Offer Perks to Senior Citizens**  
  Provide tech support and streaming perks for older users.

 **Switch to Auto-Pay**  
  Encourage automatic payment methods with small discounts.

 **Target High-Risk Segments Early**  
  Use model output to proactively engage with users showing early churn signals.
