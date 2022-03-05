# ML Olympaid

ML Olympaid 

It's a Kaggle Community Competitions hosted by ML GDEs or TensorFlow Malaysia User Group, sponsored by Google Developers. ML Ecosystem team from GDE sponsors swag prizes to winners of each competition. This is my first time to particapte the data hackathon event as I have often spent my time to build the portfolio projects.
With this participate expereince, I can leverage my machine learning knowledge to build the model. For the data hackathon, I will build the model based on training dataset, and test the model ability on testing dataset.

[Link to ML Olympaid Data Hackathon Event](https://www.kaggle.com/c/ml-olympiad-tensorflow-malaysia-user-group/overview)

# Use Case

- Business Understanding
  * This is the transactions dataset that made by credit cards in September 2013 by European cardholders.
  * It contains the information of transaction and paid amount made by credit cards
  * There's a target column to indicate whether the transaction is valid or fraud
  * Due to data security concern, all the data are encrypted
  
- Objective
  * To help company to capture the fraud transactions
  * To take action immediately on fraud transactions, and reduce the customer lost.

- Data Understanding
  * The training data contains 227,845 rows data & 28 columns
  * The Training data is 48.7mb.
  * First 26 columns (col_0 - col_25) are the information about the transactions
  * Amount column is the paid amount made by transactions. Target column is the response varibale to indicate the transactions is valid or fraud
  * This training data is highly imbalanced. As the fraud transactions only take the distribution 0.17% (386 rows) among the datasets.
  * There are the missing values contains from first 26 columns (col_0 - col_25)

- Challenge
  * This dataset is highly unbalanaced. It might lead to read the prediction result incorrectly.
  * Due to confidental data, cant apply the business domain knowledge to analyse the data

- Solution
  * Perform EDA Visualization to gain the deeper insight of data.
  * Perform Outlier Analysis to understand any outliers occured in data.
  * Feature Engineering: Data Cleansing & SMOTETomek technique
  * Build the classfication model (Xgboost) to predict the transaction validity

# EDA Visualization

- Histogram
  * Based on the distribution & X-axis, we grouped our observation and categorize into the table
  * For the image reference, please go the links. 
  * <a href="https://github.com/hoe94/ML-Olympaid/blob/main/Figures/histogram1.png">Histogram 1 (col_0 - col_14) </a>
  * <a href="https://github.com/hoe94/ML-Olympaid/blob/main/Figures/histogram2.png">Histogram 2 (col_15 - Amount)</a>
   
   
  | Group| Columns                | Distribution  | X-Axis     | Remarks                                               |
  | ---  |:-------------:         |:-------------:|:--------:  |:------------------------------------------------------|
  | 1    | col_0 - col_3, col_25, | normal        | almost 0   | most values falls nearby 0, some outlier value appears|
  | 2    | col_10, col_17, col_18 | normal        | almost 0   | most values falls nearby 0                            |
  |		    | col_21 - col_24        |               |            |                                                       |
  | 3    | col_12, col_15         | normal        |[-2, 2]     | the values between -2 to 2                            |
  |      | col_16, col_19         |               |            |                        							                        | 
  | 4    | col_4, col_8, col_14   | normal        |[-2.5, 2.5] | the values between -2.5 to 2.5                        |
  |      |                        |               |            |                        							                        | 
  |      | col_5, col_6, col_7    |               |            |                        							                        | 
  | 5    | col_9, col_11, col_13  | normal        |[-5.0, 5.0] | the values between -5.0 to 5.0                        |   
  |      | col_20                 |               |            |                        							                        | 

- Outlier Analysis
  * This analysis used to define any outlier valules occur on every column
  * From the boxplot chart, almost every column got outlier value are out of the range (min & max)
  * <a href="https://github.com/hoe94/ML-Olympaid/blob/main/Figures/boxplot1.png">Boxplot</a>
  
- Outlier Analysis 2
  * column: column name
  * min_outlier_count%: percentage(%) implies on the number of outlier count below the minimum threshold (value - (1.5 * iqr))
  * within_range_count%: percentage (%) implies on the number of value falls on within range
  * max_outlier_count%: percentage (%) implies on the number of outlier count above the maximum threshold (value + (1.5 * iqr))
  * null_count%: percentage (%) implies on the number of value which is null
  * For example: column_0 contains 3.03% data are below minimum threshold, and contains 4.58% are below maximum threshold
  * In the nutshell, we decided not to proceed handle outlier values, it's due to outliers value may contain the useful information.
  <img src="https://github.com/hoe94/ML-Olympaid/blob/main/Figures/Outlier_Analysis.png"/>
