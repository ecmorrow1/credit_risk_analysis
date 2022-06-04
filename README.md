# credit_risk_analysis

## Overview

### Purpose

The purpose of this analysis is to assess which ML model is optimized for assessing credit risk based on data that have been provided.  The models in this analysis have utilized oversampling techniques, undersampling, and combination sampling as well as two ensemble methods for supervised machine learning.  Imbalanced data were provided for fitting that contained 68470 low-risk loans and 347 high-risk loans along with several attributes for each loan that are presumed to be contributing factors to the risk status of the loans.

## Results

* When performing Naive Random Oversampling followed by Logistic Regression, the model yields an accuracy score of 0.66, a precision of 0.01, a recall/sensitivity of 0.72, and an F1 of 0.02 when attempting to identify high-risk loans.
![Naive Oversampling](Resources/naive_oversampling.JPG)

* When performing SMOTE oversampling followed by Logistic Regression, the model yields an accuracy score of 0.66, a precision of 0.01, a recall of 0.61 and an F1 of 0.02 when attempting to identify high-risk loans.
![SMOTE oversampling](Resources/smote_oversampling.JPG)

* When performing ClusterCentroids undersampling followed by Logistic Regression, the model yields an accuracy score of 0.55, a precision of 0.01%, a recall/sensitivity of 0.69, and an F1 of 0.01 when attempting to identify high-risk loans.
![ClusterCentroids undersampling](Resources/clustercentroids_undersampling.JPG)

* When performing SMOTEENN combination sampling followed by Logistic Regression, the model yields an accuracy score of 0.68, a precision of 0.01, a recall/sensitivity of 0.78, and an F1 of 0.02 when attempting to identify high-risk loans.
![SMOTEENN combination sampling](Resources/smoteenn_combination.JPG)

* When utilizing the BalancedRandomForestClassifier ensemble method, the model yields an accuracy score of 0.79, a precision of 0.01, a recall/sensitivity of 0.70, and an F1 of 0.06 when attempting to identify high-risk loans.
![BalancedRandomForestClassifier ensemble](Resources/balancedrandomforestclassifier_ensemble.JPG)

* When utilizing the EasyEnsembleClassifier ensemble method, the model yields an accuracy score of 0.93, a precision of 0.09, a recall/sensitivity of 0.92, and an F1 of 0.16 when attempting to identify high-risk loans.
![EasyEnsembleClassifier ensemble](Resources/easyensembleclassifier_ensemble.JPG)

## Summary

Of the models produced in this analysis, assuming the goal is solely to avoid high-risk loans, the preferred model to be utilized is the EasyEnsembleClassifier.  Despite having a fairly low F1 score (0.16), the model is the most successful in positively identifying high-risk loans with a recall/sensitivity of 0.92.  The model also accomplishes the lowest number of improperly identified low-risk loans, which would help to ensure that a minimal amount of low-risk loans aren't mistakenly identified as high-risk.

However, there is also a strong argument for not using any of the models.  Utilizing these models will result in the rejection of several low-risk loans, which will mean missed revenue for the lender.  Given that there are so many more low-risk loans than there are high-risk loans, it may not be worth the lost revenue to try to filter out the high-risk loans.