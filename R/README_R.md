# Advanced Statistical Modeling in R

---

## Covered Techniques

### 1. Linear and Generalized Linear Models
- Collinearity analysis with `car::vif()`
- Stepwise selection using AIC/BIC
- Normality tests: Shapiro–Francia, Anderson–Darling
- Heteroscedasticity and autocorrelation: Breusch–Pagan, Durbin–Watson
- Specification error: RESET test

### 2. Transformations and Model Re-specification
- Box–Cox and Yeo–Johnson transformations  
- Iterative model refinement  
- Comparison via `logLik`, `AIC`, and `BIC`

### 3. Count Models
- Poisson and Negative Binomial GLMMs (`glmer.nb`)
- Random intercepts for hierarchical structures: `(1 | Store) + (1 | Dept)`
- Model diagnostics with `DHARMa`

### 4. Robust Models
- Robust regressions (`rlm`, `lmrob`, `quantreg`)
- M-estimators: Huber, Tukey, Hampel
- Outlier-resistant models and influence diagnostics

### 5. Hierarchical Linear Models (HLM2 / HLM3)
- Variance decomposition via `VarCorr`
- Intraclass correlation (ICC)
- Confidence intervals and random effect interpretation

---

## Main R Packages

| Purpose | Packages |
|----------|-----------|
| Model diagnostics | `car`, `lmtest`, `performance`, `DHARMa` |
| Robust modeling | `MASS`, `robustbase`, `quantreg` |
| Hierarchical models | `lme4`, `nlme`, `glmmTMB` |
| Visualization | `ggplot2`, `effects`, `see` |

---

## Example Run

```
Rscript R/03_hierarchical_models/glmer_negative_binomial.R
````

---

## Example Output

```
# Model fit
nb_multilevel_null_model <- glmer.nb(
  Weekly_Sales ~ 1 + (1 | Store) + (1 | Dept),
  data = data
)

logLik(nb_multilevel_null_model)
AIC(nb_multilevel_null_model)
BIC(nb_multilevel_null_model)
VarCorr(nb_multilevel_null_model)
confint(nb_multilevel_null_model)
```

