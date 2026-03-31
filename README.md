# Predicting Customer Attrition Using Machine Learning

## Project Overview
Predicting Customer Attrition Using Machine Learning: A Case Study of ABC Corporation

Customer attrition, or churn, is a critical issue for ABC Corporation. Retaining customers is more cost-effective than acquiring new ones, making it essential to predict and address churn proactively. This project develops a machine learning pipeline designed to predict customer attrition using behavioral, demographic, and credit-related data.

The dataset contains information from 10,127 customers and includes 21 features related to demographics, transaction behavior, and credit usage. The target variable, `Attrition_Flag`, identifies customers as either “Attrited” or “Existing.”

---

## Objective
The goal of this project is to uncover predictive patterns in customer behavior and support targeted retention strategies through machine learning models.

---

## Dataset Description
The dataset includes both numerical and categorical variables.

### Key Feature Types

**Numerical Features**
- Customer_Age  
- Credit_Limit  
- Total_Trans_Amt  
- Total_Revolving_Bal  
- Avg_Open_To_Buy  

**Categorical Features**
- Gender  
- Income_Category  
- Card_Category  
- Marital_Status  
- Education_Level  

**Target Variable**
- Attrition_Flag (Attrited / Existing)

---

## Data Cleaning and Feature Engineering

### Missing Data Handling
- Missing values in `Income_Category` were replaced with “Unknown”
- Records with missing `Attrition_Flag` were removed
- Final dataset confirmed to have no missing values

### Feature Engineering
Two new features were created:

- **Total_Utilization** = Total_Revolving_Bal / Credit_Limit  
- **Spending_Frequency** = Total_Trans_Amt / Total_Trans_Ct  

These features capture customer credit usage behavior and spending patterns.

---

## Data Preprocessing

### Outlier Removal (IQR Method)
Outliers in variables such as `Customer_Age` and `Total_Trans_Amt` were removed using the Interquartile Range method to reduce noise and improve model stability.

### Log Transformation
- `Credit_Limit` was log-transformed to reduce skewness.

### Feature Scaling
- Numerical features were standardized (mean = 0, standard deviation = 1).

### One-Hot Encoding
- Categorical variables were converted into numerical format using one-hot encoding.

---

## Exploratory Data Analysis
Correlation analysis was performed to examine relationships between numerical variables and identify redundancy among features.

---

## Models Used

The following models were evaluated:

- Logistic Regression (baseline model)
- Decision Tree
- Tuned Decision Tree
- Random Forest
- Tuned Random Forest

---

## Model Performance Summary

### Logistic Regression
- Accuracy: 8.78%  
- Very low predictive performance  
- Failed to outperform baseline classification  

---

### Decision Tree
- Accuracy: 93.4%  
- Sensitivity: 79.63%  
- Specificity: 95.93%  
- Kappa: 0.75  

---

### Tuned Decision Tree
- Accuracy: 94.01%  
- Sensitivity: 79.37%  
- Specificity: 96.70%  
- Kappa: 0.7689  
- Balanced Accuracy: 88.03%  

---

### Random Forest
- Accuracy: 95.75%  
- Sensitivity: 82.77%  
- Specificity: 98.13%  
- Kappa: 0.833  
- Balanced Accuracy: 90.45%  

---

### Tuned Random Forest
- Accuracy: 95.87%  
- Sensitivity: 83.55%  
- Specificity: 98.13%  
- Kappa: 0.8383  
- Balanced Accuracy: 90.84%  

---

## ROC Analysis
ROC curves showed that both Random Forest and Decision Tree models outperform Logistic Regression in distinguishing between churned and retained customers.

Random Forest achieved the strongest overall AUC performance, followed closely by the tuned Decision Tree.

---

## Feature Importance (Random Forest)

Top predictive features:
- Total_Trans_Amt  
- Total_Trans_Ct  
- Total_Ct_Chng_Q4_Q1  
- Total_Revolving_Bal  
- Spending_Frequency  
- Total_Relationship_Count  
- Total_Amt_Chng_Q4_Q1  
- Total_Utilization  
- Avg_Utilization_Ratio  
- Customer_Age  

---

## Final Model Recommendation
The **Random Forest model (untuned)** achieved the highest overall performance.

However, the **tuned Decision Tree** is recommended for deployment due to its balance of:
- Strong predictive performance  
- Interpretability  
- Ease of communication with stakeholders  

---

## Business Recommendations

### 1. High Credit Utilization Customers
Target customers with high utilization using financial support tools, credit limit adjustments, and personalized outreach.

### 2. Low Relationship Count Customers
Encourage cross-selling and loyalty programs to increase engagement and reduce churn risk.

### 3. Low Credit Limit with High Usage
Provide credit limit reviews and personalized financial support to reduce financial strain and improve retention.

---

## Deployment Approach

The tuned Decision Tree model can be deployed in:

- Batch prediction systems (monthly churn scoring)
- Real-time CRM systems for immediate intervention

---

## Future Improvements

### Data Enhancements
- Customer sentiment data  
- Service interaction history  
- Customer satisfaction surveys  

### Modeling Improvements
- Neural networks for complex patterns  
- Time-series models (LSTM) for behavior tracking  

### Class Imbalance Handling
- Class weighting  
- Oversampling / undersampling techniques  

### Monitoring
- Regular model retraining  
- Continuous performance tracking  

---

## Conclusion
This project demonstrates the effectiveness of machine learning models in predicting customer attrition. While ensemble methods achieved the highest predictive performance, interpretable models provide practical value for business deployment and decision-making.


---

## Author
Ross Schanck  
M.S. Data Science
