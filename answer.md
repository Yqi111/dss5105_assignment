
## Question 1

### a) Estimated Parameters

**Model**: Y<sub>i</sub> = α + τ·W<sub>i</sub> + β·X<sub>i</sub> + ε<sub>i</sub>

- Estimated Intercept (α̂): `95.97`
- Estimated Treatment Effect (τ̂): `-9.11`
- Estimated Spending Effect (β̂): `1.51`

---

### b) Estimated Average Treatment Effect（ATE）

- τ̂ = `-9.11`
- No p-values available (used `scikit-learn`)

---

### c) Underlying Causal Assumptions

- The treatment assignment is assumed to be unconfounded

- No relevant confounders are omitted

- The linear functional form is assumed to be valid

- The Stable Unit Treatment Value Assumption (SUTVA) is met



---

## Question 2

### a) Development Environment

- Utilized GitHub Codespaces with a custom Dockerfile

- Stack includes Python, Flask, NumPy, and scikit-learn


---

### b) API Functionality

- Endpoint: `/predict?w=1&x=20`
- Returns predicted score and model parameters

---

### c) Test Result

Input:
- Treatment (w) = 1
- Spending (x) = 20

Output:

```json
{
  "w": 1.0,
  "x": 20.0,
  "predicted_engagement_score": 117.16,
  "intercept": 95.97,
  "treatment_effect (tau)": -9.11,
  "spending_effect (beta)": 1.51
}

