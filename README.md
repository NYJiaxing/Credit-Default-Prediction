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
      * The ground truth result, is slightly imbalanced




After I explore the whole dataset, I found the ground truth of the prediction is not perfectly balanced. 77% of the result is '0', which means the consumer didn't pay the bill, 23% of the consumer pay the bill. Normally, the imbalance dataset has the 8:1 ratio of positive and negative result, in this case is only 3:1. 

But I still discuess three imbalance dataset dealing method in my notebook. Over-sampling minority data, down-sampling majority data and using SMOTE algorithm to synthetic data.
