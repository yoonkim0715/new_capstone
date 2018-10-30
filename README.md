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

Throughout this project, I will try to predict Rossmann, which is the second largest drogerie store chain in Germany, sales price using machine learning techniques such as linear regression and random forest.

## Folder Directory

There are 3 different folders in this project, which are assets, code, and images.

Assets folder contains pickle objects and data frames converted in csv files. The pickle objects are X_train, X_test, y_train, y_test, and the models that I use in order to predict the sales price. The csv files are datasets after cleaning process. Some of the files are not included due to the size of the files.

Code folder contains 5 different notebooks, which are preprocessing, eda, 2 modeling, and submission. The detail of each notebook is provided at the bottom.

Images folder contains image files which are from the eda notebook and model notebooks.


## Data Directory

I merge the store data with train and test. Dataframes have somewhat different features, but they share columns. Here is the data dictionary.

| Columns | Description |
| ------ | ------ |
| Store | individual store id|
| Sales | the total sales of a given day |
| Customers | the number of customers on a given day |
| Open | an indicator whether stores are open or not. 0 means closed and 1 means open |
| StateHoliday | an indicator of 4 different state holidays. a = public holiday, b = Easter, c = Christmas, 0 = Not Holiday |
| StoreType | 4 diffrent letters based on store types, which are a, b, c, and d |
| Assortment | assortment levels based on stores. a = basic, b = extra, c = extended |
| CompetitionDistance | represents the distance between stores and competitors |
| CompetitionopenSince[Month/Year] | indicates when the competitors enter the market |
| Promo | an indicator whether stores run promotions on a given day. 0 = no promo, 1 = promo |
| Promo2On | an indicator whether stores run promotions2 on a given day. 0 = no promo2, 1 = promo2 |
| Promo2Since[Month/Year] | gives the dates when stores begin promo2 |
| PromoInterval | the name of the months of 4 values when promo2 starts,"N/A", "Jan,Apr,Jul,Oct", "Feb,May,Aug,Nov",  "Mar,Jun,Sep,Dec" |
| Year | gives the year of the current time period |
| Month | gives the month of the current time period |
| Quarter | gives the quarter of the current time period |
| LongDistance | an indicator where stores are closer to the competitors or not. 0 = close to the competitors, 1 = far from the competitors |
| Promo2BeginMonth | gives the actual month when the stores participate|


## Notebook Directory

There are 4 different notebooks in this project. Here is the notebook dictionary.

| Notebook | Description |
| ------ | ------ |
| 01_preprocessing.ipynb | cleaning train and store datasets and combine them|
| 02_eda.ipynb | visualizing so that find important features |
| 03_model_lasso.ipynb | creating a new column based on the results from eda, dropping columns by manually or applying lasso in order to avoid multicollinearity and one hot coding for machine learning and the results |
| 03_model_rf.ipynb | using random forest in order to predict the sales price and the results|
| 04_submission.ipynb | using linear regression with l1 penalty and random forest in order to forecast the sales of each stores|
