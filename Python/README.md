# Advanced Statistical Modeling in Python

---

## Covered Techniques

### 1. Linear and Generalized Linear Models
- `ols()` and `glm()` models via `statsmodels.formula.api`
- Variance Inflation Factor (VIF)
- Stepwise model selection (custom AIC/BIC loops)
- Normality and homoscedasticity tests (`shapiro`, `levene`, `bartlett`)

### 2. Robust Alternatives
- HuberRegressor, Theil–Sen, and RANSAC
- Quantile regression (`smf.quantreg`)
- Comparison of residual robustness vs OLS

### 3. Hierarchical Models
- Mixed-effects models with `linearmodels` and `statsmodels.MixedLM`
- Bayesian versions with `PyMC`
- ICC computation and posterior predictive checks

### 4. Bayesian and MCMC Estimation
- Model definition with `pymc.Model`
- Sampling with `pm.sample()`
- Visualization with `arviz`

---

## Main Python Libraries

| Purpose | Packages |
|----------|-----------|
| Classical modeling | `statsmodels`, `scipy`, `linearmodels` |
| Robust models | `sklearn.linear_model`, `pingouin` |
| Bayesian inference | `pymc`, `arviz` |
| Data manipulation | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn` |

---

## Example Run

```
python Python/04_robust_models/huber_regressor.ipynb
```

---

## Example Output

```
from statsmodels.formula.api import ols
import statsmodels.api as sm

model = ols("Weekly_Sales ~ Store + Dept", data=df).fit()
print(model.summary())

# Residual diagnostics
sm.qqplot(model.resid, line='s')
plt.show()
```


