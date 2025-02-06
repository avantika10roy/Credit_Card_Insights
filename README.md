# Data_Analysis
### Problem Statement
This case study provides comprehensive exploratory data analysis on **Credit Card Insights** prediction. In this dataset, we have a demographic and employment data of individuals, including details such as age, education, occuoation and marital status, among other features. 

This analysis explores key trends, factors influencing individual income level, socio-economic patterns and influences of various personal and work-related factors.

### Objective
To perform exploratory data analysis (EDA) and develop models to identify the most significant factors affecting income, assess various feasible models, and determine the most appropriate model for predicting income levels.

### Dataset
##### **Dataset Overview:**
* The dataset contains 32,561 rows and 15 columns.
* The target variable is income, which has two categories: <=50K and >50K.
* The dataset reflects a diverse population with varying ages, education levels, financial outcomes, and work hours, indicating a mix of individuals with diverse backgrounds and circumstances.

##### Variables in the Dataset:
|    Feature       |  Description                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------|
|   **age**        |  The age of the individual.                                                                                       |
|**workclass**     | Type of employment (e.g., Private, Government, Self-Employed).                                                    |
| **fnlwgt**       | Final sample weight, representing how many people the individual represents.                                      |
|**education**     | The highest level of education attained (e.g., Bachelors, HS-grad).                                               |
|**education-num** | Numerical representation of education level.                                                                      |
|**marital-status**| The marital status of the individual (e.g., Married, Never-married).                                              |
|**occupation**    | The individual’s occupation category (e.g., Exec-managerial, Craft-repair).                                       |
|**relationship**  | The relationship status within a family (e.g., Husband, Wife, Not-in-family).                                     |
|**race**          | The race of the individual (e.g., White, Black, Asian).                                                           |
|**sex**           | Gender of the individual (Male, Female).                                                                          |
|**capital-gain**  | Capital gains from investments.                                                                                   |
|**capital-loss**  | Losses from investments.                                                                                          |
|**hours-per-week**| The number of hours worked per week.                                                                              |
|**native-country**| The country of origin for the individual.                                                                         |
|**income**        |Binary target variable representing whether the individual's income is greater than or less than $50,000 per year. |

### Methodology
* **Data Collection:** Data was sourced from internal sales records.
* **Data Preparation:** Missing values were handled, duplicates removed, and data was standardized for analysis.
* **Tools Used:** Python (Pandas, Matplotlib, Seaborn, NumPy) for data manipulation, visualization, and statistical analysis.

### Exploratory Data Analysis
###### Skewness and Kurtosis
|                 | Skewness | Kurtosis |
|-----------------|----------|----------|
|  Age            | 0.49     | -0.45    |
| Final Weight    | 0.63     | 0.26     |
| Education Years | -0.17    | 0.38     |
| Capital Gain    | 4.94     | 26.25    |
| Capital Loss    | 29.66    | 931.56   |
| Hours per Week  | -0.35    | 1.44     |

###### Insights on Skewness
The right-skewed distributions for age, weight, capital gain, and capital loss suggest a few individuals with very high values, while education years show a balanced distribution, and the slight left skew in work hours indicates most individuals are employed full-time.

###### Insights on Kurtosis
The data shows light-tailed distributions for age, weight, and education, indicating consistency, while capital gain and loss have heavy tails, suggesting a few individuals experience extreme financial outcomes.

### Univariate Analysis
On performing **Univariate Analysis**, the following insights were drawn:

