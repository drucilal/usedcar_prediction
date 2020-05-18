<h2>Predicting Used Car Sale Prices using Machine Learning: Project Overview<h2>

  
![Image of cars](pictures/cars.png)

![Source](https://www.google.com/imgres?imgurl=https%3A%2F%2Fcdn.arstechnica.net%2Fwp-content%2Fuploads%2F2020%2F04%2FGettyImages-503375934.jpg&imgrefurl=https%3A%2F%2Farstechnica.com%2Fcars%2F2020%2F04%2Fnew-vehicle-sales-fell-by-40-50-percent-in-march-thanks-to-covid-19%2F&tbnid=XHEiz2USpny80M&vet=12ahUKEwiAmt-sqr7pAhUNSN8KHZdbA0oQMygBegUIARCaAg..i&docid=UMa4Jm9HmPweWM&w=4000&h=2667&q=car%20sale&ved=2ahUKEwiAmt-sqr7pAhUNSN8KHZdbA0oQMygBegUIARCaAg)

- Using the Craiglist used car dataset from Kaggle, the aim of this project was to determine the optimal car price based on the various features provided.
- Optimized Lasso, Elastic Net, XG Boost, Random Forest, and a Stacked Model using Gridsearch CV to reach the best model. 

Code and Resources Used:
---
Python Version: 3.7
Packages: pandas, numpy, sklearn, matplotlib, re, scipy,sklearn, mlxtend, and xgboost
Dataset: https://www.kaggle.com/austinreese/craigslist-carstrucks-data

Data Cleaning
---
After reading in the data, I needed to clean it up so that it was usable for the model.
Following Changes: 
- Fill in missing values with 'unknown'
- Removed rows with out a price 
- Changed Column Types 
- Took the logarithmic of both the price and odometer to form a normal distribution.

![Image of Price](pictures/price_log.png)

![Image of Mileae](pictures/mileage.png)

EDA
--
- Looked the distribution and value counts for the various categorical variables. Below are a few highlights:

![Image of Features](pictures/categoryeda.png)


Model Building
--
First, I took 15% of the dataset to use for model building. I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 35%. 
I tried six models and evaluated them using the Mean Squared Error and the R-Squared Score. I chose both because it is relatively easy to interpret. 
Models: 

<img src ='pictures/models.png' width = '300' height = '300'>

Model Performance 
--
The XG Boost model far outperformed the other approaches on the test and training sets. It could possibly be improved further with hyper-parameter tuning. Thus, XGBoost was able to predict 76% of the variation of car sale prices.

<img src ='pictures/xgboost.png' width = '400' height = '250'>
