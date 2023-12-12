---
Title: NYC Bus Delay Prediction
Author: Rahat, A.D.
Date: June 23rd, 2022
---

### Introduction
In the bustling city of New York, bus delays can have a significant impact on the daily commute and overall urban mobility. Understanding and predicting these delays is crucial for improving transit efficiency and passenger satisfaction. This project, NYC Bus Delay Prediction, leverages machine learning techniques to forecast bus delays in New York City.

My approach involves a comprehensive analysis of public transit data, primarily focusing on factors that contribute to bus delays. By harnessing the power of data science and machine learning algorithms, we aim to provide a robust predictive model that can aid city planners, transit authorities, and the general public in anticipating and managing bus delays more effectively.


The Project is divided by 3 chapters: 

    1. Chapter 01 - Data Preparation
    2. Chapter 02 - Exploratory Data Analysis (EDA)
    3. Chapter 03 - Implementation of ML Algorithm. 


### Chapter 01: Data Preparation: 

#### Description: 
This part of the project focuses on preparing the data necessary for predicting bus delays in New York City. The data is sourced from a Kaggle dataset, which can be found [here](https://www.kaggle.com/datasets/stoney71/new-york-city-transport-statistics).

#### Implementation Details

    1. Load all the data in dataframe. 
    2. Rename the columns. 
    3. Remove null values and duplicate entries.
    3. Calculate the delay time using expected_arrival_time and schedlue_arraival_time.
    4. Derive some imporatant time features from recorded_time. The features are : Weekend status, day of month, month of the year etc.
    

### Chapter 02 - Exploratory Data Analysis (EDA): 

#### Description: 
This part I have done all the EDA of the dataset. 

#### Implementation Details

    1. Firstly, I have analyze the uni-variant analysis. 
    2. Then I also do some bi-variate analysis. 

#### Key Insights: 
After my EDA I have found some key points: 

    1. The 'direction' feature has almost balance between to class. 
    2. Total Number of Unique Line: 242. Where b6 is mostly used one. 
    3. Total Number of Unique Source Stop: 628 and end stop: 651
    4. Total Number of Unique Bus Name: 4629
    5. Total Number of Unique Arrival Approximation: 208
    6. 78% of total ride encounter in the weekdays where rest 22% of the ride encounted in weekends.
    7. The delay pattern of the dataset are given below: 
    
        |-----------------|--------|------------|
        | Interval        | Counts | Percentage |
        |-----------------|--------|------------|
        | =0              | 264290 | 26.4%      |
        | >0 and <=5      | 373000 | 37.3%      |
        | >5 and <=10     | 172606 | 17.3%      |
        | >10 and <=20    | 126007 | 12.6%      |
        | >20 and <=50    | 57627  | 5.8%       |
        | >50             | 6470   | 0.6%       |
        |-----------------|--------|------------|

    8. After the analysis I have found some of the features have significance in the delay and those are: line_name, org_name, dest_name, vech_name, day_of_year, month_number, day_of_month, time_of_day, weekend_status.    


### Chapter 03 - Implementation of ML Algorithm:

#### Description:
In this part I have implemented three machine learning algorithms. They are: 

                          1. Linear Regression
                          2. XG-Boost Regression
                          3. Tuned XG-Boost Regression

#### Implementation Details

    1. At first, convert the categorical variables to numerical values as I will implement regression.
    2. Remove the lavel value delay from the dataset.
    3. Split 80/20 for train and test.
    4. Then apply linear regression to the dataset.
    5. After that implement XG-Boost Regression.
    6. Then I use RandomizedSearchCV in the XG-Boost Regression model using different hyper-parameter and get the best model.
    7. Lastly, I apply the test data to the best tuned XG-Boost Regression model and evaluate the results. 

### Result Analysis: 

The results of the all three models are: 

                                        | Approach                     | RMSE  |
                                        |------------------------------|-------|
                                        | Linear Regression            | 8.90  |
                                        | XG-Boost Regression          | 8.35  |
                                        | Tuned XG-Boost Regression    | 8.09  |

So, in conclusion Tuned XG-Boost Regression give the best results. But as the RMSE is not significanly lower, I can advocate for the simpler model. 