* The dataset is imbalanced, with significantly more individuals earning less than 50k compared to those earning more than 50k.
![image](https://github.com/user-attachments/assets/67def782-befb-4f0b-b368-c883ff88265c)

* Younger individuals are more likely to earn, with a higher concentration of people in the 20-50 age range. 

* Most individuals have minimal capital gain or loss and work an average of 40 hours per week. 

* A high concentration of earning individuals have 9 years of education.
![image](https://github.com/user-attachments/assets/4a417a5d-47c1-4161-91da-114af7e0e822)

* The dataset contains several outliers, like individuals with unusually high ages, abnormal education years going as low as 4, extreme capital gains, and abnormally low or high work hours, suggesting potential data quality issues or exceptional cases.

* Most individuals employed in the private sector.

* There is a trimodal distribution in education (bachelor’s, college, and high school), and a significant number of married or previously married individuals.

* There is also a predominance of white males, primarily from the United States.
![image](https://github.com/user-attachments/assets/784ab8be-d606-47b9-92d6-17b72d5ec842)

### Bivariate Analysis
On performing **Bivariate Analysis**, the following insights were drawn:

* The analysis reveals that middle-aged individuals are more likely to earn above 50K, higher education and capital gains are linked to greater income, and individuals working more than 40 hours per week are more likely to earn over 50K, highlighting the importance of age, education, and work hours in income levels.
![image](https://github.com/user-attachments/assets/512302f5-90f9-4eea-8406-e46bd9f285bd)

* The dataset shows that government and self-employed workers, those with higher education, executive roles, married individuals, and certain racial or national groups tend to earn more than 50K, while males generally earn more than females, and income disparities are observed based on occupation and marital status.
![image](https://github.com/user-attachments/assets/8675444a-7d92-4809-9c71-271da81e8768)

###### ANOVA Test
|Income vs      | Statistics | P-Value |
|---------------|------------|---------|
| Age           |  1813.08   |  0.00   |
| Final Weight  |     2.48   |  0.115  |
| Education Num |  3368.92   |  0.00   |
| Capital Gain  |  3964.84   |  0.00   |
| Capital Loss  |     8.22   |  0.004  |
| Hours per Week|  1675.44   |  0.00   |

* The analysis highlights that age, education, capital gains, capital losses, and hours worked per week are significant predictors of income, while final weight does not significantly influence income levels. This suggests targeted interventions in education and financial strategies could help address income disparities.

###### Chi-Square Test
|Income vs      | Statistics | P-Value |
|---------------|------------|---------|
| Work Class    |   874      |  0.00   |
| Education     |  3597.51   |  0.00   |
| Martial Stat  |  5838.34   |  0.00   |
| Occupation    |  3393.44   |  0.00   |
| Relationship  |  5984.37   |  0.00   |
| Race          |   293.17   |  0.00   |
| Sex           |  1313.63   |  0.00   |
| Native Country|   246.88   |  0.00   |

* The analysis reveals that workclass, education, marital status, occupation, relationship, race, sex, and native country all significantly influence income levels, suggesting the importance of these factors in shaping economic outcomes.

### Multivariate Analysis

* The **correlation matrix** reveals key relationships, such as the positive correlation between education and years of schooling, and the strong negative correlation between relationship type and sex.
![image](https://github.com/user-attachments/assets/42546c4e-efc4-46b2-8782-40cfcca10b3f)

* The **pairplot** highlights that older individuals (40-60) are more likely to earn above 50K, while younger individuals tend to earn less. Higher education levels, longer work hours (over 40 hours), and significant capital gains/losses are all associated with higher income. However, there is no clear relationship between final weight (fnlwgt) and income.
![image](https://github.com/user-attachments/assets/029d7e58-659a-4720-8a37-244f36236234)

### Model Training on Imbalanced Data
|           | Logistic Regression |  KNN   | Decision Tree | Bernoulli NB |
|-----------|---------------------|--------|---------------|--------------|
| Accuracy  |    0.6790           | 0.7083 |    0.8549     |     0.7519   |
| Precision |    0.6934           | 0.6910 |    0.8498     |     0.7311   |
| Recall    |    0.6422           | 0.7534 |    0.8621     |     0.7969   |
| F1-Score  |    0.6667           | 0.7209 |    0.8559     |     0.7625   |
| RUC AOC   |    0.7681           | 0.7836 |    0.8549     |     0.7678   |

### Model Training on Balanced Data using SMOTE
|           | Logistic Regression |  KNN   | Decision Tree | Bernoulli NB |
|-----------|---------------------|--------|---------------|--------------|
| Accuracy  |    0.7969           | 0.7855 |    0.8036     |     0.7325   |
| Precision |    0.6183           | 0.5381 |    0.5566     |     0.4394   |
| Recall    |    0.2323           | 0.2666 |    0.5831     |     0.7269   |
| F1-Score  |    0.3376           | 0.3564 |    0.5695     |     0.5477   |
| RUC AOC   |    0.7324           | 0.6443 |    0.7250     |     0.7682   |

* Performing SMOTE has reduced the performance of the models significantly, so model is trained on unbalanced data.

### Feature Importance
![image](https://github.com/user-attachments/assets/9fce7fed-c67a-4ee8-96dc-25a520ca161e)

| Feature Number |  feature      | importance |
|----------------|---------------|------------|
|    7           | relationship  |   0.393504 |
|   10           | capital.gain  |   0.222015 |
|    4           |  education.num|   0.158504 |
|    0           |  age          |   0.088918 |
|   12           | hours.per.week|   0.049009 |
|    2           | fnlwgt        |   0.030515 |
|    6           |occupation     |   0.029461 |
|    1           | workclass     |   0.011040 |
|    3           | education     |   0.005820 |
|    8           | race          |   0.004028 |
|    9           |  sex          |   0.003053 |
|   13           | native.country|   0.002406 |
|    5           | marital.status|   0.001726 |
|   11           | capital.loss  |   0.000000 |

### Model Training (Decision Tree)
Decision Tree Model was selected as it has the highest performance score among other models.

##### Confusion Matrix
![image](https://github.com/user-attachments/assets/cf1132fb-0c17-4316-91fe-ef57e784eff8)

| Actual/Predicted | Positive | Negative |
|------------------|----------|----------|
| Positive         |  4255    |   374    |
| Negative         |   553    |   784    |

### Model Testing on Unseen Data
* **Model Accuracy on Test Set:** 0.84461

### Final Conclusions

* Predicted Income closely matches the Actual Income for the given test samples, with the majority of predictions being correct.
* The accuracy score on the test set is 0.8446, indicating that the model correctly classifies about 84.5% of the test data. This suggests a reasonably good fit, especially for an initial model, and reflects strong predictive power.
* The decision tree classifier performed well in predicting income categories (<=50K and >50K), achieving relatively high accuracy.
* Decision trees are known for handling both categorical and numerical data well, making them suitable for this dataset, which has a mix of feature types (e.g., age, education, workclass).
