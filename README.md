
# Advanced Statistical Modeling — R & Python

> “A data scientist is not a button pusher.” — Prof. Luiz Paulo Fávero, USP university

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)
![Status](https://img.shields.io/badge/Status-In_Progress-yellow)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)
 
 ---

## Project Status

This repository is **work-in-progress**. 

---

## Purpose

This repository gathers **advanced exercises in statistical modeling**, implemented in both **R** and **Python**, focusing on:

- Diagnosis and fitting of **linear, GLM, and GLMM** models.  
- Application of **classical statistical tests** (normality, homoscedasticity, autocorrelation, specification).  
- Exploration of **robust alternatives** (Huber, Tukey, Quantile, RANSAC, MM-estimators).  
- **Hierarchical (HLM2/HLM3)** modeling and variance decomposition.  
- Comparison of **fit metrics** (logLik, AIC, BIC, ICC).  
- Visualization and interpretation with an **inferential and reproducible** approach.

The project deliberately avoids “black-box” automation (e.g., `sklearn.fit()`), emphasizing **true statistical reasoning** over algorithmic shortcuts.

---

## Repository Structure

```

advanced-statistical-models/
│
├── R/
│   ├── 01_linear_models/
│   ├── 02_glm/
│   ├── 03_hierarchical_models/
│   ├── 04_robust_models/
│   ├── 05_model_comparison/
│   ├── 06_bayesian_extensions/
│   └── README_R.md
│
├── Python/
│   ├── 01_linear_models/
│   ├── 02_glm/
│   ├── 03_hierarchical_models/
│   ├── 04_robust_models/
│   ├── 05_model_comparison/
│   ├── 06_bayesian_extensions/
│   └── README_Python.md
│
└── README.md

```

---

## Project Philosophy

> “Simplicity in statistics must precede complexity in algorithms.”

The goal is to **strengthen statistical fundamentals**, applying appropriate diagnostics and transformations *before* moving to non-statistical approaches like trees, ensembles, or neural networks.  
Each exercise is implemented **twice** — once in R and once in Python — demonstrating that solid reasoning is **language-agnostic**.

---

## Topics Covered

### 1. Linear Models
- Linearity and multicollinearity diagnostics (`car::crPlots`, `statsmodels.stats.outliers_influence`)
- Stepwise model selection (AIC, BIC, AICc)
- Residual diagnostics: Shapiro–Francia, Breusch–Pagan, Durbin–Watson, RESET test

### 2. Generalized Linear Models (GLM)
- Poisson vs Negative Binomial  
- Overdispersion and Zero-Inflation tests  
- Model comparison via deviance and log-likelihood ratio tests  

### 3. Hierarchical Models (HLM2 / HLM3)
- Random intercept and random slope models `(1 | Store) + (1 | Dept)`
- Intraclass Correlation Coefficient (ICC)
- Diagnostics using `DHARMa` (R) and simulated residuals (Python)

### 4. Robust Model Alternatives
- Robust regressions: Huber, Tukey, MM-estimator, Theil–Sen, RANSAC  
- Quantile regression (median and quantile estimation)  
- Weighted Least Squares (WLS) vs OLS  
- Graphical comparison and robust metrics  

### 5. Bayesian Extensions
- Hierarchical modeling with `brms` (R) and `PyMC` (Python)
- Convergence and prior sensitivity diagnostics  
- Posterior predictive checks  

---

## Main Libraries

**R:**  
`car`, `lmtest`, `DHARMa`, `MASS`, `robustbase`, `glmmTMB`, `effects`, `brms`, `influence.ME`

**Python:**  
`statsmodels`, `scipy`, `sklearn`, `pymc`, `pingouin`, `linearmodels`, `matplotlib`, `seaborn`, `rpy2`

---

## Example — OLS vs Huber Regression

| Method | Outlier Sensitivity | Robustness |
|--------|---------------------|------------|
| OLS    | High                |    Weak    |
| Huber  | Moderate            |    Strong  |
| Tukey  | Low                 | Very Strong|

<img src="assets/ols_vs_huber.png" width="600">


---

## Installation & Setup

Follow the steps below to set up your environment correctly.

### 1. Clone the repository

```
git clone https://github.com/your-username/walmart-hlm.git
cd walmart-hlm
```

### 2. Install Miniconda or Mamba (if you don’t have it yet)

* [Download Miniconda](https://docs.conda.io/en/latest/miniconda.html) or
* [Install Mamba](https://mamba.readthedocs.io/en/latest/installation.html) (faster, recommended).

### 3. Create the environment

```
mamba env create -f environment.yml
# or
conda env create -f environment.yml
```

### 4. Activate the environment

```
conda activate walmart-hlm
```

### 5. (Optional) Install R and `lme4` for GLMM models

If you plan to use `pymer4` for Negative Binomial GLMM models, make sure R and `lme4` are installed:

#### On Linux / macOS:

```
# Install R
sudo apt-get update && sudo apt-get install -y r-base
# or use brew on macOS
brew install r

# Install lme4 in R
R -e "install.packages('lme4', repos='https://cloud.r-project.org')"
```

#### On Windows:

1. Install [R](https://cran.r-project.org/).
2. Open R and run:

```
install.packages("lme4", repos="https://cloud.r-project.org")
```

> Note: `pymer4` requires `lme4` under the hood to run GLMMs.
> If you don't want to use R, you can rely on Python’s `statsmodels` for OLS and GLM models only.

### 6. Verify the installation

```
python -c "import numpy, pandas, statsmodels; print('Python stack OK')"
R -q -e "library(lme4); cat('R stack OK\n')"
```

**Tips for best practice**:

* Always work inside the conda environment — this ensures your results are reproducible.
* If you make changes to `environment.yml`, update the environment with:

```
mamba env update -f environment.yml --prune
```

* For collaborators: they only need to run steps 1–4 to reproduce your environment.


---

## References


* Gelman & Hill (2007) *Data Analysis Using Regression and Multilevel/Hierarchical Models*
* Fox & Weisberg (2019) *An R Companion to Applied Regression*
* Venables & Ripley (2002) *Modern Applied Statistics with S*
* Fávero & Belfiore (2023). *Data Science, Analytics and Machine Learning with R*
* Fávero & Belfiore (2017). *Manual de análise de dados*


---


## About the Author

I’m a Data Science and Analytics specialist (USP postgraduate) and Computer Engineer (UERJ) with a career spanning from **Pascal/C/Java roots** to **modern Machine Learning and AI**.

My academic and professional background includes:

* **Computation in general**
* **Machine Learning**
* **Statistical Machine Learning**
* **Deep Learning, LLMs, and Reinforcement Learning (ongoing specialization)**


---


## Contact  

- [LinkedIn](https://linkedin.com/in/celso-m-silva)  
- Or open an [issue](https://github.com/celsomsilva/advanced-statistical-models)



