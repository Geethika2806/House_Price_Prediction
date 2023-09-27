# House_Price_Prediction
The dataset used is available on Kaggle: https://www.kaggle.com/amitabhajoy/bengaluru-house-price-data
This code performs data preprocessing and builds Linear Regression machine learning model on the Bengaluru House prices dataset.

Steps:
1) Data Cleaning is started b initially removing entries with any null values
2) A new feature for bhk as an integer is added to maintain consistency in the number of bedrooms.
3) Entries which have a range as total_sqft are converted into float by taking average.
4) A new entry price per sqft is added.
5) All the locations which have less than 10 houses are termed as other to reduce the dimensionality and make it easier to perform one-hot encoding
6) Further outliers are removed using business logic. (Eg: Checking minimum sqft threshold for a bedroom which is considered to be 300 in this case, removing entries which have unusual number of bathrooms for a particular number of bedrooms)
7) Since there is a large variation between the minimum and maximum price per sqft, for every location outliers are removed by using mean and one standard deviation
8) On plotting prices for a partiacular loacation, it is observed that for the same sqft some 2bhk houses are priced more than 3bhk house. Those 2bhk houses whose price per sqft is less than mean of price per sqft of 1 are removed. Likewise 3bhk prices are compared with mean of 2bhk prices and the outliers are removed.
9) Later one-hot encoding is done on the location feature.
10) A Linear regression model is trained to predict house prices based on loaction,sqft,number of bathrooms and number of bedrooms.
11) Accuracy of model is measured using K Fold cross validation.
12) The model gives an accuracy of above 80%.
