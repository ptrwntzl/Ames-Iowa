# General Assembly Project 2: Linear Regression Modeling of Ames Housing Data

#### Peter Wentzel
---


## Problem Statement

Residential house pricing is subject to many factors both subjective and numerically quantifiable.  The wide range of properties that can affect the value of property need to be considered when appraising a current lot or considerations are made for future developments/projects.  The goal of this project is to analyze a data set of home sales between 2006 and 2010 provided by the Ames Assessor’s office to gain more understanding of the metrics and features that give a home its value.  Ultimately by evaluating feature correlation and engineering of features the aim is to create a linear regression model that accurate predicts the sale price of a home. 

## Executive Summary

The data for this project consists of a training set and test set of home sale prices with included features to gain more insight into determining factors on the sale price.  Per the data dictionary provided with the data set, the data has 82 columns which include 23 nominal, 23 ordinal, 14 discrete, and 20 continuous variables.  Sale condition was omitted so therefore only 81 columns are present in the training set and of course sale price is omitted from the testing set.  

Data was cleaned and no rows were removed from the data set.  Null values were typically re-assigned to a feature not being present for a lot as opposed to being removed from the data set.  One feature had many numerical values missing (lot frontage is possibly not available for all lots) and was engineered with respect to the lot area.  This may cause bias issues, but model results seemed respectable.  Location and general house type were dummied to provide features that measured the effect of the overall location of the house and general style of the house.  A regular lot configuration interaction was created as most lots are not irregular in shape and are located in-line with the road they are on.  Additionally, a high leverage metric was created based on values from multiple features that accentuated higher priced homes and performed well in the model at garnering variance. 

A linear regression model was created from the training data using regular linear regression, lasso and ridge models in the scikit learn library.  The data was scaled using standard scaler help removing issues of larger values of data skewing results.  At one point the sale price was converted to a log scale to attempt to create better model performance, but it was found to create any meaningful changes regarding this model.  Lasso was found to perform the best of the three methods.  The baseline null model R^2 was -4.33*10^4 for the testing set and -1.56*10^-10 for the training set.  Lasso fit the model to an R^2 score of 0.874 and an RMSE 2.78*10^4.  


## Recommendations for Future Work 

Future work should focus on creating better interaction terms to help define edge cases better.  Additionally, by creating these better interactions terms it can help determine what realtors and residential building companies can focus on feature wise regarding sales/creating a better product.  Potentially looking at other modeling techniques to evaluate correlation and scoring metrics could also help in getting a better idea of geographical/location based information then the metrics used in the Ames set.

## Data Dictionary

Please see the 'data information.txt' in the project repo for the data information for this study.

