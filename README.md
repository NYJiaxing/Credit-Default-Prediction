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
      
### 3. Prediction with Machine Learning Modeling
Normally, using a decision tree or logistic regression as a bench mark, I use decission tree this time. I send four different training data into the same model, downloaded data from UCI dataset, oversampled data, downsampled data and SMOTE data. Then I use confusion matrix, ROC and AUC as evaluation standard to figure out which balancing data method is better.

| Data Used			        |    AUC	      | Precision   | Recall    |  
|:---------------------:|:---------------------------------------------:|:-----------:|:-----------:| 
| Normal dataset      		|  0.72| 0.62 | 0.33 |
| Over-sampled data      		|0.72 | 0.42 | 0.58 |
| Down-sampled data      		| 0.71| 0.38 | 0.65 |   
| SMOTE data      		|0.71 | 0.43 | 0.54 |     

##### Precision: *(also called positive predictive value) is the fraction of relevant instances among the retrieved instances*
##### Recall: *(also known as sensitivity) is the fraction of relevant instances that have been retrieved over the total amount of relevant instances.*
##### AUC: *AUC is equal to the probability that a classifier will rank a randomly chosen positive instance higher than a randomly chosen negative one*

So from the result we can find that the normal dataset get the highest precision, which means the data without over or down sampling is fine to feed to prediction model. In the same time, it gets the lowest recall which means the ability of find out all positive value ('1') is less than the others. It's make sance because other dataset had balanced before sent to the model, the minority data percentage increased.

### 4. Other algorithms can be use
In this section, I introduced two other ensembling algorithms, bagging and boosting. The reason why I introduc these two algorithms is because these two algorithms are not that sensitive to the imbalance data. So I use these two algorithms compare with the decision tree algorithm with normal data to see the result better or not. 

Bagging, developed by Breiman(1996), is a machine-learning method that uses boostrapping to creat multiple training datasets from given datasets. Random forest algorithms is a typical bagging algorithm.

Boosting, especially the populer one AdaBoosting, proposed by Freund and Schapire(1996) is a sequential learning method. It on the basis of supervised learning, weights are successively adjusted and multiple learning results are sought.

*  Ada-Boost algorithm 
*  Random Forest algorithm

| Algorithm Used			        |    AUC	      | Precision   | Recall    |  
|:---------------------:|:---------------------------------------------:|:-----------:|:-----------:| 
| Decision Tree algorithm   		|0.71 |0.62  |  0.54|
| Ada-Boost algorithm      		|0.759 |0.69  | 0.31 |
| Random Forest algorithm   		|0.761 | 0.65|  0.36|

From the result we can see the Ada-Boost and RF algorithm has better accuracy than the benchmark algorithm, it show their ability to handle the imbalance dataset.

