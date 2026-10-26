# Implementation Note — Customer Churn Prediction

## 1. Objective
The objective of this project is to identify customers who may churn and support customer-retention efforts.

## 2. Dataset
The project uses `customer-churn-training.csv`, which contains 12 sample customer records. The dataset includes tenure, support tickets, monthly spend, days since last login, plan type, and the churn label.

The dataset is small and intended for learning and demonstration. Its original provenance, consent status, and exact churn-label time window have not been independently verified.

## 3. Implementation
1. Load the CSV file and inspect its columns, data types, missing values, and duplicate records.
2. Define the prediction target, business decision, observation unit, action window, and non-ML baseline.
3. Establish a simple rule-based baseline using customer inactivity and support-ticket patterns.
4. Exclude `customer_id` from model features because it is an identifier.
5. Evaluate the baseline using precision, recall, F1-score, and a confusion matrix.
6. Consider the costs of unnecessary retention outreach and missed churners.
7. Document data-quality issues, potential leakage, privacy considerations, and limitations.

## 4. Risk Management
The small dataset may not represent real customers. The churn label and its time window need clarification, and features must be checked to prevent data leakage. Data authorization and consent should be verified before practical use.

Uncertain predictions should receive human review. Monitoring and rollback thresholds should be defined before any deployment.

## 5. Proof and Deliverables
The repository contains:
- `README.md` — project overview.
- `ml_problem_framing_memo.md` — problem framing and baseline.
- `responsible_data_card_completed.md` — data documentation and limitations.
- `baseline_notebook.ipynb` — baseline implementation and analysis.
- `risk_register.md` — risks and proposed safeguards.
- `customer-churn-training.csv` — sample dataset.

Reviewers can inspect the notebook and run its cells to verify the implementation and results.

## 6. Limitations and Conclusion
This is a learning demonstration, not a production-ready churn prediction system. The dataset contains only 12 records, and its provenance and label timing have not been independently verified. Larger representative data and independent validation are required before real-world use.
