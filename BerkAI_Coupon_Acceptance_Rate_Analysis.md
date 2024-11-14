# Coupon Acceptance Rate Analysis
![image](https://github.com/7ksravan/BerkAI/blob/main/images/5carryout.png)

## Summary
Deep Dive of customer coupon data reveals highest coupon acceptance among specific occupation times and when the coupon give is for a carry-out or cheaper restaurant

## Links
[Jupyter Notebook](https://github.com/7ksravan/BerkAI/blob/main/BerkAI_Coupon_Acceptance_Rate_Analysis.ipynb)

## Overview & Data

The data is from a survey conducted via Amazon Mechanical Turk to evaluated drivers acceptance or rejection for different types of coupons based on various driving scenarios, like destination, time, weather, and passengers. Responses are labeled to indicate acceptance (Y=1) or rejection (Y=0). The goal is to predict coupon acceptance. The provided data had ~12600 records with 8 numerical features and 18 categorical features. 1 almost empty feature was deleted and duplicates/nulls removed from rest of the data

## Insights from my Analysis

 1. Overall coupon acceptance rate was 57%
    
 2. For coupons provided for Bars, acceptance rate was 41%
    
 3. For coupons provided for Bars, there is a huge difference in acceptance rates among Bar frequenters (76%) and people who visit Bar less frequently (37%)
    
 4. Coupon acceptance rate is higher when weather is good (Sunny) than when weater is bad (Snowy, Rainy)
    
 5. Coupon acceptance rate is much higher among students
    
 6. Coupon acceptance rate is much higher when the coupon is provided for a place which is in the direction of the driver's travel
    
 7. Coupon acceptance rate is higher for coupons given in the afternoon (2PM)
    
 8. Deep dive analysis reveals highest acceptance rates for coupons given to carry outs and cheaper restaurants
    
![image](https://github.com/7ksravan/BerkAI/blob/main/images/5coupontype.png)

 9. Occupation seems to be a big predictor of coupon acceptance. People from specific occupation accept coupons much more than others

**value types with highest coupon acceptance**

![image](https://github.com/7ksravan/BerkAI/blob/main/images/5accrateall.png)
    
 10. Further deep diving of carry out coupon data reveals 100% acceptance among people from Building & Grounds Cleaning & Maintenance occupation. There is almost 100% acceptance among certain occupations for carry out coupons

**value types with highest CARRYOUT coupon acceptance**

![image](https://github.com/7ksravan/BerkAI/blob/main/images/5accratecarryout.png)

## Future Work:

1. Accessing granular data behind this dataset for further analysis (ex: some data is in bins. it would be interesting to look at the actual numbers)
2. Classification and clustering analysis of this data
