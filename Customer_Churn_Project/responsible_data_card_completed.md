# Responsible Data Card — Customer Churn Prediction

## 1. Dataset Purpose
This dataset is being used for an educational customer churn prediction project. The aim is to explore whether available customer information can help identify customers who may leave a service. Predictions should only support human review and must not automatically cancel service, deny benefits, or set prices.

## 2. Provenance and Permission
Dataset filename: `customer-churn-training.csv`.

The supplied file does not state who created the dataset, where it originally came from, how the data was collected, whether customers consented to this use, or what license applies. These details must be confirmed with the internship guide or dataset provider before any real-world use. Until then, use the file only for the authorized internship exercise.

## 3. Population and Representation
The dataset contains 12 rows and appears to contain one row per customer. It includes the plan types Basic, Standard, and Pro. The source population, collection dates, geography, sampling method, and customer-group representation are not documented. Therefore, we cannot conclude that the data represents real customers generally.

The target column has two values: `1` (churned) and `0` (not churned). The exact definition and time period for churn are not documented.

## 4. Features and Target
- `customer_id`: Customer identifier. Exclude it from model input because it identifies records rather than describing customer behaviour.
- `tenure_months`: Customer tenure in months. Confirm when it was measured.
- `support_tickets`: Number of support tickets. The counting period is not specified.
- `monthly_spend_inr`: Monthly spend in Indian rupees. Confirm the billing period and calculation.
- `last_login_days`: Days since last login. Confirm the date used to calculate it.
- `plan_type`: Subscription plan (Basic, Standard, or Pro).
- `churned`: Target label; `1` means churned and `0` means not churned, based on the supplied coding. Confirm the business definition and prediction horizon with the data provider.

## 5. Data Quality Checks
- Number of records: 12.
- Number of columns: 7.
- Missing values: none detected in the supplied file.
- Exact duplicate rows: none detected.
- Customer IDs: 12 unique values.
- Churn labels: 5 records labelled `1` and 7 records labelled `0`.
- The dataset is very small. Any model evaluation will be unstable and should be treated as a demonstration, not evidence of production performance.
- The file does not include documented timestamps, so a realistic time-based evaluation cannot yet be performed.

## 6. Leakage Risks
A feature may cause data leakage if it was recorded after the time at which the prediction is meant to be made. Before modeling, confirm that all features are available at prediction time and that the churn label describes a later, defined period. Do not use `customer_id` as a predictive feature.

## 7. Risks and Safeguards
- **Privacy and permission:** Verify source, license, consent or other valid permission, and permitted use.
- **Small sample:** Do not claim that the model generalizes from 12 records. Obtain a larger, representative dataset for meaningful evaluation.
- **False positives:** Customers may be flagged unnecessarily, causing unwanted outreach and staff workload. Use human review and monitor outreach volume.
- **False negatives:** Customers who may churn could be missed. Track recall and review missed cases.
- **Bias and fairness:** Check whether data coverage or model performance differs across relevant customer groups where appropriate and lawful. The supplied file does not contain demographic attributes, so fairness cannot be fully assessed from this file alone.
- **Misuse:** Do not use predictions to deny service, penalize customers, or set prices.
- **Human oversight:** Treat model output as advisory. A person should decide whether outreach is appropriate.

## 8. Intended Evaluation
Compare a transparent rule-based baseline with any ML model. Report a confusion matrix, precision, recall, F1 score, and the number of customers flagged for review. Decide with the business owner whether false negatives or false positives are more costly before choosing a threshold. With a larger, time-stamped dataset, use a chronological evaluation that mirrors future use and inspect errors. Fairness and calibration checks require adequate data.

## 9. Approval Status
**Not approved for production use.** Dataset provenance, permissions, label definition, prediction timing, representativeness, and adequate evaluation data have not been established.

## 10. Questions to Confirm with the Internship Guide
1. What is the original source of this dataset, and what use is permitted?
2. What exactly does `churned = 1` mean, and over what time period?
3. When were the features measured relative to the churn outcome?
4. Is there a required prediction horizon or evaluation metric?
