# Credit_Risk_Analysis
Determining credit risk using scikit-learn and imbalanced-learn

## Overview of Project
The goal of this project was to teach the basics of machine learning, with broad coverage on many use cases and various models. Chiefly, an analysis and learning functions were run on a dataset that showed qualification for home loans, based on a variety of factors. The algorithms, in some cases, are able to rank the most important metrics within the analysis, to better refine the model and gain more and more accurate results.

### Results
Balanced Accuracy scores will be listed in descending order by model, along with their associated Classification Reports:

The highest accuracy model by far - which can be an indicator of overfitting, but may also be a simple side effect of the multiple logic progression - is the EasyEnsemble ADA Boost model.

The recall (or accuracy at predicting) is above 90% for both high and low risk categories, and performs solidly across other metrics as well. As will be seen as a theme here, the High_risk data has an extremely low precision rating, which is indicative of higher sensitivity. When catching non-qualified buyers, higher sensitivity would be preferred to precision, so as to not issue a loan to an individual that will not be able to pay it back within the terms of the loan agreement. Should a decline be issued in error, a second application would assist the model by providing data to show which applications may actually qualify that did not on the first time around.

IMAGES

Coming in at a close second, the BalancedRandomForest model performed second best, arguably for similar reasons. Run with 100 iterations, the overall accuracy is not much lower than the ADA model at a ~7% decrease, but the recall scores are drastically lower than those of the ADA Model.

IMAGES

Third is the SMOTEENN model, with yet more decreases in the overall accuracy and recall scores

IMAGES

Fourth is the SMOTE algorithm, the base version of SMOTEENN. These scores are similar as the models run in similar ways when predicting data in a set. While SMOTEENN has a slightly higher accuracy, the recall scores on the base SMOTE algorithm are actually better than SMOTEENN.

IMAGES

Fifth is the RandomOversampling model, which clocks slightly lower on the model's accuracy overall. However, there is a marked difference in recall, with scores decreasing nearly 10% for high risk, and 8% for low risk (which is nearly on par with SMOTEENN, potentially ruling RO out based on total accuracy being so much lower, without a strong factor to make up for it).

IMAGES

Sixth, and certainly least, is the CLusterCentroids model. With how diverse the data is, and approval ratings being as (seemingly) random as they are, it's not necessarily easy to split the data as CC attempts to do. Scoring an astounding 54% overall accuracy, and terrible recall scores, there would be no reason to use this model to predict whether a borrower would be qualified for a loan to purchase a house.

IMAGES

## SUMAMRY
Overall, the models that utilized ensemble learning outclassed the more "traditional" models in every way. They are more accurate as a whole, provide greater insight into the data and whether an interested party would qualify for a loan, and are overall a better fit for the types of answers we are seeking in this challenge. A strong argument is made for EasyEnsemble, at 94% high risk recall. When determining a member's loan risk, it is far more beneficial to know who you don't want to or can't issue money to than who you can, and thus having higher recall in that category would be of greater help than a higher rating for determining low risk applicants, such as is present in the Centroids algorithm.