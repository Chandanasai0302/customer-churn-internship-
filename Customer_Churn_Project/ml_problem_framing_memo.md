# ML Problem-Framing Memo: Customer Churn Prediction

## 1. Project Objective
The objective of this project is to study customer churn prediction using machine learning. The project aims to identify patterns in customer data that may help predict whether a customer will churn.

## 2. Decision to Support
The prediction can help a business identify customers who may need additional support or retention activities. The model will provide decision support and will not make final customer-related decisions automatically.

## 3. Prediction Target
The target variable is `churned`, available in the provided dataset.

- `1` represents a customer labeled as churned.
- `0` represents a customer labeled as not churned.

The exact definition and time period of the churn label are not specified in the provided dataset.

## 4. Unit of Observation
Each row represents one customer record. The `customer_id` column is used to identify the customer and will not be used as a predictive feature.

## 5. Available Features
The dataset contains the following potential predictive features:

- `tenure_months`: Customer tenure in months.
- `support_tickets`: Number of support tickets.
- `monthly_spend_inr`: Monthly customer spending in Indian rupees.
- `last_login_days`: Number of days since the last login.
- `plan_type`: Customer subscription plan.

These features will be examined for their suitability before model training.

## 6. Action Window
The intended purpose is to identify potentially at-risk customers early enough for a business to review their needs. The dataset does not specify a prediction horizon or action window, so these cannot be established from the available information.

## 7. Non-ML Baseline
A simple rule-based method will be used as a baseline before evaluating a machine learning model. For example, customers with a high number of days since their last login may be flagged for review. The rule and its threshold will be documented and evaluated before comparison with an ML model.

## 8. Evaluation Metrics
The project will evaluate precision, recall, F1-score, and the confusion matrix.

False positives may lead to unnecessary customer outreach, while false negatives may result in missed opportunities to retain customers. The preferred trade-off will depend on the relative costs of these errors.

## 9. Data Limitations
The provided dataset contains 12 customer records and 7 columns. It contains no missing values in the inspected fields, but the small sample size limits the reliability of model evaluation.

The dataset's original source, collection method, permitted use, and exact churn-label definition are not documented in the supplied files.

## 10. Responsible Use
The model will be treated as an educational prototype. Predictions should be reviewed by a human before any retention action is taken. The model must not be used as the sole basis for denying services, penalizing customers, or making other significant decisions.

## 11. Conclusion
This project will establish a basic customer churn prediction workflow, evaluate a simple baseline, and examine whether machine learning can provide useful predictive information. Further data validation and a larger dataset are required before considering real-world use.
