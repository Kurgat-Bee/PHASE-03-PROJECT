## Overview
In Tanzania, water wells become non-functional due to various factors such as quantity of water available in the wells, the source of the water feeding the well and the management group.
Identifying non-functional wells will help prioritize maintenance efforts and improve water infrastructure planning. 
This analysis aims to develop a machine learning classifier that predicts the condition of water wells based on features like water point type, construction year, and other factors. 
The model will categorize wells as functional or non-functional.
## Business Objectives
- Develop a classification model to predict whether a well is functional or non-functional using historical data.
- Implement and compare multiple algorithms to identify the most effective model for well functionality prediction.
- Improve prediction accuracy through feature selection, hyperparameter tuning, and handling class imbalances.
## Business Questions
- What factors contribute most to well failures?
- Which regions have the highest concentration of non-functional wells?
- How does the construction year affect well failure rates?
## Methods 
The methods used in the analysis are as follows:
Data Collection, Exploratory Data Analysis, Statistical Analysis - correlations, Linear regression, Logistics regression, Random Forest, Decision Trees, K-Nearest Neighbour
## Insights from the analysis and modeling
This histogram illustrates the distribution of well construction years, revealing a significant rise in well development since the 1960s, with a peak in the late 2000s.

![image](https://github.com/Kurgat-Bee/PHASE-03-PROJECT/blob/f5067e212da8d41f35937ff06febf97d2ddf48f3/images/Histogram%20of%20construction%20of%20wells.png)

This plot shows well status by location. Non-functional wells are spread across the region but are more concentrated in the south eastern parts.

![image](https://github.com/Kurgat-Bee/PHASE-03-PROJECT/blob/84fbfd97ae32f7e0f51d10e4c239279f4abb9a56/images/Well%20status%20by%20location.png)

Well performance over construction years. Older wells tend to have a higher proportion of non-functional status. More recent wells are more likely to be functional.


![image](https://github.com/Kurgat-Bee/PHASE-03-PROJECT/blob/f5067e212da8d41f35937ff06febf97d2ddf48f3/images/Well%20performance%20over%20the%20years.png)

Comparison between model performances. Random Forest is the best choice to maximize predictive performance and correctly classify as many wells as possible.

![image](https://github.com/Kurgat-Bee/PHASE-03-PROJECT/blob/f5067e212da8d41f35937ff06febf97d2ddf48f3/images/Model%20comparison.png)

Comparison of the confusion matrices of the different models. Random Forest (Optimized) is the most reliable model, making it the best choice for minimizing misclassifications.

![image](https://github.com/Kurgat-Bee/PHASE-03-PROJECT/blob/04707863105b54c6a4b56cd3aecc7ee59e2f8abe/images/Confusion%20matrices.png)

## Conclusions
- The Optimised Random Forest model stands out as the best performing model with:

Accuracy-85.38%

Recall-92.39%

Precision-85.17%

F1-score-88.63%.

- The best parameters after tuning are:

max_depth: 20

min_samples_leaf: 1

min_samples_split: 5

n_estimators: 300

- The following features stand out as the leading predictors to the functionality of a well: 'quantity', 'waterpoint_type', 'source', 'construction_year', 'payment_type', 'management_group'.
  
- There is a high cluster of non-functional wells in the south east of Tanzania. The government should consider allocating resources towards repair and maintenance in this area, to ensure the residents get good water supply.
  
- More recent wells are more likely to be functional than aged wells. The presence of non-functional wells in all time periods highlights that factors beyond age also play a role in well performance.


## Recomendations

- Once the most influential factors affecting well functionality are identified, analyze their impact—do they contribute positively or negatively? Understanding these relationships will help the government of Tanzania make informed investment decisions to enhance well longevity.

- Instead of using construction year as a standalone feature, create a new variable, "well age", to better capture the patterns related to functionality. This could improve the model's ability to detect trends over time.

- The model could be further analysed as a ternary classification problem to include the 'functional but needs repair' as a category on its own. This will help the client be able to plan for maintenance early enough before the well condition deteriorates to the 'non-functional' category.
