# Customer information predicts bank marketing success

![image](https://github.com/7ksravan/BerkAI/blob/main/images/17%20term%20deposit.jpg)

## Summary
Bank Marketing data for getting clients to make Long Term Deposits reveals customer information is crucial (than even marketing campaign and prevailing economic environment) to achieving higher rates of positive response to marketing campaign.

## Links
[Jupyter Notebook](https://github.com/7ksravan/BerkAI/blob/main/BerkAI_Customer_information_predicts_bank_marketing_success.ipynb)

## Overview

The data is related with direct marketing campaigns (phone calls) of a Portuguese banking institution. Performing detailed classification modeling on this dataset is an opportunity to understand the 4 models specified (Logistics Regression, K-nearest Neighbors, Decision Trees, Support Vector Classifer) as well as understanding the specifics involved in modeling and finetuning for this and similar classification problem solving use cases.

## Problem Statement

The **Business Objectives** is 2 folds:

1) how to optimize the banking campaign strategy to maximize client response
   
2) Which target customer groups are more likely to respond to the campaign and end up making a Term Deposit

The **Machine Learning objective** is:

to find the best classifier among the 4 specified classifier that have the best accuracy, precision, recall & F1 scores 

## Data
Data source: https://archive.ics.uci.edu/dataset/222/bank+marketing

Data information: PHONECALL marketing campaigns data of a Portuguese banking institution in trying to get clients make TERM DEPOSITS.

Data description:

The Data comprises of 3 components:

1) Client Data: personal and demographic data of the client who the campaign contacted
   
client: age, client: job, client: marital, client: education, client: default status, client: housing, client: loan

2) Marketing Campaign information: mode of communication, frequency of communication, period of communication
   
mark: contact, mark: month, mark: contact day_of_week, mark: duration, mark: campaign, mark: pdays, mark: previous, mark: poutcome

3) Data pertaining to prevailing economic situation at the time of the campaign
   
eco: ecovarrate, eco: cpi, eco: confindex, eco: euribor3m

## Report

### Data Preparation

 1. Data columns were curated - SIR curation - Sorting, Irrelevant column removal, Renaming
    
 2. Data row issues were handled - DON curation - 12 duplicates removed, some outliers removed, no nulls
    
 3. Data data special issues were handled

### Exploratory Data Analysis (EDA)

4.  EDA provided key insights to data and their interrelation.
  
   For example, below is a 2D PCA of the 2 classes Client Response Yes, Client Response No. With a PCA preserved variance of just 67%, it is intuitive that there is clear class separation in 2D PCA

  ![image](https://github.com/7ksravan/BerkAI/blob/main/images/17pca2D.png)
    
### Metrics & Baselining

 5. Metrics for this classification problem:
    1. Recall
    2. Precision
    3. F1 score
    4. Training Accuracy
    5. Test Accuracy

 6. High Benchmark Baselining:

I am taking the average scores obtained by running 10 out-of-box scikit learn models as a higher benchmark for my models to beat

Below are the Baseline Models details and scores

![image](https://github.com/7ksravan/BerkAI/blob/main/images/17baseline.png)

### Feature Engineering

7. Two new Economic Feature was engineered from the 5 original Economic features since there are highly correlated. Total preserved variance was 89.08%
   
8. No Feature selection was carried out although Chi Square statistical analysis was performed
   
9. Feature Scaling was done: numerical features via MinMax Scaler & categorical features via Ordinal Encoder

### Model Engineering

10. Models for this Assignment:

    1. Logistic Regression
    2. K Nearest Neighbors
    3. Decision Tree
    4. Support Vector Machine Classifier

11. Best Parameters were found out for the models by running GridSearch. Refer to Jupyter Notebook for details

### Evaluation & Results Discussion
    
12. A final evaluation was run for all the models with best parameters
   
 ![image](https://github.com/7ksravan/BerkAI/blob/main/images/17evalscorestable.png)

13. Classifier Models: Scoring Comparison

     1. Decision Tree is the best performing model with the highest scoring in precision, recall and F1 score
     2. Logistics Regression is a close second with the highest Test accuracy but behind Decision Tree in precision, recall and F1 score
     3. KNN performed reasonably well but fell behind in recall score that dragged down the F1 score too
     4. SVC score is not good and much below the baseline score
     
![image](https://github.com/7ksravan/BerkAI/blob/main/images/17score.png)
    
14. Classifier Models: performance comparison

SVC is the most time consuming and computationally expensive of all models as demonstrated below. It took ~25 minutes to run 2 iterations of SVC. While all other models ran ~16-20 iterations in least than 2 minutes. Part of the bad score of the SVC is probably because I could not perform finetuning.

![image](https://github.com/7ksravan/BerkAI/blob/main/images/17runtime.png)

15. **Feature Importance**

Feature Importance was arrived by ranking features by:

   1. Chi Square statistical score 
   2. Logistic Regression coefficient
   3. Decision tree feature importance

![image](https://github.com/7ksravan/BerkAI/blob/main/images/17featimp.png)

I calculated the cumulative **weighted ranking** of all the ranking to get insights into the most important features

Interestingly the customer profile ends up being the most important predictor of the Marketing Campaign success.
Customers information like job info, housing & loan status and age see to be more telling of the chances of them making a Term Deposit than even the marketing campaign and prevailing economic situation. This is intuitive if we think of assume the marketing campaign is already fairly standardized and optimized

The second tier of features that seem to be important are the marketing features like time, mode and frequency of communication. Interestingly the month of the year seems to have an important bearing on the prediction. If the chances of success are high in particular months, it might be a good strategy to cyclically focus more on Term Deposit marketing in a particular period of the year while focussing on other products during the other periods of the year.
    
15. **Lessons Learnt:** Dimensionality Reduction

 I did a quick evaluation and I can confirm there is no difference in scores between the running the models with the original 5 economic features and with the 2 PCA features arrived by merging those features. This makes intutive sense since the PCA information retention is ~90%. While this specific problem set was not too big and contained only 21 features, this should a helpful pointer to leverage Dimensionality reduction in future on datasets with huge number of features
    
16. **Future Work**
    
     1. Do further deep dive into features that were deemed as important in this exercise
     2. Perform further EDA & Feature engineering on Marketing Campaign features
     3. Outlier removal resulted in loss of number of records with 'No' Client Response, which was already an underrepresented class. Future work can evaluate other ways of handling outliers
