# Lending Club Data Credit Risk Analysis - Predicting Default
Using Machine learning Classification Models to predict defaults on Loans

## Project Motivation

For this project I chose a dataset from Lending Club **approved personal loans between 2007 and 2011**. The data can be found on www.lendingclub.com. The purpose of the analysis is to reduce defaults, improve profitability and help the company and investors determine interest rates. We will use machine learning models to analyze credit risk as a binary classification problem.

![](https://theme.zdassets.com/theme_assets/680652/3abc1fe11ed0a385b1298f0a1e44a7d7d5f78fc1.png)

## Process Overview

- ###	**Introduction**

- ###	**Importing Libraries**
- ###	**Creating Helper Functions**

    - #### Confusion Matrix plot
    - #### Feature importance plot
    - #### ROC curve plot
    - #### Minimum PCA
    - #### FPR and TPR
 
- ###	**Exploratory Data Analysis**

    - #### Reading Data
    - #### Exploring Data -Target Column -Features Selection
    - #### Cleaning
        - ##### Missing Values
        - ##### Formatting Numerical Data
        - ##### Creating dummy variables for Categorical
        
- ###	**Modeling**

    - #### Selecting performance metrics
    - #### SMOT for class imbalance
    - #### Logistic Regression
    - #### Random Forest  
    - #### XG Boost
    
- ###	**Conclusion**
- ###	**Nest Steps**

## Performance Metric Selection

The model will be used to determine who should be approved for a loan and who shouldn’t, denying the loan to a client who will end up paying in full (false positives) represents a loss, but because interest is usually only a portion of principal the company will most likely be more comfortable not taking the chance when the risk is not to get reimbursed at all and lose the entire principal which represents a higher amount. Thus the main concern here is to avoid approving somebody who won't be able to repay or in other words avoid false negatives. This is achieved by a model with a high recall rate. Recall will be the performance evaluation metric of choice for our model. We also need to evaluate TPR to make sure we are not declined too many qualified borrowers.

## SMOT 

Imbalanced datasets as the one we are working with in this project are very common in data science. Training a Machine Learning Model with this imbalanced dataset, often causes the model to develop a certain bias towards the majority class. SMOT is a technique based on nearest neighbors judged by Euclidean Distance between data points in feature space. In our dataset only 15% of the loans were not repaid and we need to use SMOT to balance the dataset.

## Binary Logistic Regression

Logistic regression is a powerful Algorithm for classification of categorical variables and it will turn out to be very useful for our credit default prediction task. In this project we use the sigmoid function to transform our inputs into 0 to 1 values and then use the 50% threshold to decide on the class each data point will be attributed to. 

![](https://capstone-project-bucket-niko.s3.amazonaws.com/notebooks/sigmoid+function.png)

## Random Forest  

Random forest represents the wisdom of the crowd. The concept is to build a large number of decision trees trained on different subsamples of the data generated by bootstrapping and use a voting system to decide on the classification.

![](https://capstone-project-bucket-niko.s3.amazonaws.com/notebooks/random+forest.png)

## XG Boost

Gradient descent is the bread and butter of machine learning algorithms and XG Boost is the golden standard of utilizing gradient descent. Think of it as planning out a few different routes to a single location you’ve never been to; as you use all of the routes, you begin to learn which traffic lights take long when and how the time of day impacts one route over the other, allowing you to craft the perfect route.

![](https://capstone-project-bucket-niko.s3.amazonaws.com/notebooks/XGboost.png)
