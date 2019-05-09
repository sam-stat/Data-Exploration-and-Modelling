Problem Statement:
------------------
We have data associated with fuel consumption in miles per gallon for the city of California.
Along with the fuel consumption details we also have other information about the car including
horsepower, acceleration, model, etc.
We need to model fuel consumption (mpg) using the given independent variables.

The data description is given below:
1. mpg: continuous 
2. cylinders: multi-valued discrete 
3. displacement: continuous 
4. horsepower: continuous 
5. weight: continuous 
6. acceleration: continuous 
7. model year: multi-valued discrete 
8. origin: multi-valued discrete 
9. car name: string (unique for each instance)

Exploratory data analysis:
---------------------------
1. In the very first step we try to understand the distribution of the target variable that is mpg.
   For that distribution analysis, skewness and other attributes are analysed.
2. Now the other features types are analysed. In the process of analysis we checked the distribution
   of all variables to get a understanding of the outliers in the data. 
3. Features which are having missing values are identified which is to taken care at the time of 
   modelling.
4. Scatter plot of all the features are plotted to get insights that how the different features are 
   associated with one another. After that to bring out the correlated variables we have done a separate
   correlation analysis.
5. Scatter plot gives information how the continious variables are related to one another. To get an 
   understanding of the multi-valued discrete variables we have done a box-plot analysis of the same.    

Model development:
-------------------
Basic preprocessing
--------------------
1. Initially we have death with missing values by imputing with the mean values of the respective 
   columns.
2. Outliers very less in numbers for only two columns are being removed before modelling.
3. One feature "car name" which is different for all the variables is not used in modelling. 
4. Since we are not given with a test and a train data separately, so we have divided the data set
   into two parts train and test. We will keep test totally away and build our model on train. Cross
   validation will be done on the train data only.
5. One hot encoding was done on the discrete multivalued variable.
6. As a measure of goodness of our model we have chosen r2 score.

Linear Regression (Basic Modelling)
-----------------------------------
Linear regression was applied with "mpg" being the target and other features
as independent variables.
Results: 
Train accuracy: 0.8250051486909883 and Test accuracy: 0.8112807219286456

Decision Tree Regression (Basic Modelling)
------------------------------------------
Results:
Train accuracy: 1.0 and Test accuracy: 0.6669754519741429
Remark- Decision tree actually overfitted the data very much and thats why giving training accuracy as 1.

XgBoost Regression (Advanced modelling)
---------------------------------------
Xgboost regression was applied on the data with "mpg" being the target variable.

Results without hyperparameter tuning:
Train accuracy: 0.9999999863569797 and Test accuracy: 0.8369761540733889
Remark- We still found out that the model is still overfitting. Now we have applied hyperparameter tuning
        on the model and the results are given below.

Results with hyperparameter tuning:  
Train accuracy: 0.957182934176924 and Test accuracy: 0.8572520306269685

So, we have finally achieved a accuracy of 85% with hyperparameter tuning.

Note:
------
1. Model.ipynb: I-Python notebook for all the modelling works.
2. Exploratory data analysis.ipynb: I-Python notebook for all the EDA works.  
