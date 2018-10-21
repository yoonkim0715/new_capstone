# Rossmann Sales Prediction

## General Information

Rossmann was founded in March 17, 1972 in Germany and became the second largest drug store in Germany.
They had approximately 4,000 stores all over the Europe.  
I wanted to predict the the total sales of each store on a given day.

Throughout this project, I will predict sales price from Rossmann store. There are 1115 unique stores total in dataset and 4 different types of stores. There are three different kinds of assortment. The dataset also provides information about competitors including the distance from each store to their competitors, years and month when competitors entered their business. There are also various columns that are related to promotion, which can be informative with regards to a prediction of sales.

## Problem Statement

How to increase the total sales in rossmann stores, so that we can have more returns?

### Preprocessing and Exploratory Data Analysis

Both train and test data date features, therefore, I wanted to check if there's a trend in terms of sales. By checking the train dataset, we can observe that there is seasonality, which might be informative.

By checking the weekly sales report, we can check that there is a trend with regards to the total sales.

There is a trend in terms of quarters as well. Generally speaking, the total sales tends to increase as time passes.

### Feature Engineering

We can use date object as index, which allows us to explore our data more easily. I create new features from the index, which are year, month, and quarter.
The reason why I create the year and month features is I want to calculate the length of promotion, and the length of competition. From these two features, I can create compete_duration, which is a calculation from a given date to a date when competitors enter the market. This column is based on the length of months. For a similar reason, I create the feature called promo2_duration, which gives me the length of promo2. Also, using the distance between competitors and the stores, I create a new feature called long_distance. After checking the distribution of the distance of competitors, I choose 75% percentile to indicate where stores are located nearby competitors or not.
After creating new features, I convert categorical features. In order to use machine learning techniques, we need to have either continuous or discrete variables, not letters. Therefore, if columns contain string, we can change the values into new numerical values.
After one hot coding, few columns are dropped because they contain redundant information, which might cause multicollinearity.

### Modeling

In order to predict sales price, I applied two different methods, which are linear regression and random forest.

The first model I choose was linear regression. Linear regression is a part of parametric method, which means that assumptions need to be met in order to apply it.
The reason why I choose linear regression is because it is fast to train and easy to interpret.

The second model that I used was random forest, which is a part of non-parametric method.
Compared to linear regression, random forest does not need to satisfy some assumptions.
It is relatively easy to interpret and since it chooses features randomly, it can avoid overfitting problem.


### Evaluation

|             	       |         r2  	      | root mean squared error |
|--------------------- |-------------------	|------------------------	|
|Linear Regression     |      0.57        |        2416.48          |
|Random Forest     	   |      0.05        |        3607.76          |

Based on my model, random forest does not perform really well and extremely overfits. Therefore, using linear regression, we can have a better prediction.


### Recommendation

Based on the result, promo does affect an increase of sales, while promo2 decreases the total sales.
In terms of store types, there are 4 different store types, which are a,b,c, and d. All the 4 different types of stores tend to increase their sales when they have promotion. However, the increase of storetype b is not that impressive compared to the other store types. In fact, there are only 17 stores that have store type b. Therefore, it is recommended to have more promotions in the other three different types of stores in order to maximizer our return.   
Also, there is a difference in terms of assortment. There are 3 different assortment levels a, b, and c. Similarly, there is not a hugh increase in assortment b, and there are only 9 stores with assortment b. Therefore, we can have more promotions in assortment a and c in order to increase the total sales.

### Future Steps

Since linear regression out performs random forest, I need to manipulate variables, so that features follow assumptions.

In order to have a better prediction, I could apply facebook prophet, which is a good source of prediction. I may be able to use it on the next step.

I can use ARMA and ARIMA model since the dataset is time series data.

I can use rolling means since the dataset contains seasonality.
