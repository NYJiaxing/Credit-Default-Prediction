# Credit-Default-Prediction

This project is created to predict consumer credit default with machine learning techniques. The dataset is download from UCI public dataset [Download Dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00350/).

In this project, I'll follow the below process, based on the data we have to predict whether the consumer will make a credit default in the 

* Data exploration
* Data Preprocessiong
* Prediction with Machine Learning Modeling
* Evaluation

### 1. Data Exploration
In data exploration, I using python Pandas package import the data from CSV file. And using matplotlib and seaborn package visualize the dataset. Follow result is found after the exploration:
      * In this dataset has 30000 rows data and 25 features.
      * All of the features had already digitalized before I downloaded it
      * There is no missing value in the dataset
      * The ground truth result, is slightly imbalanced (77% of data is positive, 23% of data is negative)

![](/images/data_exp_2.png)

### 2. Data Preprocessing
In data preprocessing, I try three method to overcome the imbalance dataset:
      * Over-sampling, randomly create more data to minority data to ensure the two data is balanced
      * Down-sampling, randomly delete data from majority data to ensure the two data is balanced
      * SMOTE Algorithm, using KNN algorithm to find nearest data around the minority data to make two dataset balanced
      
      

