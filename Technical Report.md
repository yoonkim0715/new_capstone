# Rossmann Sales Prediction

## General Information

Rossmann was founded in March 17, 1972 in Germany and became the second largest drug store in Germany.
They had approximately 4,000 stores all over the Europe.  
I wanted to predict the the total sales of each store on a given day.

Throughout this project, I will predict sales price from Rossmann store. There are 1115 unique stores total in dataset and 4 different types of stores. There are 3 different kinds of assortment. The dataset also provides information about competitors including the distance from each store to their competitors, years and month when competitors entered their business. There are also various columns that are related to promotion, which can be informative with regards to a prediction of sales.

## Problem Statement

How to increase the total sales in rossmann stores, so that we can have more returns?

### Preprocessing and Exploratory Data Analysis

Both train and test data date features, therefore, I wanted to check if there's a trend in terms of sales. By checking the train dataset, we can observe that there is seasonality, which might be informative.

By checking the monthly sales report, we can check that there is a trend with regards to the total sales.

 Generally speaking, the total sales tends to increase as time passes.

### Feature Engineering

We can use date object as index, which allows us to explore our data more easily. I create new features from the index, which are year, month, and quarter.
The reason why I create these features is we can check seasonality based on different time frames.


After creating new features, I convert categorical features. In order to use machine learning techniques, we need to have either continuous or discrete variables, not letters. Therefore, if columns contain string, we can change the values into new numerical values.
After one hot coding, few columns are dropped because they contain redundant information, which might cause multicollinearity.

### Modeling

In order to predict sales price, I applied two different methods, which are lasso linear regression and random forest.

The first model I used was lasso linear regression. Linear regression is a part of parametric method, which means that assumptions need to be met in order to apply it.
The reason why I choose lasso linear regression is because it is fast to train and easy to interpret. It also makes the coefficients to zero, therefore, we can choose less amount of features to predict the total sales price.

The second model that I used was random forest, which is a part of non-parametric methods.
Compared to linear regression, random forest does not need to satisfy some assumptions. It generally does not suffer from over-fitting since it randomly chooses features.


### Evaluation

|             	       |         r2  	      | root mean squared error |
|--------------------- |-------------------	|------------------------	|
|Lasso     |      0.207        |        2608.22          |
|Random Forest    	   |      0.287        |        2668.57          |

Based on Lasso, these are the important features.
![betas](https://github.com/yoonkim0715/new_capstone/blob/master/images/betas.png)

Feature Importance based on random forest.
![feat](https://github.com/yoonkim0715/new_capstone/blob/master/images/feature.png)

In order to predict the sales price, I would like to use Lasso linear regression. The reason is that it is fast to train, therefore, it is time and money efficient. Also, it is easy to interpret the result. 



### Recommendation

Based on the result, promo does affect an increase of sales. More promotions will attract more customers, which lead to higher sales. It is because customers and sales have a high correlation, therefore, it is predictable that when more customers come to shop at the stores, the stores have a higher chance to boost their sales.
In terms of store types, there are 4 different store types, which are a,b,c, and d. All the 4 different types of stores tend to increase their sales when they have promotion. However, based on the results from Lasso, stores with storetype b have the second highest weight in my model, which means that we can promote more promotion in these types of stores in order to boost the total sales.
It is also recommended that we need to have promotions on different items since promotions work differently based on store types.

### Future Steps

- Facebook Prophet

Facebook prophet is extremely useful with regards to forecast financial dataset. It also has a parameter which we can specify holiday season, so that we can predict the total sales of holiday seasons. The problem I face with facebook prophet is the module gives me the total sales of the entire stores instead of an individual store. I am certain that the module will provide an individual store's sales price, therefore, I need to explore more about it.

- Time Series Model

Rossmann sales prediction ranges from January 1st, 2013 to July 31st, 2015. It is time series dataset, which means I need to check a trend throughout the dataset. Since time series data is almost non-stationary, I need to make the dataset stationary. After than I can apply time series models such as ARIMA and ARMA, which might give me a better result.

- Deep Learning

Since I have sufficient amount of data, I can use neural network in order to predict the total sales. It generally produces better results than other machine learning techniques, but it takes a long time to train the model. Therefore, for the future step, I can apply neural network in order to find the total sales.
