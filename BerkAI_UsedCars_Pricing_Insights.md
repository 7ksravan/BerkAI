# Used Car Pricing Insights

## Summary
Although the Regression modeling in this exercise reveals the somewhat predictive ability of the car Year, Odometer reading and manufacturer name, the poor accuracy of models reveals the need for powerful feature engineering techniques to be applied for the accuracy of models to be improved

## Links
[Jupyter Notebook](https://github.com/7ksravan/BerkAI/blob/main/BerkAI_UsedCars_Pricing_Insights.ipynb)

## Overview
This dataset contains ~426K records of Used Cars Sales. The goal of the exercise is to gain meaningful pricing insights by applying Regression modeling techniques.

## Business Goal
Get pricing insights for used cars to determine procurement pricing and strategy, sales pricing and statrgy, and car segments to focus for maximizing revenue

## Technical Objectives from data perspective
1. Exploratory Data Analysis for getting insights into data features, their inter-relationships and influence on pricing
2. Data Curation to handle data discrepancies including duplicates, outliers, nulls and special issues
3. Appropriate feature scaling techniques for numerical and categorical features
4. Modeling and hyperparameter tuning for building Regression models that determine pricing accuracy based on features
5. Appropriate Evaluation metrics for measuring efficiencies of model

## Report & Insights

### Modeling
1. The dataset was evaluated with 4 models Linear Regression, Lasso Regression, Ridge Regression and Random Forest.
2. Random Forest was the best performing model among all 4 models
3. Linear Regression, Lasso and Ridge performed very poorly for this dataset even with hyperparameter tuning
4. Random Forest modeling took significant computational resource and was time consuming. Finetuning for Random Forest had to be interupted because it was taking too long.

![image](https://github.com/7ksravan/BerkAI/blob/main/images/11eval.png)
![image](https://github.com/7ksravan/BerkAI/blob/main/images/11score.png)
   
### Correlations
5. There is STRONG negative correlation between Year and Odometer, which is intuitive. The older the year the higher the mileage
6. There is WEAK positive correlation between Price and year
7. There is WEAK negative correlation between Price and Odometer reading

![image](https://github.com/7ksravan/BerkAI/blob/main/images/11corr.png)
   
### To the client
8. Based on Random Forest feature importance Year, Odometer, Manufacturer and Cylinder turned out to be the most significant features
9. The client is asked to present any further data associated with the used cars that might be helpful in better modeling
10. Below are the features importance ranking for the client's reference

![image](https://github.com/7ksravan/BerkAI/blob/main/images/11featimp.png)

## Future Work
1. The poor accuracy shows the need to improve the features by feature engineering
2. Model information was not used since the data needs complex manupulation to extract meaningful information
3. These efforts will be taken up in my Capstone Project for which I shall use the same dataset

