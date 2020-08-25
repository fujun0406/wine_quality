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

Based on the rule, we can see most wine quality label would be good and average in Figure 5.

<img src="/image/quality_label.png" width="500"/>

<em>Figure 5: The distribution of wine quality label.</em>

We can notice that the correlation plot (Figure 6) shows:

* alcohol show the postive correlation values with wine quality
* chlorides, volatile_acidity and density as a negative correlation with wine quality
* total_sulfur_dioxide and free_sulfur_dioxide have high correlation
* total_sulfur_dioxide and bonus_sulfur_dioxide have high correlation
* total_sulfur_dioxide and wine have high correlation

<img src="/image/correlation.png" width="500"/>

<em>Figure 6: The correlation.</em>

### Preprocessing

## Building Models

### Model Comparison
### Variable Selection

## Result

## Discussion
