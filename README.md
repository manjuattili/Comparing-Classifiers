# Comparing-Classifiers
In this practical application, goal is to compare the performance of the classifiers namely K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. Dataset related to marketing bank products over the telephone was utilized.

**Overview:**
The business objective is to develop a predictive model to accurately identify bank clients likely to subscribe to a term deposit, enabling targeted marketing campaigns to optimize resource allocation and increase subscription rates.

**Data Preparation:** After examining the data, checking for missing values and duplicate values, the following features were coerced from 'object' to 'category' type: 'job', 'marital', 'education', 'default', 'housing', 'loan', 'contact', 'month', 'day_of_week', 'poutcome' and the target variable 'y' was coerced into 'boolean' type. One hot coding was used for categorical features and the numerical features were scaled for normalization.  

**Modeling:**  Four models were used for the classification task - K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. ROC curves were plotted for analysis. These models and their results are provided in the table below.


**Evaluation:** Model #9 from the above table is the recommended model. This data is heavily imbalanced with 88% of 0s and 11% 1s for the target variable 'y' which resulted in low ROC values. Class weights were applied and hyperparamater tuning with gridsearchcv was used. 
