# Rossmann Sales Prediction

## Directory Structure

```
.
├── Technical_Report.md
├── README.md
├── assets
├── code
├── images

```

## Data Gathering

I obtained data from Kaggle and data is available on [here](https://www.kaggle.com/c/rossmann-store-sales)


The data contained three different csv files, which are train, test, and store.


## Technical Report

Throughout this project, I will try to predict rossmann, which is the second largest drugerie chain in Germany,  sales price using machine learning techniques such as linear regression and random forest.

## Folder Directory

There are 3 diffrent folders in this project, which are assets, code, and images.

Assets folder contains pickle objects and data frames converted in csv files. The pickle objects are either X and y objects or models that I use. There are 3 csv files, which are the data frames that have been preprocessed for modeling. Some pickle objects or csv files that exceed 100 mb will not be included in this folder.

Code folder contains 4 different notebooks, which are preprocessing, eda, feature engineering, and model. The detail of each notebook is provided at the bottom.

Images folder contains 11 image files which are from the eda notebook and model notebooks. 


## Data Directory

I merge the store data with train and test. Dataframes have somewhat different features, but they share columns. Here is the data dictionary.

| Columns | Description |
| ------ | ------ |
| store | individual store id|
| sales | the total sales of a given day |
| customers | the number of customers on a given day |
| open | an indicator whether stores are open or not. 0 means closed and 1 means open |
| stateholiday | an indicator of 4 different state holidays. a = public holiday, b = Easter, c = Christmas, 0 = Not Holiday |
| storetype | 4 diffrent letters based on store types, which are a, b, c, and d |
| assortment | assortment levels based on stores. a = basic, b = extra, c = extended |
| competitiondistance | represents the distance between stores and competitors |
| competitionopensince[month/year] | indicates when the competitors enter the market |
| promo | an indicator whether stores run promotions on a given day. 0 = no promo, 1 = promo |
| promo2 | an indicator whether stores run promotions2 on a given day. 0 = no promo2, 1 = promo2 |
| promo2since[month/year] | gives the dates when stores begin promo2 |
| promointerval | the name of the months of 4 values when promo2 starts,"N/A", "Jan,Apr,Jul,Oct", "Feb,May,Aug,Nov",  "Mar,Jun,Sep,Dec" |
| year | gives the year of the current time period |
| month | gives the month of the current time period |
| quarter | gives the quarter of the current time period |
| compete_duration | gives the length of competition between the stores and competitors in months|
| long_distance | an indicator where stores are closer to the competitors or not. 0 = close to the competitors, 1 = far from the competitors |
| promo2_duration | gives the length of promo2 from the current date to the starting point of promo2|


## Notebook Directory

There are 4 different notebooks in this project. Here is the notebook dictionary.

| Notebook | Description |
| ------ | ------ |
| 01_preprocessing.ipynb | cleaning trani and store datasets and combine them|
| 02_eda.ipynb | visualizing so that find important features |
| 03_feature_engineering.ipynb | creating new columns based on the results from eda, dropping columns in order to avoid multicollinearity and one hot coding for machine learning |
| 04_model.ipynb | using linear regression and random forest in order to forecast the sales of each stores |
