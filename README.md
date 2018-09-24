# House-price-Advanced-Regression-Techniques
Kaggle competition

Project made by:

* Davide Aureli
* Valerio Guarrasi
* Andrea Marcocchia

Kaggle account -- The PODS --


**Cleaning Data-1**: reformatted character variables to numeric, without grouping them. So each observations has its respective value.
**Cleaning Data-2**: drop off all the variables that have been numeric and are no longer needed. 
**Cleaning Data-3**: replace NA values using:

- 0 -> if NA meant that the feature doesn’t exist
- mode -> if the feature is discrete and NA is a lack of information
- mice package with classification and regression trees method (cart)

**Feature engineering-1**: created new features based on correlation between variables in train dataset 
**Feature engineering-2**: removed outliers following GrLivArea.

All the operations above are done for train and test dataset.


**Model selection-1**: Linear Model:

- standardize all the variables except dicotomical variables and SalePrice
- apply logarithm to SalePrice
- estimate the linear model using “backward elimination” algorithm to choose the variables to removeà score = 0.12372

**Model selection-2**: XGBoost:

- transform the train and test dataframes in Sparse Matrix Object
- estimate the XGBoost model with parameter declared in paramà score = 0.12047

**Model selection-3**: LASSO:

- use the cross-validation method to estimate the parameters
- estimate the LASSO model with parameter estimated beforeà score = 0.12106
Model selection-4: Evaluated weighted mean between the three previous methods with the respective
weights: 10%, 68% and 22%.


**Kaggle score: 0.11624**
