# Coffee-Case-Study
Using Machine Learning to make informed business decisions about whether customers will purchase new coffee selection offered. 

![image](https://github.com/user-attachments/assets/43eb2a49-f249-4b48-b869-d8c83bd969d9)

## Overview

## Predicting Demand for Hidden Farm Coffee using Machine Learning
RR Diner Coffee, a specialty coffee company, operates three retail locations—two in Europe and a flagship store in the USA. They sell high-quality coffee beans (in bulk by the kilogram) and a curated selection of coffee equipment and branded merchandise.

All products are quality-assessed at the U.S. flagship location before being distributed to international customers—primarily café owners in major cities like New York, Paris, London, Hong Kong, Tokyo, and Berlin. Shipping costs increase with distance from the U.S., adding complexity to the supply chain.

The company is now facing a critical decision: whether to partner with a legendary but remote Chinese coffee producer, known as the Hidden Farm. Rumors suggest their beans are unlike any other—boasting tasting notes of lychee, dark chocolate, and apple juice-like sweetness. However, the partnership is risky due to high costs and uncertain customer demand.

This data science project aims to support RR Diner Coffee’s decision-making by building a machine learning model (decision tree) that predicts the number of units of Hidden Farm coffee that would likely be purchased by the company’s most loyal customers.

## This model could play a key role in reducing business risk and helping RR Diner Coffee navigate a high-stakes investment in a premium product during a challenging time for the specialty coffee industry.



## Dataset

This dataset contains information from customers at a coffee chain (RR coffee diner) , including customer: Age, Gender, number of coffeebags purchased per year, amount spend last week, amount spent last month, salary, Distance from coffee shop, their decision on buying new coffee selection offered. 

Dataset is composed of 702 rows and 9 columns. 



# Methodology
The project follows these key steps:

1. Data Preprocessing: Cleaning and preparing the data for analysis.
2. Exploratory Data Analysis: Exploring relationship between features and using visualizations techniques to discover insights.
3. Feature Engineering: Selecting and transforming relevant features to enhance model performance. 
4. Model Development: Implementing machine learning algorithms to predict lung cancer risk levels (Low, Medium, High).
5. Model Evaluation: Assessing the model's accuracy and reliability using appropriate metrics.


# 1) Data Preprocesssing:
In the part of the project I loaded the data and checked for duplicate values and null values. Furthermore I explored the data types and discovered that all were numeric with the exception of two. 

df.head() and df.columns are used to explore the feature of the dataset and begin developing questions to explore during EDA. 


# 2) Exploratory Data Analysis:

 ## Exploring the target variables 

 ## Distribution of money spent per month by customers at RR coffee diners

 <img width="461" alt="image" src="https://github.com/user-attachments/assets/f4785af7-e150-4a70-bed6-2a873f7c7047" />

 ## Observations:
 - For the most part data is normally distributed which means statistical methods such as T-test, Z-tests, Regression analaysis and Pearson Correlation can be used.


## Distance from coffee shop and Decision to try new potental selection of coffee

<img width="566" alt="image" src="https://github.com/user-attachments/assets/2786ccab-28ec-441d-9d18-027d9e0d3671" />

### Insights:
- Over 50% of customers who responded YES live 3 miles or less from a RR Diner. 

- Over 75% customers who responded NO live more than 5 miles from RR Diner. 


## Age, Salary and Decision to buy new potential coffee

<img width="719" alt="image" src="https://github.com/user-attachments/assets/c4b0a543-bb81-4695-ac09-1e3b281e3fd7" />


## Insights:
- Customers between ages 20-30 who make more than 40k a year were far more likely to answer YES to survey on buying hidden farm coffee. 
- Regardless of age, customers who make 20k or less are far more likley to answer NO to buying hidden farm coffee.


## Money spent week before survey and decision to buy new selection 

<img width="553" alt="image" src="https://github.com/user-attachments/assets/e38f9158-0ffe-483a-8a39-87f4af9c982e" />

### Insights:
- Over 75% of customers who responded YES spent more than $30 week before survey.

- Over 75% of customers who responded NO spent less than $35 week before survey.

### Exploring correlation between Salary, Distance and Decision to try new coffee selection

<img width="866" alt="image" src="https://github.com/user-attachments/assets/6bdf1310-c3dd-496f-9c74-343d7233e544" />

### Insights:
- Distance seems to be a key factor in indicating whether a customer responded YES or No on the survey. 
- The majority of customers who are less than 2 miles from RR coffee diner responded YES regardless of salary to buying hidden farms coffee. 
- Additionally customers were far more likely to respond NO on survey if they lived more than 4 miles away and had a salary of less than 40k. 


## Exploring how Salary plays a role in decision to purchase new potential selection of coffee

<img width="868" alt="image" src="https://github.com/user-attachments/assets/eb9fc77c-4cdb-4a12-abc9-cfa2d1b73a6f" />

### Insights:
- Every customer who responded YES to the survey makes over $75,000 per year and spent more than $150 the month before the survey. 
- Every single customer who spent more than $140 the week prior to survey answered YES to buying hidden farms coffee. 
- Majority of customers who spent less than $60 the week before survey answered NO to buying hidden farms coffee. 


### Comment:
- This information could also be used to impute null values of customers who did not respond to survey. 


 # 3) Feature Engineering:

- Creating categories of spenders (low spender, medium spender, high spender)

<img width="596" alt="image" src="https://github.com/user-attachments/assets/283df8de-f5c7-43a8-ba9f-a473eab4d215" />



# 4) Model Development:

## Models developed:

- Decision Tree - Entropy model - no max_depth
- Decision Tree - Gini impurity model - no max_depth
- Decision Tree - Entropy model - max depth 3
- Decision Tree - Gini impurity model - max depth 3
- Random Forest 


# 5) Model Evaluation: 
- Decision Tree - Entropy model - no max_depth: Accuracy = 0.9915966386554622
- Decision Tree - Gini impurity model - no max_depth: Accuracy = 0.9831932773109243
- Decision Tree - Entropy model - max depth 3: Accuracy = 0.907563025210084
- Decision Tree - Gini impurity model - max depth 3: Accuracy = 0.907563025210084
- Random Forest: Accuracy = 0.9663865546218487


## Conclusion
### Model Comparison Summary
After executing the Random Forest model, the results were nearly identical to those of my best-performing model (Model 4). While the Random Forest showed slightly higher metrics and was able to classify three new customers as "YES" for purchasing Hidden Farm Coffee, the overall predicted purchase percentage increased only marginally—remaining around 69.65%, which is still below the target threshold of 70%.


# My Recommendations for RR Diner Coffee Based on Decision Tree and Random Forest Analysis. 
- Based on the current data, I would advise RR Diner Coffee stakeholders not to proceed with the Hidden Farm deal at this time. The margin of uncertainty is too narrow, and the financial risk is too high given the minimal projected return.

- I recommend increasing marketing efforts within a 3-mile radius of each diner location. Customers living closer to the stores were significantly more likely to purchase Hidden Farm coffee. Targeted campaigns in these zones could help attract new loyal customers and boost future revenue.

- While this deal may not be ideal right now, it could become profitable in the future if the loyal customer base expands—especially within the high-conversion radius.

- Regardless of income level, proximity was a stronger predictor of purchase intent. Customers living within 3 miles were consistently more likely to buy Hidden Farm coffee.

 



