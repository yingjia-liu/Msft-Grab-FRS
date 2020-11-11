# Introduction

Dear students, this document target to be the Q & A panel for all questions raised to Grab & Microsoft data science supporting team. 
During the check-in session on 1st October, the most common questions have been answered and listed below. 
If you have and other questions, please add it below following the format template:
- Qx: TBC [Submitter] [Date]

# Topics: 

## Traffic Management
- 1st Check-in @ 2020.10.01

Q1: What does the actual term for the 'demand' column? (as it's in a normalized form)
A1: The demand is normalized into scale of [0,1]. It indicates how many trips requested by passengers generated in this geospatial zone (geohash level 6) at certain time period

Q2: What does the 'day' column mean?
A2: The 'day' column shows the sequential order of the date among the time period for the dataset. (The dataset shows 2 month demand records, so the day is from 1 to 60)

Q3: Which region is the dataset targeting? in Southeast Asia? Do we have to find out on our own?
A3: The geohash area is not a real location in Southeast Asia. The geohash is more like a feature to classify the trip pattern for different zones.

Q4: Which country is the 'timestamp' column referring to? Based in Singapore? Or based on the Geohash location/country time zone?
A4: The timezone will not affect model building and performance, so to simplify, we may consider it as based in SG. 
The purpose of 'timestamp' is to cut the demand into 15 min interval time for the participants to identify the travel pattern change over the time.

## Safety
- 1st Check-in @ 2020.10.01

Q1: There are some duplicate data: Over unique booking 20000, 18 are duplicated. How should we handle these records?
A1: Checking whether there are duplicate records is a part of data cleaning step. If the label is incorrect, it's recommended to delete the records. 

Q1: The model accuracy for training data is 1.0, is it suppose to be correct?
A1: Model accuracy: 1.0 shall not be true, the reason might be overfitting or using un-balanced dataset. 
Student are suggest to figure out the reason through some exploration and you may record all the exploration process as script comments or included in the presentation slides. 

## General Questions on Models
- 2nd Check-in @ 2020.11.11

Q1: How to handle imbalanced dataset
A1: The imbalanced dataset shall mainly refer to the safety dataset, for this dataset, re-sample the training dataset to made label 0/1 around same size shall be a good choice. To understand more for the popular methods to handle imbalanced dataset, please refer to the links below:
1. https://www.kdnuggets.com/2017/06/7-techniques-handle-imbalanced-data.html
2. https://towardsdatascience.com/methods-for-dealing-with-imbalanced-data-5b761be45a18
3. https://towardsdatascience.com/handling-imbalanced-datasets-in-machine-learning-7a0e84220f28

Q2: How to select suitable algorithms:
A2: First, take note that TM topic is more like a regression problem whereas Safety topic is a classification problem.

For regression models, here are some algorithms to be considered:
- Linear regression (Simple, Multiple, and Polynomial)
- Decision tree regression
- Random forest trees
- Gradient boosted trees

For classification models, here are some algorithms to be considered:
- Naive Bayes
- Logistic regression
- SVM (Kernel)
- Decision tree
- Ensemble learning

Please take note that both problems are supervised learning, for supervised learning, majority algorithmns are all included in the scikit-learn library. Please read the manual to understand each algorithmn: https://scikit-learn.org/stable/supervised_learning.html

You are also welcome to explore Deep Learning algorithmns for the topics such as Neural Network, LSTM, etc. 

Q3: How to determine the best predicted algorithms
A3: First, take note that TM topic is more like a regression problem whereas Safety topic is a classification problem.

For regression models, here are some of the evaluation metrics to justify the algorithmn performance: https://openclassrooms.com/en/courses/6401081-improve-the-performance-of-a-machine-learning-model/6519016-evaluate-the-performance-of-a-regression-model

For classification models, here are some of the evaluation metrics to justify the algorithmn performance: 
https://www.ritchieng.com/machine-learning-evaluate-classification-model/

Please also take note that different parameters in the algorithmn will also affect the model performance. So hyperparameter tuning is an important steps that you shall never forget. Here are some links to help you on the hyperparameter tuning:
1. https://www.jeremyjordan.me/hyperparameter-tuning/
2. https://kharshit.github.io/blog/2018/08/03/methods-of-hyperparameter-optimization



