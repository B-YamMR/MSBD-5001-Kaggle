# MSBD-5001-Kaggle 19Fall
MSBD 5001 Individual Project

Draw 2D plots to make intuitive observe
 - Found that playtime is most related to 'total_positive_reviews' and 'total_negative_reviews'

Data Cleansing
 - Drop rows in training set which hava empty value
 - Fill in with mode in column 'total_negative_reviews' and 'total_positive_reviews' in testing set
 - Fill in with previous data in column 'purchase_date' and 'release_data' in testing set
 
Feature Engineering
 - Add feature: interval of purchase_date and release_date ('pur_rel_itv')
 - One-hot column 'genres'
 - Fix skewness in 'price','total_positive_reviews' and 'total_negative_reviews'
 - PCA(the main purpose of PCA here is not decompsition but get rid of correlation)

Feature Selection:
 - Drop columns: 'playtime_forever','is_free','price','total_positive_reviews','total_negative_reviews','genres', 'categories', 'tags', 'purchase_date','release_date'

Modeling & Evaluation: Try 14 models
 - Linear Regression
 - Ridge
 - Lasso
 - Random Forest Regressor
 - Gradient Boosting Regressor
 - SVR
 - LinearSVR
 - Elastic Net
 - SGD Regressor
 - Bayesian Ridge
 - KernelRidge
 - Extra Trees Regressor
 - XGB Regressor
 - AdaBoost Regressor

Pick Top 8 Models after Fine Tuning:(sorted from best -> worst)
 - KernelRidge
 - SVR
 - Bayesian Ridge
 - Ridge
 - Lasso
 - Random Forest Regressor
 - XGB Regressor
 - Elastic Net
* Some of the model perform worse after fine tunning, which is little confusing...

Fine Tuning Parameters:
 - NEED A LOT OF WORK MAN...
 
Ensemble Methods:
 - Assign weighted average to each model
 - Stacking(Use KernelRidge,SVR,Bayesian Ridge,Ridge,Lasso,Random Forest Regressor,XGB Regressor,Elastic Net in layer-1, and KernelRidge in layer-2)

Submission
