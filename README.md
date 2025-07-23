# Customer Churn Prediction at SyriaTel Telecom

## Project Overview

This project focuses on predicting customer churn for SyriaTel, a telecom provider. By analyzing customer usage patterns and service data, we aim to identify potential churners early and provide business recommendations to improve retention strategies.

---

## Business Problem

**SyriaTel** wants to proactively reduce churn.  
They need a data-driven solution to:

- Predict which customers are likely to leave
- Understand the key factors influencing churn
- Develop targeted retention strategies

---

## Project Objectives

- **Classify** whether a customer will churn using machine learning
- **Improve model performance** via class balancing (SMOTE) and hyperparameter tuning
- **Interpret model outputs** to guide business decisions
- **Recommend churn mitigation strategies**

---

## Dataset

- **Source**: Provided SyriaTel Telecom customer data
- **Records**: 3,333 customers
- **Target Variable**: `churn` (True/False)
- You can find the dataset [here](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset).


### Key Features
- `account_length`, `number_vmail_messages`
- `total_day_minutes`, `total_day_calls`
- `total_eve_minutes`, `total_night_minutes`, `total_intl_minutes`
- `international_plan`, `voice_mail_plan`
- `customer_service_calls`

---

## Modeling Process

### 1. **Data Preprocessing**
- Handled class imbalance using **SMOTE**
- Applied **One-Hot Encoding** to categorical variables

### 2. **Baseline Model**
- Logistic Regression (imbalanced accuracy: 86%)
- Poor recall on churners (26%)

### 3. **Improved Models**
| Model                | Accuracy | Recall (Churn) | F1-Score (Churn) |
|---------------------|----------|----------------|------------------|
| Logistic (Balanced) | 75%      | 71%            | 45%              |
| Decision Tree        | 90%      | 64%            | 66%              |
| **Tuned Decision Tree** | **93%**  | **67%**          | **75%**            |
| Random Forest        | 92%      | 55%            | 67%              |

**Best Model:** Tuned Decision Tree (balanced accuracy, strong churn recall)

---

## Feature Importance Insights

| Rank | Feature                | Business Insight                                                                 |
|------|------------------------|----------------------------------------------------------------------------------|
| 1    | `total_day_minutes`    | High daytime usage may lead to higher bills and churn.                          |
| 2    | `customer_service_calls` | Indicates dissatisfaction — strong churn predictor.                              |
| 3    | `total_eve_minutes`    | High evening usage reveals customer activity trends.                            |
| 4    | `total_day_calls`      | May reflect customer needs not being met.                                       |
| 5    | `international_plan`   | Plan-specific churn drivers — consider pricing and performance.                 |
| 6    | `total_intl_minutes`   | High global usage may indicate quality/cost concerns.                           |
| 7    | `total_night_minutes`  | Off-peak users may benefit from specialized plans.                              |
| 8    | `total_night_calls`    | Reveals customer behavior and engagement.                                       |
| 9    | `total_day_charge`     | Billing dissatisfaction possible churn trigger.                                 |
| 10   | `account_length`       | Newer customers may churn early — poor onboarding.                              |

---

## Business Recommendations

- **Enhance customer service** to reduce churn due to unresolved complaints.
- **Revise pricing plans**, especially for high-usage customers.
- **Targeted retention campaigns** for customers with high international or peak-hour usage.
- **Early onboarding support** for new customers to reduce short-term churn.

---

## Limitations

- Only call usage & plan features were used — lacks demographic and contract data.
- Future improvements can include temporal trends (month-on-month behavior).
- SMOTE may introduce synthetic noise if features aren't well-distributed.

---

## Tools Used

- Python (pandas, scikit-learn, matplotlib, seaborn)
- Jupyter Notebook
- SMOTE (imbalanced-learn)
- PowerPoint for presentation

---

## Conclusion

The **Tuned Decision Tree Classifier** provided strong predictive power for churn, especially for minority class customers. Feature interpretation offered actionable business insights that can help SyriaTel retain more customers.

---

## Author

Wadhare Isaac  
_Data Scientist | Python & Machine Learning Enthusiast_

