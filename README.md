# Credit_Risk_Analysis
Determining credit risk using scikit-learn and imbalanced-learn

## Overview of Project
The goal of this project was to teach the basics of machine learning, with broad coverage on many use cases and various models. Chiefly, an analysis and learning functions were run on a dataset that showed qualification for home loans, based on a variety of factors. The algorithms, in some cases, are able to rank the most important metrics within the analysis, to better refine the model and gain more and more accurate results.

### Results
Balanced Accuracy scores will be listed in descending order by model, along with their associated Classification Reports:

The highest accuracy model by far - which can be an indicator of overfitting, but may also be a simple side effect of the multiple logic progression - is the EasyEnsemble ADA Boost model.

The recall (or accuracy at predicting) is above 90% for both high and low risk categories, and performs solidly across other metrics as well. As will be seen as a theme here, the High_risk data has an extremely low precision rating, which is indicative of higher sensitivity. When catching non-qualified buyers, higher sensitivity would be preferred to precision, so as to not issue a loan to an individual that will not be able to pay it back within the terms of the loan agreement. Should a decline be issued in error, a second application would assist the model by providing data to show which applications may actually qualify that did not on the first time around.

<img width="152" alt="1 EasyEnsembleADA" src="https://user-images.githubusercontent.com/116296092/224591390-9c19bfa0-c4fc-46b1-8256-23f9d2b0ebcc.png">
<img width="597" alt="1 5 EEC CRI" src="https://user-images.githubusercontent.com/116296092/224591400-06f75df8-39a5-4483-9029-f4a575f17684.png">

Coming in at a close second, the BalancedRandomForest model performed second best, arguably for similar reasons. Run with 100 iterations, the overall accuracy is not much lower than the ADA model at a ~7% decrease, but the recall scores are drastically lower than those of the ADA Model.

<img width="147" alt="2 BalancedRF" src="https://user-images.githubusercontent.com/116296092/224591412-efc2fabf-dcbe-4ccd-9fa2-f7c2e99439fc.png">
<img width="600" alt="2 5 BRF CRI" src="https://user-images.githubusercontent.com/116296092/224591416-f5a824df-62f9-4e01-bb04-11acf6ae6cf1.png">

Third is the SMOTEENN model, with yet more decreases in the overall accuracy and recall scores

<img width="142" alt="3 SMOTEENN" src="https://user-images.githubusercontent.com/116296092/224591434-d0a48eb2-62c1-4d70-a217-4536dc95e439.png">
<img width="598" alt="3 5 SMOTEENN" src="https://user-images.githubusercontent.com/116296092/224591439-b49476e1-d8b9-4a10-a4d5-0464e2e45b71.png">

Fourth is the SMOTE algorithm, the base version of SMOTEENN. These scores are similar as the models run in similar ways when predicting data in a set. While SMOTEENN has a slightly higher accuracy, the recall scores on the base SMOTE algorithm are actually better than SMOTEENN.

<img width="128" alt="4 SMOTE" src="https://user-images.githubusercontent.com/116296092/224591452-2dc3c1cf-e779-404e-8533-b4a771fdb782.png">
<img width="598" alt="4 5 SMOTE" src="https://user-images.githubusercontent.com/116296092/224591459-aa6fcdcf-7507-4cb5-99a2-7853c23b4740.png">

Fifth is the RandomOversampling model, which clocks slightly lower on the model's accuracy overall. However, there is a marked difference in recall, with scores decreasing nearly 10% for high risk, and 8% for low risk (which is nearly on par with SMOTEENN, potentially ruling RO out based on total accuracy being so much lower, without a strong factor to make up for it).

<img width="140" alt="5 RandomOversampling" src="https://user-images.githubusercontent.com/116296092/224591473-27ea42c2-76eb-4e91-a6ec-761e7458e7d9.png">
<img width="599" alt="5 5 ROS CRI" src="https://user-images.githubusercontent.com/116296092/224591481-0981ec0c-eece-4d36-b718-8524dab8a777.png">

Sixth, and certainly least, is the CLusterCentroids model. With how diverse the data is, and approval ratings being as (seemingly) random as they are, it's not necessarily easy to split the data as CC attempts to do. Scoring an astounding 54% overall accuracy, and terrible recall scores, there would be no reason to use this model to predict whether a borrower would be qualified for a loan to purchase a house.

<img width="142" alt="6 Centroids" src="https://user-images.githubusercontent.com/116296092/224591496-ae8b221a-3b38-472d-b17c-08565222bf5f.png">
<img width="599" alt="6 6 Centroids" src="https://user-images.githubusercontent.com/116296092/224591508-46c52eaa-672d-4011-bd31-10145b1945bf.png">

## SUMAMRY
Overall, the models that utilized ensemble learning outclassed the more "traditional" models in every way. They are more accurate as a whole, provide greater insight into the data and whether an interested party would qualify for a loan, and are overall a better fit for the types of answers we are seeking in this challenge. A strong argument is made for EasyEnsemble, at 94% high risk recall. When determining a member's loan risk, it is far more beneficial to know who you don't want to or can't issue money to than who you can, and thus having higher recall in that category would be of greater help than a higher rating for determining low risk applicants, such as is present in the Centroids algorithm.
