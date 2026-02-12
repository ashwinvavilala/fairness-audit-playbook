\# Bias Source Identification — Loan Approval Model



\## 1. Data Bias



\### Representation Bias

\- Black women over 40 underrepresented.



\### Label Bias

\- Repayment labels reflect historical inequities.



\### Sampling Bias

\- Applicants from historically redlined areas under-sampled.



\## 2. Model Bias



\### Proxy Features

\- ZIP code correlates with race.



\### Feature Sensitivity

\- Short credit history penalizes older women.



\### Architecture Limitations

\- No fairness-aware regularization.



\## 3. Pipeline Bias



\### Feedback Loops

\- Denials prevent building credit history.



\### Drift

\- No subgroup drift monitoring.



\### Human Overrides

\- Overrides disproportionately affect certain ZIP codes.



\## 4. Intersectional Bias Map



| Source | Evidence | Impacted Groups | Severity | Mitigation |

|--------|----------|-----------------|----------|------------|

| Representation | Low sample size | Black women 40+ | High | Oversampling |

| Label Bias | Biased repayment labels | Black applicants | High | Label audit |

| Proxy Features | ZIP code correlation | Black applicants | Medium | Remove ZIP |

| Feature Sensitivity | Penalizes short history | Women 40+ | Medium | Transform features |

| Drift | No monitoring | Minority groups | Medium | Add drift detection |



\## 5. Summary

Bias is present across data, model, and pipeline components.

