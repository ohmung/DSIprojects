# Project 2: Ames, IA Housing Data - Sale Price Prediction Models

## Problem Statement

The housing market plays an important role in the US economy. Being able to accurately identify factors affecting housing prices and predict prices of housing prices based on a given set of attributes is important for many stakeholders for their financial considerations.

Using our model, we aim to answer the following problems:
* Which features of a property are important in predicting sale prices of houses in Ames, IA, and which contribute to higher prices or lower prices?

* What is the predicted sale price of a house in Ames, IA based on its features?

* What can homeowners in Ames do to improve the saleprice of their homes?

* What should home buyers watch out for?

## Executive Summary

In this project, we examine a housing dataset consisting of various attributes and features, along with its sale prices during 2006 to 2010 in Ames, IA. 

We aim to understand which features of a property greatly affect sale prices of houses in Ames, IA using various regression models. After evaluating the performance our models, we optimize a model with best performance to accurately predict housing sale prices when given a set of features. 

The model will be useful for many stakeholders including real estate agents, investors, house owners, and house buyers in a decision-making process by having a benchmark / certainty in prices. It helps them make a more informed decision when calculating the market value of their houses.

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

### Features that hurt the value of a home the most
* Buuilding Type: Townhouse End Unit

### Things that home owners could improve in their homes to increase the value
* Overall quality and external quality: With a unit increase in overall quality (up to excellent), it increases the house value by \\$ 11800. 
A unit increase in external quality (up to excellent) increase the house value by \\$ 6721. For example, we can repaint the house, replace wallpapers, replace carpet materials and other exterior improvements.
* Kitchen quality: With a unit increase in kitchen quality (up to excellent), the price increases by \\$ 4470. We can consider replacing old or retired appliances should the cost not be more than the unit increase.
* Overall Condition of house: With a unit increase in overall condition (up to excellent), it increases the house value by \\$4518. It is important to keep cleanliness and tidiness of the house, and consider whether to replace retired interior or exterior.
* Functionality: With a unit increase in functionality / maintaining functionality typical, it increases the house value by \\$4216. Keeping functionality of the house at basic level with no deductions is important. We can also installing some affordable smart homes devices.

### Things that house buyers should look out for when purchasing homes
* Renovation prices involving overall quality and external quality: renovation cost of improving overall quality and external quality needs to be considered. Existing good overall quality contribute to house prices greatly, followed by existing good external quality. For example, if the cost to renovate it up to that quality is less, it may be worth renovating a house with lower quality. 
* Year Built of house: Houses built earlier / that are older cost less.
* Renovation prices involving kitchen quality: if there is an intent to improve the kitchen quality, we should consider the cost needed compared to getting another house of a higher kitchen quality.



### Neighborhoods of good investment
The neighborhood a house is situated at plays an important part on sale price. Neighborhoods that have a higher positive effect on pricing include Northridge Heights, Stone Brook, NorthRidge. Among all neighborhoods, Greenhill is the most expensive. In this case, investing in Northridge Heights, Stone Brook, and NorthRidge are a better option.


### Recommendations & Further Research
* Certain features in the dataset (square feet, quality) in Ames could be generalized to other cities in USA of similar GDP or markets. Features such as neighborhood specific to Ames would need to be removed to make the model more universal for other cities. Factors like fireplaces, heating would also be affected depending on the temperatures in the other USA cities. Supply and demand indices of housing in each city would be needed as well.
* The dataset captures only houses sold during 2006 - 2010 in Ames. We may not be able to generalize the result for use in present day due to external factors such as inflation, economical outlook of the year, availability of mortgages, supply and demand of housing and more.
* The dataset primarily captures house features and minamlly on nearby amenities (park, railroad). Other factors would include ease of access to supermarkets / hospital / schools / eateries, and distance from city centre. Factors like crime rates, fire-prone, flood potential, unforseen developments, traffic conditions are also important.
* The dataset does not have a lot of samples with sale prices > $400,000. To predict the prices of higher-valued homes, more datasets are needed.