# Comparing-Classifiers
In this practical application, goal is to compare the performance of the classifiers namely K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. Dataset related to marketing bank products over the telephone was utilized.

**Overview:**
The business objective is to develop a predictive model to accurately identify bank clients likely to subscribe to a term deposit, enabling targeted marketing campaigns to optimize resource allocation and increase subscription rates.

**Data Preparation:** After examining the data, checking for missing values and duplicate values, the following features were coerced from 'object' to 'category' type: 'job', 'marital', 'education', 'default', 'housing', 'loan', 'contact', 'month', 'day_of_week', 'poutcome' and the target variable 'y' was coerced into 'boolean' type. One hot coding was used for categorical features and the numerical features were scaled for normalization. Four models were used for the classification task - K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. ROC curves were plotted for analysis. These models and their results are provided in the table below.

**Modeling:**  (Model #9 is the model with lowest error and highest R2 values).

| Model | X Features | R² - Train | R² - Test | MSE |
|-------|------------|------------|-----------|-------------|
| 1. Linear Regression | year, manufacturer, fuel, odometer, title_status, transmission, type, paint_color, state | 0.548 | 0.544 | 94394261.14 |
| 2. Ridge Regression | year, manufacturer, fuel, odometer, title_status, transmission, type, paint_color, state | 0.548 | 0.544 | 94378978.45 |
| 3. Lasso Regression (α=1) | year, manufacturer, fuel, odometer, title_status, transmission, type, paint_color, state | 0.548 | 0.544 | 94378978.45 |
| 4. Linear Regression | year, manufacturer, odometer | 0.406 | 0.401 | 124117305.87 |
| 5. Linear Regression | year, odometer | 0.299 | 0.296 | 146012502.62 |
| 6. Linear Regression | year | 0.121 | 0.116 | 183239489.06 |
| 7. LASSO (Poly degree=2, α=0.1) | year, manufacturer, odometer | 0.427 | 0.421 | 119929661.46 |
| 8. LASSO (Poly degree=2, α=0.1) | year, manufacturer, fuel, odometer, title_status, transmission, type, paint_color, state | 0.560 | 0.555 | 92167311.15 |
| 9. LASSO (Poly degree=3, α=0.1) | year, manufacturer, fuel, odometer, title_status, transmission, type, paint_color, state | 0.564 | 0.560 | 91144455.49 |
| 10. Ridge (GridSearchCV, best α=10) | year, odometer | 0.299 | 0.296 | 146012463.52 |
| 11. LASSO (Poly degree=3, α=10) | year, manufacturer, fuel, odometer, title_status, transmission, type, paint_color, state | 0.556 | 0.551 | 92989662.12 |
| 12. LASSO (Poly degree=3, α=1) | year, manufacturer, fuel, odometer, title_status, transmission, type, paint_color, state | 0.564 | 0.559 | 91294591.38 |

**Evaluation:** Model #9 from the above table is the recommended model. This data is heavily imbalanced with 88% of 0s and 11% 1s for the target variable 'y' which resulted in low ROC values. Class weights were applied and hyperparamater tuning with gridsearchcv was used. 
