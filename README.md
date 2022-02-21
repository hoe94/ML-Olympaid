# ML Olympaid

ML Olympaid 

It's a Kaggle Community Competitions hosted by ML GDEs or TensorFlow Malaysia User Group, sponsored by Google Developers. ML Ecosystem team from GDE sponsors swag prizes to winners of each competition. This is my first time to particapte the data hackathon event as I have often spent my time to build the portfolio projects.
With this participate expereince, I can leverage my machine learning knowledge to build the model. For the data hackathon, I will build the model based on training dataset, and test the model ability on testing dataset.

[Link to ML Olympaid Data Hackathon Event](https://www.kaggle.com/c/ml-olympiad-tensorflow-malaysia-user-group/overview)

# Use Case

- Data Description
  * This is the transactions dataset that made by credit cards in September 2013 by European cardholders.
  * It contains the information of transaction and paid amount made by credit cards
  * There's a target column to indicate whether the transaction is valid or fraud
  * Due to data security concern, all the data are encrypted
  
- Objective
  * Build the ML model to implement the fraud detection
  * To enhance the probabiltiy of detect the fraud transactions.
  * To tackle the imbalanced dataset

- Observation
  * The training data contains 227,845 rows data & 28 columns (227845, 28)
  * First 26 columns (col_0 - col_25) are the information about the transactions
  * Amount column is the paid amount made by transactions. Target column is the response varibale to indicate the transactions is valid or fraud
  * This training data is highly imbalanced. As the fraud transactions only take the distribution 0.17% (386 rows) among the datasets.
  * There are the missing values contains from first 26 columns (col_0 - col_25)

- Challenge
  * This dataset is highly unbalanaced. It might lead to read the prediction resutl incorrectly

- Methodology
  * Python Library: pandas, numpy, matplotlib, seaborn
  * EDA Visualization: Histogram, Boxplot
