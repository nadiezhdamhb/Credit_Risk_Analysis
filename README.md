# Credit_Risk_Analysis
Module 17

### Overview of the analysis:

*Background and Purpose*

Fast Lending, a peer-to-peer lending services company is looking to use machine learning to assess credit risk. By using machine learning, they hope to create a quicker and more reliable loan experience. Machine Learning will have a high accuracy identification rate for good candidates for loans which in turn could allow for lower default rates. 

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, you’ll need to employ different techniques to train and evaluate models with unbalanced classes. Jill asks you to use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, you’ll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, you’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, you’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Once you’re done, you’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.

### Results: 

*Deliverable 1: Use Resampling Models to Predict Credit Risk*

#### Naive Random Oversampling

![image](https://github.com/nadiezhdamhb/Credit_Risk_Analysis/blob/main/Resources/Naive_random_model.png)

- Balanced Accuracy: 0.6249984891886339
- Precision: The precision is 0.01 for High-risk loans and 1.00 for Low-risk loans.
- Recall: High & Low risk = 0.60 and 0.65 respectively
- F1 scores for High & Low risk: 0.02 and 0.79 respectively

#### SMOTE Oversampling

![image](https://github.com/nadiezhdamhb/Credit_Risk_Analysis/blob/main/Resources/Smote_model.png)

- Balanced Accuracy: 0.6512584051472337
- Precision: The precision is 0.01 for High-risk loans and 1.00 for Low-risk loans.
- Recall: High & Low risk = 0.64 and 0.66 respectively
- F1 scores for High & Low risk: 0.02 and 0.79 respectively

#### Undersampling

![image](https://github.com/nadiezhdamhb/Credit_Risk_Analysis/blob/main/Resources/Undersampling_model.png)

- Balanced Accuracy: 0.5107398543980726
- Precision: The precision is 0.01 for High-risk loans and 1.00 for Low-risk loans.
- Recall: High & Low risk = 0.59 and 0.44 respectively
- F1 scores for High & Low risk: 0.01 and 0.61 respectively

*Deliverable 2: Use the SMOTEENN algorithm to Predict Credit Risk*

#### Combination Under-Over Sampling using the SMOTEENN algorithm

![image](https://github.com/nadiezhdamhb/Credit_Risk_Analysis/blob/main/Resources/Smoteen_algorithm.png)

- Balanced Accuracy: 0.6163546337591808
- Precision: The precision is 0.01 for High-risk loans and 1.00 for Low-risk loans.
- Recall: High & Low risk = 0.69 and 0.54 respectively
- F1 scores for High & Low risk: 0.02 and 0.70 respectively

*Deliverable 3: Use Ensemble Classifiers to Predict Credit Risk*


#### Balanced Random Forest Classifier

![image](https://github.com/nadiezhdamhb/Credit_Risk_Analysis/blob/main/Resources/Balanced_random_forest.png)

- Balanced Accuracy: 0.7877672625306695
- Precision: The precision is 0.04 for High-risk loans and 1.00 for Low-risk loans.
- Recall: High & Low risk = 0.67 and 0.91 respectively
- F1 scores for High & Low risk: 0.07 and 0.95 respectively

#### Easy Ensemble AdaBoost Classifier

![image](https://github.com/nadiezhdamhb/Credit_Risk_Analysis/blob/main/Resources/Easy%20Ensemble%20AdaBoosting.png)

- Balanced Accuracy: 0.925427358175101
- Precision: The precision is 0.07 for High-risk loans and 1.00 for Low-risk loans.
- Recall: High & Low risk = 0.92 and 0.94 respectively
- F1 scores for High & Low risk: 0.14 and 0.97 respectively

### Summary and Recommendation: 

After testing all the algorithms, it looks like all the models have very poor precision scores for High-Risk loans and scored high precision (1.00) on predicting Low-Risk loans which is not ideal. This is not helpful because in order for a model to be effective it should be able to predict well against bad decisions when faced with new data. Althought the High-Risk data is less frequent than the Low-Risk data based on the confusion matrix, it might be a good idea to collect more data on High-Risk and test to see if this will help boost the precision score. To determine how effective a model is, the recall scores are what will help to make this decision. The Easy Ensemble Classifier has the best recall scores of 92% and 94% for High-Risk and Low-Risk, respectively when compared to the rest of the models.

I would recommend the usage of the Easy Ensemble Classifier because is a good algorithm to identify High-Risk loans. The Easy Ensemble Classifier shows a high accuracy score with a very good high-risk recall score, which means that this model would be the most effective at predicting which loans are at risk of any negative consequences for the company such as non-repayment, loans going to collection, etc. The recall score for the High-Risk loans is the most important piece when determing which model to use.
