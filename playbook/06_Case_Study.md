# 6. Case Study: Fairness Audit of a Loan Approval Model

This case study demonstrates how the Fairness Audit Playbook can be applied end‑to‑end to a real‑world scenario.  
The example focuses on a binary loan approval model used by a financial institution to automate credit decisions.

---

## 1. Context and Model Overview

The institution uses a gradient‑boosted decision tree model to predict loan repayment likelihood.  
The model influences approval decisions for personal loans ranging from £2,000–£15,000.

- **Business owner:** Lending Operations
- **Technical owner:** ML Engineering Team
- **Primary objective:** Reduce manual underwriting workload while maintaining risk thresholds
- **Sensitive attributes available:** Race (self‑reported), Gender, Age
- **Risk level:** High (financial access, regulatory exposure, historical inequities)

---

## 2. Historical Context

The audit begins by grounding the evaluation in domain‑specific inequities:

- **Documented history of lending discrimination:**  
  Past policies (e.g., redlining, biased credit scoring) have disproportionately harmed Black and minority ethnic borrowers.

- **High‑risk intersectional groups identified:**
  - Black women
  - Older minority borrowers
  - Applicants from historically underserved postcodes

- **Structural factors:**
  - Lower average credit histories due to systemic barriers
  - Higher likelihood of thin‑file applicants
  - Geographic clustering caused by historical segregation

This context shapes the fairness definitions and metrics selected later.

---

## 3. Fairness Definition Selection

Two fairness definitions were chosen:

- **Primary: Equal Opportunity**  
  Ensures qualified applicants (those who would repay) have equal approval rates across groups.  
  This aligns with regulatory expectations and reduces harm to creditworthy minority borrowers.

- **Secondary: Demographic Parity**  
  Used as a monitoring metric to detect large disparities in overall approval rates, even if risk‑adjusted fairness is satisfied.

Rationale: Equal Opportunity balances fairness with legitimate business risk constraints.

---

## 4. Bias Source Identification

A structured bias mapping exercise revealed several risk points:

### **Data Bias**

- Underrepresentation of minority groups in the training dataset
- Historical repayment labels reflect past discriminatory lending practices
- Thin‑file applicants disproportionately belong to protected groups

### **Feature Bias**

- **Postcode** strongly correlated with race due to historical segregation
- **Employment stability** penalizes applicants in precarious labour markets
- **Credit history length** disadvantages younger and minority borrowers

### **Modeling Bias**

- Model overfits to repayment patterns shaped by historical inequities
- Thresholds optimized for overall accuracy, not group‑level fairness

### **Process Bias**

- Manual overrides disproportionately applied to certain groups
- Lack of fairness checks during model retraining

---

## 5. Fairness Metrics Evaluation

Metrics were computed for the two largest demographic groups:

| Metric                   | Group A (Majority) | Group B (Minority) | Disparity |
| ------------------------ | ------------------ | ------------------ | --------- |
| True Positive Rate (TPR) | 0.81               | 0.62               | **0.19**  |
| Approval Rate            | 0.78               | 0.55               | **0.23**  |
| False Negative Rate      | 0.19               | 0.38               | **0.19**  |
| Calibration Error        | 0.04               | 0.09               | **0.05**  |

**Key Findings:**

- Minority applicants who would repay are being denied at significantly higher rates.
- Approval rate disparity exceeds internal fairness thresholds.
- Calibration differences suggest the model is less reliable for minority groups.

---

## 6. Mitigation Strategies

The audit team proposed a combination of data, model, and process interventions:

### **Data-Level Mitigations**

- Reweighting training samples to reduce group imbalance
- Synthetic oversampling for thin‑file minority applicants
- Removing postcode as a feature due to high proxy risk

### **Model-Level Mitigations**

- Group‑specific thresholds to equalize TPR
- Fairness‑constrained optimization during training
- Calibration adjustments for minority groups

### **Process-Level Mitigations**

- Introduce fairness checks in every retraining cycle
- Require justification for manual overrides
- Add governance review for high‑impact model changes

---

## 7. Validation and Documentation

Using the validation checklist:

- All fairness definitions were justified
- Metrics were computed across intersectional groups
- Mitigation strategies were tested and documented
- Stakeholders reviewed the audit findings
- A final audit report was produced using the template

---

## 8. Final Outcome

After applying mitigations:

- TPR disparity reduced from **0.19 → 0.05**
- Approval rate disparity reduced from **0.23 → 0.08**
- Calibration improved for minority groups
- Business risk remained within acceptable thresholds

The model was approved for deployment with ongoing monitoring requirements.

---

This case study demonstrates how the playbook can be applied in practice and provides a reference for teams conducting their own fairness audits.
