\# Case Study: Loan Approval Model



\## Problem

A loan approval model shows lower approval rates for Black women over 40.



\## Step-by-Step Application



\### Historical Context

\- Documented history of lending discrimination  

\- High-risk intersectional group identified  



\### Fairness Definition Selection

\- Primary: Equal Opportunity  

\- Secondary: Demographic Parity  



\### Bias Source Identification

Findings:

\- Underrepresentation in training data  

\- Historical bias in repayment labels  

\- Proxy features (ZIP code) correlated with race  



\### Metrics

\- TPR disparity: 0.62 vs. 0.81  

\- Approval rate disparity: 0.55 vs. 0.78  

\- Calibration error higher for intersectional group  



\### Mitigations

\- Reweighting  

\- Removing ZIP code  

\- Synthetic oversampling  

\- Post-processing threshold adjustments  



\### Outcome

Disparities reduced by ~30% while maintaining model performance.

