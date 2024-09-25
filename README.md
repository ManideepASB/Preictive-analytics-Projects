                                   INTRODUCTION:
By using income prediction, we may forecast a person's income based on the given data by identifying pertinent trends and behaviors.
The aim of this work is to determine what is the ideal mix of age, education, marital status, and so on for a person's income living in the United States. The income statement forecasts and predictions made using data analytics can be used by a variety of people to make judgments regarding his/her businesses. There are several significant uses of Income prediction.
 The k-nearest neighbor’s algorithm (k-NN) is a non-parametric supervised learning technique in statistics. Regression and classification are two uses for it. The input in both situations consists of a data set's k closest training samples. Whether k-NN is applied for classification or regression determines the results. The result is membership in a class. The class that an object is assigned to based on the majority vote of its k closest neighbors is determined by the item's neighbors. It is a non-parametric and lazy learning algorithm. It can also be used for Regression problems.
                                         DATASET EXPLANATION:
Numerous things influence a person's yearly income. It follows that a person's education level, age, gender, occupation, and other factors will affect them. The dataset contains 16 columns. Target filed: Income. The income is divided into two classes: <=50K and >50K. Several attributes: 14. These are the demographics and other features to describe a person. Based on the person's personal information, we can investigate the feasibility of forecasting their income level.

DATA CLEANING:
First, we explore the data, as you can see the data doesn’t have any column names, so we name them first with the given dataset description. Then we drop the unnecessary column. Let’s drop 'fnlwgt' feature as it is not useful in our analysis or in our further predictions Now, we go further along with our EDA. Check which factors might affect salary. First, we separate categorical features and numerical features.

EXPLORATORY DATA ANALYSIS:
We started off with exploring the feature age, even though there are fewer women than men, both men and women have a similar distribution of ages by gender. 2 observations are made, People who earn more than 50K tend to be between the ages of 35 and 55. Most people with incomes under 50K are between the ages of 17 and 35. 

 
 
 


Next, we go to work class, In this 2799 missing values out of 48842, Let’s fill in the missing values with mode (private value).
  
In the education column also there are 2 observations. People with incomes under 50K are more likely to have finished high school or attended some college. The majority of those with incomes over 50k have earned a bachelor's degree.
 
Now we look at the occupation column some observations are made There are some missing values in the 'occupation' feature: people with the missing occupation are more likely to have, an income lesser than 50k completed their some-college are male are never married & are from United-States. If gender is 'Female' it means the occupation is more likely to be 'Adm-clerical', if gender is 'Male' occupation is more likely to be 'Other-service'. Let’s replace the missing value with respect to the above logic

 

 
In race column we can see that the white population is extremely high than the others. 
 

In sex ratio income equality can be shown in the below graph.
 
In the Native country column, there are 857 (1.76%) missing values. After careful observations we can see most of the missing values in 'Native-Country' are from United-States, let’s replace the missing value with 'United -States i.e. mode'
We will be looking at the sns plots of many categorical and numerical data and compare them to get the outlier observations
                                      
                                       
        

   
                                           
                                                   
                                       
                                                      
Now we check for the outliers in the numerical data 
1. age: there can be people with ages more than 78 years, data is ok 
2. educational-num: there can be an educational-num with less than 4.5, data is ok
 3. capital-gain: as there are entries with 0 capital loss which is also a multiplier when calculating outliers, therefore upper limit and lower limits are calculated as 0 - there are some entries of value '99999',  from the above data we can see that most of them a. have done 'Bachelors' and 'Professional Schooling' a. have income more than 50k, b. are with the occupation of 'Prof-specialty' Therefore capital-gain of '99999' can be considered valid.
 4. capital-loss: as there are entries with 0 capital loss which is also a multiplier when calculating outliers, therefore upper limit and lower limits are calculated as 0 
5. hours-per-week: as minimum hours-per-week is 1 and maximum hour-per-week are 99, there can be people with hours-per-week less than 40 and higher than 45
After that we re-define categorical and numerical data frame, as we have replaced missing values only in original data frame.

FEATURE ENGINEERING:
We created dummy variables for categorical features by One Hot encoding then we concatenated the numerical data frame with the categorical data frame (with dummies). After, that we separate the dependent and independent variables. We split training and testing data with a test size of 0.2. Then we standardize the data and created a KNN model and check its results here.

MODEL FITTING:
After fitting the model, we check for continuous k values from 1 to 10 and get the best out of it which is 10. We also check it with additional values for confirmation. Then we’ll plot the Roc curve to get accurate results. 
A heatmap is made for the accuracy score to be displayed.
 
Then we fit the model with the KNN classifier and try out with different k values also.
 
Here there were few observations that can been seen,
•	The test score keeps increasing with value of K and reaches a local peak at k=8, then again from k=10 it raises and attains almost a constant value.
•	The ideal selection of K would be 8, as the more the K value more complex the model can tend to become for future purposes.
•	The accuracy observed here is 0.84, with an AUC of 0.87.
A screenshot of ROC curve is given below for reference,
 


CONCLUSION:
After training the ideal data set with the Model and obtaining accuracy scores we have obtained an ideal fit for the data. It has the most ideal k value at K=10. The test accuracy score has a maximum at a much higher value of K. But a higher value of K can lead to a much more complex model for further usage of the model. The model is chosen to keep all of these into consideration So finally, the ideal model is having a Train data score here of 86.7%, which resembles the model that is well fit and with a test accuracy score of 83.8%. The final accuracy of the model obtained here is 84% with and AUC value of 0.87.
