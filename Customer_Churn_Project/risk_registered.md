# Risk Register: Customer Churn Prediction

## 1. Data Quality Risk
**Risk:** Missing, incorrect, or inconsistent customer data may cause unreliable predictions.

**Mitigation:** Check missing values, duplicate records, invalid values, and data types before training.

## 2. Small Dataset Risk
**Risk:** The supplied dataset contains only 12 customer records, which is insufficient to establish reliable model performance.

**Mitigation:** Use it for learning and demonstration only. Obtain a larger, representative dataset before considering real-world use.

## 3. Data Leakage Risk
**Risk:** The model may use information that would not be available when the prediction is made.

**Mitigation:** Confirm the prediction date and ensure that all features are available before the churn prediction period.

## 4. False Positive Risk
**Risk:** A customer may be incorrectly identified as likely to churn, resulting in unnecessary outreach.

**Mitigation:** Require human review before contacting flagged customers and monitor unnecessary outreach.

## 5. False Negative Risk
**Risk:** A customer who is likely to churn may not be identified.

**Mitigation:** Measure recall, review missed churn cases, and compare the model against the baseline.

## 6. Privacy and Permission Risk
**Risk:** The dataset's source, consent, license, and permitted uses are not documented in the supplied information.

**Mitigation:** Verify these details with the dataset provider before any real-world use.

## 7. Bias and Fairness Risk
**Risk:** The model may perform differently across customer groups or subscription plans.

**Mitigation:** Evaluate data representation and group-level performance where appropriate and lawful.

## 8. Model Performance Risk
**Risk:** Model performance may decline when customer behaviour changes.

**Mitigation:** Monitor performance using verified outcomes and predefined evaluation criteria.

## 9. Human Oversight Risk
**Risk:** Staff may rely on predictions without considering other relevant information.

**Mitigation:** Treat predictions as decision-support signals and require human review.

## 10. Rollback Plan
Stop using the model and return to the documented rule-based baseline if serious data quality problems, leakage, unacceptable performance, or harmful outcomes are identified.

## Conclusion
The risk register identifies key risks and mitigation measures for the customer churn prediction project. The model is intended for educational evaluation and must not be considered production-ready based on the current dataset.
