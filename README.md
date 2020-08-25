# Project - Wine Quality

## Contents
* [Overview](#overview)
* [Exploratory Data Analysis](#exploratory-data-analysis)
    * [Data](#data)
    * [Preprocessing](preprocessing)
* [Building Models](#building-models)
    * [Model Comparison](#model-comparison)
    * [Variable Selection](#variable-selection)
* [Result](#result)
* [Discussion](#discussion)

## Overview
We will be using data exploring the quality and physicochemical characteristics of Portuguese Vinho Verde wine. These data come from a paper published by Cortez, et al. in Decision Support Systems in 2009. The purpose of this project is predicting the quality of the wine based on physicochemical characteristics.

* Utilizing machine learning techniques including random forest, decision tree and logistic regression.
* Measuring which model is more suitable for this dataset.
* Trying to do variable selection in order to simplify model.

## Exploratory Data Analysis

### Data
In this dataset, we have 13 features in Table 1 which consist of continuous variabls and categorical variables and total samples is 3000. There is no missing values in the dataset.

<table>
<tr><th>Variabls </th><th>Variables</th></tr>
<tr><td>
  
| Column | Non-Null Count | Dtype |
|--|--|--|
| quality |                3000 non-null | int64 |
| wine |                   3000 non-null | object |
| fixed_acidity |          3000 non-null | float64 |
| volatile_acidity |       3000 non-null | float64 |
| citric_acid |            3000 non-null | float64 |
| residual_sugar |         3000 non-null | float64 |
| chlorides |              3000 non-null | float64 |

</td><td>

| Column | Non-Null Count | Dtype |
|--|--|--|
| free_sulfur_dioxide | 3000 non-null | float64 |
| total_sulfur_dioxide | 3000 non-null | float64 |
| density | 3000 non-null | float64 |
| p_h | 3000 non-null | float64 |
| sulphates | 3000 non-null | float64 |
| alcohol | 3000 non-null | float64 |

</td></tr> </table>

<em>Table 1: The attribute for datasets of dataset.</em>

We can get descriptive statistic of quality perspective in Figure 2 which is part of table and based on the description we can know the following characteristics.

* The higher the quality, the higher the average alcohol concentration
* The chlorides and volatile_acidity are less present and presented smaller standard deviation in wines of higher quality.
* The free_sulfur_dioxide is higher with higher quality, but their standard deviation decrease with the increase the quality.
* Higher quality has less fixed_acidity, but the standard deviation slightly increase with the increase the quality.
* Lower levels of volatile_acids in wines with high quality ratings

<img src="/image/table.JPG" width="820"/>

<em>Figure 2: The descriptive statistic of dataset.</em>

We can see that 75.1% is white wine and 24.9% is red wine in Figure 3.

<img src="/image/wine_proportion.png" width="500"/>

<em>Figure 3: The distribution of wine.</em>

In Figure 4, most wine quality is 5 and 6.

<img src="/image/quality.png" width="500"/>

<em>Figure 4: The distribution of wine quality.</em>

According to the classification rule, wine can be classified to four categories: `excellent`, `good`, `average`, `poor`. 
The categorization must occur using the following table:

| Quality Category  | Quality Score |
|-------------------|:-------------:|
| Excellent         | > 7           |
| Good              | 6             |
| Average           | 5             |
| Poor              | < 4           |  

<em>Table 2: The classification rule.</em>

Based on the rule, we can see most wine quality label would be good and average in Figure 5.

<img src="/image/quality_label.png" width="500"/>

<em>Figure 5: The distribution of wine quality label.</em>

We can notice that the correlation plot (Figure 6) shows:

* alcohol show the postive correlation values with wine quality
* chlorides, volatile_acidity and density as a negative correlation with wine quality
* total_sulfur_dioxide and free_sulfur_dioxide have high correlation
* total_sulfur_dioxide and bonus_sulfur_dioxide have high correlation
* total_sulfur_dioxide and wine have high correlation

<img src="/image/correlation.png" width="700"/>

<em>Figure 6: The correlation plot.</em>

### Preprocessing
Based on previous analysis, we know data is imblanced for quality class. In order to prevent imblanced data to discard useful information. We resample the data from each quality class for training dataset and process training set and testing set.

## Building Models
In this project, we try to use random forest, decision tree and logistic regression to explore this datset because this dataset is high dimensional input. 

### Model Comparison
We use randome forest, decision tree and logistic regression model to fit training dataset and the results of validation dataset show as following. We can see that the performance of Random Forest is better than others. We will employ this method as following.

#### Random Forest

| | precision | recall | f1-score | support |
| --- | --------- | ------ | -------- | ------- |
| 0 | 0.90 | 0.98 | 0.94 | 257 |
| 1 | 0.69 | 0.64 | 0.66 | 229 | 
| 2 | 0.62 | 0.55 | 0.58 | 264 | 
| 3 | 0.78 | 0.86 | 0.82 | 272 | 
| accuracy |  |  | 0.76  | 1022 | 
| macro avg | 0.75 | 0.76 | 0.75 | 1022 | 
| weighted avg | 0.75 | 0.76 | 0.75 | 1022 | 

<em>Table 3: The reslut of Random Forest.</em>

<img src="/image/rf.png" width="400"/>

<em>Figure 7: The confusion matrix for Random Forest.</em>

#### Decision Tree

| | precision | recall | f1-score | support |
| --- | --------- | ------ | -------- | ------- |
| 0 | 0.82 | 0.87 | 0.85 | 257 |
| 1 | 0.55 | 0.59 | 0.57 | 229 | 
| 2 | 0.50 | 0.42 | 0.46 | 264 | 
| 3 | 0.72 | 0.74 | 0.73 | 272 | 
| accuracy |  |  | 0.66  | 1022 | 
| macro avg | 0.65 | 0.66 | 0.65 | 1022 | 
| weighted avg | 0.65 | 0.66 | 0.65 | 1022 | 

<em>Table 4: The reslut of Decision Tree.</em>

<img src="/image/dt.png" width="400"/>

<em>Figure 8: The confusion matrix for Decision Tree.</em>

#### Logistic Regression

| | precision | recall | f1-score | support |
| --- | --------- | ------ | -------- | ------- |
| 0 | 0.60 | 0.66 | 0.63 | 257 |
| 1 | 0.38 | 0.35 | 0.37 | 229 | 
| 2 | 0.39 | 0.29 | 0.33 | 264 | 
| 3 | 0.54 | 0.67 | 0.60 | 272 | 
| accuracy |  |  | 0.50  | 1022 | 
| macro avg | 0.48 | 0.49 | 0.48 | 1022 | 
| weighted avg | 0.48 | 0.50 | 0.49 | 1022 | 

<em>Table 5: The reslut of Logistic Regression.</em>

<img src="/image/lg.png" width="400"/>

<em>Figure 9: The confusion matrix for Logistic Regression.</em>

### Variable Selection
There are some variables which have high correlation with each other. If we use those vairbles, it may cause multicollinearity. In order to prevent this issue, we use feature importances at first to select variables.

<img src="/image/importance.png" width="600"/>

<em>Figure 10: The importance of variables.</em>

Because the variable of wine has low importance in the model, we decide to remove this feature from the model. The variable of total_sulfur_dioxide have high correlation with free_sulfur_dioxide and bonus_sulfur_dioxide so try to remove this feature from the model to prevent multicolinearity.

After that, we employ selected variables to fit randome forest model again and the result shows as following.

| | precision | recall | f1-score | support |
| --- | --------- | ------ | -------- | ------- |
| 0 | 0.89 | 0.98 | 0.93 | 257 |
| 1 | 0.70 | 0.65 | 0.67 | 229 | 
| 2 | 0.60 | 0.51 | 0.55 | 264 | 
| 3 | 0.77 | 0.85 | 0.81 | 272 | 
| accuracy |  |  | 0.75  | 1022 | 
| macro avg | 0.74 | 0.75 | 0.74 | 1022 | 
| weighted avg | 0.74 | 0.75 | 0.74 | 1022 | 

<em>Table 6: The reslut of Random Forest using selected variables.</em>

<img src="/image/rf2.png" width="400"/>

<em>Figure 11: The confusion matrix for Random Forest using selected variables.</em>

## Result
In this model we take the features including 'fixed_acidity', 'volatile_acidity', 'citric_acid', 'residual_sugar', 'chlorides', 'free_sulfur_dioxide', 'density', 'p_h', 'sulphates', 'alcohol' and 'bonus_sulfur_dioxide'. We use random forest as our algorithm to construct the model.

We use number to represent quality class (poor: 0, average: 1, good: 2, excellent: 3) The performance of the testing dataset as following, we can see that for classifing average, good and excellent the accuracy is more than 50%. In terms of poor, though wine may be misclassfied, most of them would be average and good.

| | precision | recall | f1-score | support |
| --- | --------- | ------ | -------- | ------- |
| 0 | 0.24 | 0.34 | 0.28 | 44 |
| 1 | 0.67 | 0.66 | 0.66 | 325 | 
| 2 | 0.61 | 0.55 | 0.58 | 429 | 
| 3 | 0.56 | 0.63 | 0.60 | 202 | 
| accuracy |  |  | 0.60  | 1000 | 
| macro avg | 0.52 | 0.55 | 0.53 | 1000 | 
| weighted avg | 0.60 | 0.60 | 0.60 | 1000 | 

<em>Table 7: The reslut of Random Forest for testing dataset.</em>

<img src="/image/test.png" width="400"/>

<em>Figure 12: The confusion matrix for Random Forest for testing dataset.</em>

## Discussion
In this projerct, we only discuss three machine learning models but it still provides many information about classifying wine quality. Compared with decision tree and logistic regression, random forest is more suitable in this dataset. As far as for future research, we can try deep learing methods to outperform model.
