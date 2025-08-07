# Comparing-Classifiers
In this practical application, goal is to compare the performance of the classifiers namely K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. Dataset related to marketing bank products over the telephone was utilized.

**Overview:**
The business objective is to develop a predictive model to accurately identify bank clients likely to subscribe to a term deposit, enabling targeted marketing campaigns to optimize resource allocation and increase subscription rates.

**Data Preparation:** After examining the data, checking for missing values and duplicate values, the following features were coerced from 'object' to 'category' type: 'job', 'marital', 'education', 'default', 'housing', 'loan', 'contact', 'month', 'day_of_week', 'poutcome' and the target variable 'y' was coerced into 'boolean' type. One hot coding was used for categorical features and the numerical features were scaled for normalization.  

**Modeling:**  Four models were used for the classification task - K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. ROC curves were plotted for analysis. These models and their results are provided in the table below.

| Model Name                | Training Accuracy | Testing Accuracy | Notes |
|---------------------------|-------------------|------------------|-------|
| Logistic Regression       | 0.9011            | 0.9002           | Default settings, no class weighting |
| KNN                       | 0.9138            | 0.8898           | Default settings (`n_neighbors=5`), no class weighting |
| Decision Tree             | 0.9957            | 0.8426           | Default settings, no class weighting |
| SVM                       | 0.9060            | 0.8999           | Default settings, no class weighting |
| Logistic Regression       | 0.8296            | 0.8279           | Class-weighted (`class_weight='balanced`) |
| KNN                       | 0.9957            | 0.8830           | Class-weighted (`weights='distance`) |
| Decision Tree             | 0.9951            | 0.8388           | Class-weighted (`class_weight='balanced`) |
| SVM                       | 0.8565            | 0.8504           | Class-weighted (`class_weight='balanced`, `probability=True`) |
| Logistic Regression       | 0.8294            | 0.8287           | Class-weighted (`class_weight='balanced`), X2 features (dropped `age`, `education`) |
| KNN                       | 0.9743            | 0.8796           | Class-weighted (`weights='distance`), X2 features (dropped `age`, `education`) |
| Decision Tree             | 0.9480            | 0.8078           | Class-weighted (`class_weight='balanced`), X2 features (dropped `age`, `education`) |
| SVM                       | 0.8532            | 0.8496           | Class-weighted (`class_weight='balanced`, `probability=True`), X2 features (dropped `age`, `education`) |
| Decision Tree (GridSearchCV) | Not reported      | 0.8421           | Class-weighted (`class_weight='balanced`), GridSearchCV (`max_depth=5`), top 20 features |
| KNN (GridSearchCV)        | Not reported      | 0.8935           | Class-weighted (`weights='distance`), GridSearchCV (`n_neighbors=20`), top 20 features |


**Evaluation:** The first model from the above table is the recommended model; it has the highest trainingh and testing accuracu and ROC of 0.79. This data is heavily imbalanced with 88% of 0s and 11% 1s for the target variable 'y' which resulted in low ROC values. Class weights were applied and hyperparamater tuning with gridsearchcv was used. 
