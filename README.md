# linear_ridge_lasso_elastic_regression_practice
# Regression Comparison: Linear, Ridge, Lasso, and Elastic Net

## 📊 Project Overview
This project compares four types of regression models on the **Diabetes dataset** from `sklearn.datasets`.  
The goal is to understand **how regularization affects coefficients and model performance**.

**Dataset:**
- **Observations:** 442  
- **Features:** 10 (`age`, `sex`, `bmi`, `bp`, `s1`–`s6`)  
- **Target:** Disease progression after 1 year

---

## 🧩 Models Compared
| Model       | Penalty  | Notes / Effect                                    |
|------------|----------|--------------------------------------------------|
| Linear     | None     | Baseline OLS regression, no shrinkage           |
| Ridge      | L2       | Shrinks coefficients, reduces multicollinearity |
| Lasso      | L1       | Shrinks some coefficients to 0 (feature selection) |
| Elastic Net| L1 + L2  | Mix of shrinkage + feature selection            |

---

## 📈 Key Results
| Model       | Best α | R² (Test) | MSE (Test) | Notes on Coefficients                  |
|------------|--------|-----------|------------|--------------------------------------|
| Linear     | N/A    | 0.44      | ~2900      | All coefficients present              |
| Ridge      | ~10    | 0.45      | ~2850      | All coefficients shrunk slightly      |
| Lasso      | ~0.01  | 0.44      | ~2950      | Some coefficients exactly 0           |
| Elastic Net| ~0.03  | 0.45      | ~2850      | Combination of shrinkage + zeros      |

> Numbers are approximate; actual results depend on dataset split and CV.

---

## 🔍 Observations
- Coefficients can be **positive or negative**, indicating direction of effect.  
- **Lasso** zeros out some features → useful for feature selection.  
- **Elastic Net** balances Ridge & Lasso → ideal for correlated features.  
- Regularization improves **stability** when predictors are correlated.

---

## 💡 Practical Tips
- Use **Linear Regression** for small, simple datasets.  
- Use **Ridge** when predictors are correlated but all are important.  
- Use **Lasso** when you want sparse models (irrelevant features removed).  
- Use **Elastic Net** for large datasets with many correlated features, combining shrinkage and selection.

---

## 📊 Optional Visuals
- Bar chart comparing coefficients (Ridge vs Lasso vs Elastic Net).  
- Table comparing R² and MSE for all models.  

---

## 📂 References
- [Scikit-learn Regression Models](https://scikit-learn.org/stable/supervised_learning.html#supervised-learning)  
- [Diabetes Dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_diabetes.html)
