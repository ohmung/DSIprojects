# Project 2: Ames, IA Housing Data - Sale Price Prediction Models

## Problem Statement

Which features of a property are important in predicting sale prices of houses in Ames, IA?

Which features of a property contribute to higher prices or lower prices of houses in Ames, IA?

What is the predicted sale price of a house in Ames, IA based on its features?

What can homeowners in Ames do to improve the saleprice of their homes?

## Executive Summary

In this project, we examine a housing dataset consisting of various attributes and features, along with its sale prices during 2006 to 2010 in Ames, IA. 

We aim to understand which features of a property greatly affect sale prices of houses in Ames, IA using various regression models. After evaluating the models, we shortlist key features that are important in predicting housing sale prices in Ames, IA.

### Contents

1. Data Import & Cleaning 
    * Libraries
    * Import Train and Test Data
    * Rename Columns
    * Check Null Values
    * Update Column Data Types
    * Check Outliers


2. Exploratory Data Analysis
    * Histograms: Numerical Columns Distribution
    * Scatter Plots: Numerical Columns vs Sale Price
    * Bar Charts: Categorical Columns Distribution
    * Box Plots: Categorical Columns vs Sale Price
  
  
3. Pre-processing
    * Encode / Map: Categorical data
    * Encode / Map: Ordinal Columns
    * Dummies: Categorical columns
    * Features matrix (`X`) and target vector (`y`)
    * Train/Test Split Training Data
    * Scaling


4. Modelling
    * Candidate Models and Hyperparameters 
        * Linear Regression
        * Ridge
        * Lasso
        * ElasticNet
    * Evaluate Models on Test Data
        * Linear Regression
        * Ridge
        * Lasso
        * ElasticNet


5. Features Selection
    * Selected Features
    * Final Model with Selected Features
    
    
6. Kaggle Submission


7. Conclusions and Recommendations

## Conclusions and Recommendations

Our ElasticNet Model, scaled with StandardScaler performed best on predicting the sale prices of houses in Ames, IA. 


### Features that add the most value to a home
* GrLivArea: Above grade (ground) living area square feet
* OverallQual: Overall material and finish quality
* BsmtFinSF1: Basement Type 1 finished square feet
* YearBuilt
* Neighborhood: Northridge Heights
* Neighborhood: Stone Brook
* TotalBsmtSF: Total square feet of basement area
* ExterQual: Exterior material quality
* LotArea: Lot size in square feet
* MasVnrArea: Masonry veneer area in square feet
* Overall Condition
* Kitchen Quality
* Sale Type: New
* Typical Functionality
* GarageArea: Size of garage in square feet
* LotBsmtExposure: Walkout or garden level basement walls

### Features hurt the value of a home the most
* Old age of house at sale 
* Building Type: Townhouse End Unit


### Things that homeowners could improve in their homes to increase the value
* Overall material and finish quality: repainting the house, replacing wallpapers, replacing carpet materials and other exterior improvements.
* Kitchen quality: replacing old or retired appliances.
* Overall Condition of house: keep cleanliness and tidiness, replacing retired interior or exterior.
* Functionality: Keeping functionality of the house at basic level with no deductions, installing smart homes devices.
* Fireplace: adding fireplaces


### Neighborhoods of good investment
The neighborhood a house is situated at plays an important part on sale price. Neighborhoods that have a higher positive effect on pricing include Northridge Heights, Stone Brook, NorthRidge. Among all neighborhoods, Greenhill is the most expensive. In this case, investing in Northridge Heights, Stone Brook, and NorthRidge are a better option.

### Recommendations
* Certain features in the dataset (square feet, quality) in Ames could be generalized to other cities in USA of similar GDP or markets. Features such as neighborhood specific to Ames would need to be removed to make the model more universal for other cities. Factors like fireplaces, heating would also be affected depending on the temperatures in the other USA cities. Supply and demand indices of housing in each city would be needed as well.
* The dataset captures only houses sold during 2006 - 2010 in Ames. We may not be able to generalize the result for use in present day due to external factors such as inflation, economical outlook of the year, availability of mortgages, supply and demand of housing and more.
* The dataset primarily captures house features and minamlly on nearby amenities (park, railroad). Other factors would include ease of access to supermarkets / hospital / schools / eateries, and distance from city centre. Factors like crime rates, fire-prone, flood potential, unforseen developments, traffic conditions are also important.
