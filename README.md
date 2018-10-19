## General Information

Rossmann was founded in March 17, 1972 in Germany and became the second largest drug store in Germany.
They had approximately 4,000 stores all over the Europe.  
I wanted to predict the the total sales of each store on a given day.

Throughout this project, I will predict sales price from Rossmann store. There are 1115 unique stores total in dataset and 4 different types of stores. There are three different kinds of assortment. The dataset also provides information about competitors including the distance from each store to their competitors, years and month when competitors entered their business. There are also various columns that are related to promotion, which can be informative with regards to a prediction of sales.

This project contains 3 notebooks total, which are assets, code, and images.

Assets folder contains pickle objects that are from preprocessing notebook. The pickle object named clean_df is from after preprocessing and feature engineering. The pickle object named clean_store is obtained after cleaning store dataset.

Code folder contains 3 different types of python notebook.

- The first notebook describes the way I clean the dataset. There were _ columns and _ rows in total. This process includes imputing null values, create new columns based on the dataset, manipulating some features in the dataset, and merging two data sets and get a new data frame. I use two different dataset, which are train and store.

- The second notebook shows exploratory data analysis. In this notebook, there are various plots that show the relationship between dependent - independent variables and dependent - dependent variables.

- The third notebook represents models that I use for prediction. This notebook has three sub-notebooks because I use two models in order to predict the sales. The first model is linear regression. Linear regression is easy to train and interpret. However, there are some assumptions that have to be met in order to use linear regression. Therefore, I use random forest in the second notebook. It is relatively easy to interpret compared to other models, but it does not require linear regression's assumptions, which means that there is no limitation in terms of applying the model.


Train data has 9 columns total, which are store, dayofweek, date, sales, customers, open, promo, stateholiday, and schoolholiday.
Store data has 10 columns total, which are
store, storetype, assortment, competitiondistance, competitionopensincemonth, competitionopensinceyear, promo2, promo2sinceweek, promo2sinceyear, promointerval.
Test data has 8 columns total. It has the same features as train dataset, but without sales since sales is the dependent variable.


Image folder contains image files that are from eda notebook.
There are various image files total which show the relationship between the variables.


## Data Gathering

I obtained data from Kaggle and data is available on [here](https://www.kaggle.com/c/rossmann-store-sales)
The data contained three different csv files, which are train, test, and store.

#### Train
There were 1115 different stores in total from January 1, 2013 to July 13, 2015 in dataset.
The train dataset contains 1017209 observations and 9 features. Here is the data dictionary.

- Store:
a unique Id for each store

- Sales:
the turnover for any given day (this is what you are predicting)

- Customers:
the number of customers on a given day

- Open:
an indicator for whether the store was open: 0 = closed, 1 = open

- Promo:
indicates whether a store is running a promo on that day

- StateHoliday:
indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None

- SchoolHoliday:
indicates if the (Store, Date) was affected by the closure of public schools


### Store

The store dataset contains 1115 observations with 10 features. The observation is unique. There are some stores that have open as 0, which means that they close for renovation or some situations.

- StoreType:
differentiates between 4 different store models: a, b, c, d

- Assortment:
describes an assortment level: a = basic, b = extra, c = extended

- CompetitionDistance:
distance in meters to the nearest competitor store

- CompetitionOpenSince Month/Year:
gives the approximate year and month of the time the nearest competitor was opened

- Promo2:  
Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating

- Promo2Since Year/Week:
describes the year and calendar week when the store started participating in Promo2

- PromoInterval:
describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store

### Preprocessing and Exploratory Data Analysis

Both train and test data date features, therefore, I wanted to check if there's a trend in terms of sales. By checking the train dataset, we can observe that there is seasonality, which might be informative.
I also wanted to check if customers had similar patterns based on stores and some stores tended to have higher numbers of customers with regards to their average expenditure.
In the processing of eda, I was able to find a relationship between sales and customers.
![sales_customers](https://github)
It turns out that store type and assortment have some effects with regards to promotion.
![sales_storetype](https://github)
![sales_assortment](https://github)
Although most of stores are closed on national holidays, stores tended to have good sales on school holiday.
It also turns out that which day of week is a good indicator of average sales.
![sales_assortment](https://github)


I assumed that there might be more promotions if stores are closed to competitors. However, the distance between competitor did not seem like to have an effect on promotion.

### Modeling

In order to predict sales price, I applied two different methods, which are linear regression and random forest.

The first model I choose was linear regression. Linear regression is a part of parametric method, which means that assumptions need to be met in order to apply it.
The reason why I choose linear regression is because it is fast to train and easy to interprete.

The second model that I used was random forest, which is a part of non-parametric method.
Compared to linear regression, random forest does not need to satisfy some assumptions.
It is relatively easy to interpret and since it chooses features randomly, it can avoid overfitting problem.


### Evaluation

|             	       |         r2  	      | root mean squared error |
|--------------------- |-------------------	|------------------------	|
|Linear Regression     |      0.8876        |        1240.96          |
|Random Forest     	   |      0.8707        |        1331.20          |



### Future Steps

In order to have a better prediction, I could apply facebook prophet, which is a good source of prediction. I may be able to use it on the next step.
I can use ARMA and ARIMA model since the dataset is time series data.
I can use rolling means since the dataset contains seasonality.
