# MSCS_634_Lab_4

# Regression Techniques Lab using the Diabetes Dataset

## 📌 Purpose of the Lab

This lab explores regression techniques applied to the `sklearn` Diabetes dataset to predict disease progression. The objectives were:

- ✅ Implement and compare **Linear**, **Multiple**, and **Polynomial Regression** models  
- ✅ Apply **Ridge** and **Lasso** regularization methods to prevent overfitting  
- ✅ Evaluate model performance using **MAE**, **MSE**, **RMSE**, and **R²**  
- ✅ Derive insights into **feature importance** and **model robustness**  

---

## 📊 Key Insights

### 1. Model Performance

| Model                  | MAE   | R²   |
|------------------------|-------|------|
| Simple Linear (BMI)    | 44.42 | 0.23 |
| Multiple Regression     | 42.79 | 0.30 |
| Polynomial (Degree=2)   | 43.21 | 0.28 |
| Ridge Regression        | 42.80 | 0.30 |
| Lasso Regression        | 42.81 | 0.30 |

- **Multiple Regression** outperformed Simple Linear Regression, confirming that including more features improves predictive performance.
- **Ridge and Lasso** matched Multiple Regression in accuracy while offering better generalization by controlling coefficient sizes.
- **Polynomial Regression** provided only marginal improvement but introduced overfitting risk with higher-degree models.

---

### 2. Feature Importance

- **Lasso Regression** performed automatic feature selection by shrinking less important coefficients to zero.
- **BMI** and **blood pressure (bp)** emerged as consistently strong predictors across all regression models.

---

### 3. Regularization Impact

- **Ridge (L2)**: Reduced coefficient magnitudes smoothly to avoid overfitting.
- **Lasso (L1)**: Eliminated weaker features by assigning zero coefficients.
- Both **Ridge** and **Lasso** contributed to more stable, generalized predictions compared to unregularized models.

---

## ⚙️ Challenges & Decisions

### 1. Data Scaling for Regularization

- **Challenge**: Ridge and Lasso require features on similar scales, but the dataset had varying units.
- **Solution**: Used `StandardScaler` to normalize features before applying regularization models.

### 2. Polynomial Regression Overfitting

- **Challenge**: High-degree polynomial models (e.g., degree=3) degraded performance on test data.
- **Decision**: Limited polynomial analysis to degree=2 after observing increased RMSE values.

### 3. Alpha (λ) Tuning

- **Challenge**: Selecting optimal regularization strength (`alpha`) for Ridge and Lasso.
- **Decision**: Tested a range of alpha values (0.001 to 100) on a log scale and selected:
  - `α = 1.0` for Ridge  
  - `α = 0.1` for Lasso  
  Based on the best balance of MAE and generalization.

---

## ✅ Conclusion

This lab demonstrates the practical trade-offs between model complexity, performance, and generalization. Regularization techniques like Ridge and Lasso are essential tools to control overfitting and interpret feature importance in regression analysis.