
# Store Sales - Time Series Forecasting 
## **`Dataset Description`**

You will predict sales for the thousands of product families sold at Favorita stores located in Ecuador. The training data includes dates, store and product information, whether that item was being promoted, as well as the sales numbers. Additional files include supplementary information that may be useful in building your models.

## **`Business problem statement`**

In this “getting started” competition, you’ll use time-series forecasting to forecast store sales on data from Corporación Favorita, a large Ecuadorian-based grocery retailer.

Specifically, you'll build a model that more accurately predicts the unit sales for thousands of items sold at different Favorita stores. You'll practice your machine learning skills with an approachable training dataset of dates, store, and item information, promotions, and unit sales.

## `Evaluation` :
The evaluation metric for this competition is Root Mean Squared Logarithmic Error.

The RMSLE is calculated as:

$$RMSLE = \sqrt{ \frac{1}{n} \sum_{i=1}^n \left(\log (1 + \hat{y}_i) - \log (1 + y_i)\right)^2}$$

where:

 n is the total number of instances,

 $\hat{y}_i$ is the predicted value of the target for instance (i),

 ${y}_i$ is the actual value of the target for instance (i)
 
 $log$ is the natural logarithm.

## **`File Descriptions and Data Field Information`**

`train.csv` :

The training data, comprising time series of features store_nbr, family, and onpromotion as well as the target sales.
store_nbr identifies the store at which the products are sold.
family identifies the type of product sold.
sales gives the total sales for a product family at a particular store at a given date. Fractional values are possible since products can be sold in fractional units (1.5 kg of cheese, for instance, as opposed to 1 bag of chips).
onpromotion gives the total number of items in a product family that were being promoted at a store at a given date.

`test.csv` :

The test data, having the same features as the training data. You will predict the target sales for the dates in this file.
The dates in the test data are for the 15 days after the last date in the training data.

`sample_submission.csv` : 

A sample submission file in the correct format.
stores.csv
Store metadata, including city, state, type, and cluster.
cluster is a grouping of similar stores.

`oil.csv` : 

Daily oil price. Includes values during both the train and test data timeframes. (Ecuador is an oil-dependent country and it's economical health is highly vulnerable to shocks in oil prices.)

`holidays_events.csv` : 

Holidays and Events, with metadata
NOTE: Pay special attention to the transferred column. A holiday that is transferred officially falls on that calendar day, but was moved to another date by the government. A transferred day is more like a normal day than a holiday. To find the day that it was actually celebrated, look for the corresponding row where type is Transfer. For example, the holiday Independencia de Guayaquil was transferred from 2012-10-09 to 2012-10-12, which means it was celebrated on 2012-10-12. Days that are type Bridge are extra days that are added to a holiday (e.g., to extend the break across a long weekend). These are frequently made up by the type Work Day which is a day not normally scheduled for work (e.g., Saturday) that is meant to payback the Bridge.
Additional holidays are days added a regular calendar holiday, for example, as typically happens around Christmas (making Christmas Eve a holiday).

`Additional Notes` : 

Wages in the public sector are paid every two weeks on the 15 th and on the last day of the month. Supermarket sales could be affected by this.
A magnitude 7.8 earthquake struck Ecuador on April 16, 2016. People rallied in relief efforts donating water and other first need products which greatly affected supermarket sales for several weeks after the earthquake.

# Steps Followed 

1. Data transforming (Reading,Down casting,Setting the data types, Parsing the dates)
2. Data Cleaning (Handling null values)
3. Exploring the data and EDA
4. Working on the sample
5. Applying the ML model
6. Model Selection
7. Model Evaluation

# Conclusion
1. Base Model (Linear Regression)  
The private leaderboard score for the Linear Regression model was 2.11573

2. Random Forest Regressor    
The private leaderboard score for the Random Foerst Regressor model was 0.89513

3. Exponential Moving Average:          
The public leaderboard score for the EMA was 0.44556 

# Summary & Insights

In this project, we have compared Decision tree regressor, Random forest regressor and XGB regressor models. A fraction of training data (0.02 of total training data), was used to train the model because of the low memory issue. Following are the major conclusion of this study.

- EDA is an important step to develop insights on the given data.
- Feature engineering helps in transforming the data in format that is best fit for fitting into a model.
- Its always a good idea to compare two or more models to obtain best results.
- It is found that after hypertuning the parameters, the training loss for training and bigger training dataset has significantly improved when measured against the RMSLE loss.
- Gradient Boosting gives the best result for validation loss for RMSLE as compared to Decision Tree Regressor or Random Forest Regressor.
- Whole training data must be used to get the best Kaggle score.


