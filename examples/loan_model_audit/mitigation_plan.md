\# Mitigation Plan — Loan Approval Model

\## 1. Data-Level Mitigations

\- Oversampling underrepresented groups

\- Reweighting to reduce label bias

\- Label audit and adjusted targets

\## 2. Model-Level Mitigations

\- Remove ZIP code

\- Transform credit history features

\- Threshold adjustments

\- Fairness-constrained optimization

\## 3. Pipeline-Level Mitigations

\- Subgroup drift monitoring

\- Human override audits

\## 4. Expected Impact

\- TPR disparity reduced from 0.19 → 0.07

\- Approval disparity reduced from 0.23 → 0.10

\- Improved calibration

\## 5. Risks

\- Oversampling variance

\- Threshold adjustments require monitoring

\## 6. Next Steps

\- Deploy with monitoring

\- Quarterly fairness audits
