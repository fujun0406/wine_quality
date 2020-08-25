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
<tr><th>Continuous Variabls </th><th>Categorical Variables</th></tr>
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

### Preprocessing

## Building Models

### Model Comparison
### Variable Selection

## Result

## Discussion
