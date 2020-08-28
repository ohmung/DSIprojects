# DSI Projects

This is a repository of my projects for General Assembly's Data Science Immersive course.

## Project 1: Analysis of SAT and ACT Data 2017/2018
In this project, I will be analyzing the participation rates and scores for students taking SAT and ACT test across US states in 2017 and 2018. I will be exploring the relationship between participation rates across years, tests and scores. State-by-state comparison will also be done. 

The data has demonstrated that high participation rates in a certain test will reflect a low participation rate in the other test. This is particularly consistent with states that set one of two tests as a mandatory test or as a graduation requirement. There is also a negative correlation between participation rates and average test scores. Averages of test scores remain similar across years. Top and low performing states, which did not see a statewide education policy change, remains similar across years.

From the analysis, I propose to increase SAT participation rates in West Virginia, which has not mandate any tests. The growth potential is high as its SAT participation rate has doubled in 2018 and ACT participation rate has had slight decrease. Geographically, it is located next to two states which has higher and increasing SAT participation rates. Strategies to increase participation rates has been suggested for West Virginia. Other than that, I have also recommended other country-wide strategies to focus on. 

## Project 2: Ames, IA Housing Data - Sale Price Prediction Models
In this project, we examine a housing dataset consisting of various attributes and features, along with its sale prices during 2006 to 2010 in Ames, IA. 

We aim to understand which features of a property greatly affect sale prices of houses in Ames, IA using various regression models. After evaluating the performance our models, we optimize a model with best performance to accurately predict housing sale prices when given a set of features. 

The model will be useful for many stakeholders including real estate agents, investors, house owners, and house buyers in a decision-making process by having a benchmark / certainty in prices. It helps them make a more informed decision when calculating the market value of their houses.


## Project 3: Web APIs and Subreddit NLP Classifier
Reddit, an American online community, has over 500 million registered users worldwide. It is broken up into more than a million communities known as “subreddits,” each of which covers a different topic. In this project, we have collected data via the official Reddit API for two popular subreddits:

**r/povertyfinance**: Financial advice, frugality tips, stories, opportunities, and general guidance for people who are struggling financially.

**r/investing**: Advice and opportunities for those actively participating in financial markets.

After removing duplicates and cleaning, we worked with 1890 samples of combined title and content. The samples are then split into training, validation and test dataset. We used two classification models, Naive-Bayes Multinomial and Logistic Regression, each coupled with different vectorizers, Count Vectorizer and TFIDF Vectorizer. The parameters of the vectorizers were optimized using GridSearchCV. We then compared the accuracy, precision and sensitivity scores across the different combination of models and vectorizers. The best performing model was then used to evaluate our test data.

Our final classifier model, Multinomial Naive Bayes with TFIDF Vectorizer,  was able to predict 97.4% of the posts in the test data accurately. It has a precision of 97.8% and sensitivity of 96.7%. This shows that our model was able to classify the posts rather well, which could be due to the difference in nature of the subreddits. However, misclassifications happened when words used were more generic in nature, such as the word 'bank' which in r/povertyfinance may refer to bank recommendations and in r/investing may refer to performance of banking sector. 

Our model found that:
* Topics in r/povertyfinance center around **saving up and restricting spending for the financially challenged**. This includes money-saving tips / frugality (e.g. eggs as part of meals, groceries), basic needs (e.g. dental services), insurance advice, paying debts, and living paycheck to paycheck. 
* Topics in r/investing center around **investing and making financial returns.** This includes stocks, market outlooks, discussions on companies, and earning potentials.

## Project 4: West Nile Virus Prediction in Chicago
This is a Kaggle challenge and we were given 9 files in total which contained the main datasets (train.csv & test.csv) that recorded that number of mosquitoes found in traps set up for mosquito survelliance, spray data of spray efforts of the City of Chicago in 2011 and 2013, weather data from two weather stations in Chicago and map data from Open Streetmap to aid with visualisations.

The task was to build a binary classification model which would accurately predict the presence of the West Nile Virus when given the test datasets. One of the first challenges we faced as a group was to address the null values that were prevalent in the Weather Data, some missing values were imputed from the other Weather Station as there were two Weather Stations within the City, and some weather metrics (SnowFall) that were not relevant to the Mosquito season were dropped. We also accounted for seasonality of the weather by imputing of Wetbulb, StnPressure and Sealevel with Median with the median value of the month. For the train dataset, we concentrated on dropping the Address Accuracy column as we felt that Address infotypes were sufficient to compare against the test datasets for the location of traps along with creating a new column to measure the total number of mosquitoes per trap for that day as every 50 mosquitoes found in the trap sample for that day creates a new entry in the train dataset. As for the spray dataset, we found that the column Time had too many duplicates and null values to justify keeping and so it was dropped.

In order for us to account for weather conditions on the day that the traps were assessed by the CDPH, we merged the train and weather datasets on the Date columns and used only one set of weather data from the nearest weather station to the relevant trap on the train dataset. With our Exploratory Data Analysis, we were interested in looking at patterns that would be strongly correlated to a positive West Nile Virus diagnosis of a mosquito found in those traps. We found less than 500 of the over 8000 samples contained the West Nile Virus and the number of positive cases did not gradually decrease with the spraying efforts. And so, we were interested in examine any seasonal trends that might be prevalent in the number of mosquitoes and which species might be more susceptible to WNV. Our findings showed that the warmer months in the year brought a seasonal increase in the number of mosquitoes and a seasonal decrease in the cooler months and that the spraying efforts were not having the intended effect on the mosquitoes populations which led us to observing that spraying did take place at traps where most WNV positive cases were found.

With this understanding of the impact of spraying, we looked at the weather data to determine more granular weather metrics that would help us in feature engineering for our classification model. Given the disparity between positive and negative cases of mosquitoes having WNV in the target variable, we employed SMOTE oversampling to oversample the datasets. We employed a variety of models to find the best kaggle score and predict the presence of WNV most accurately.

We also looked into the Cost Benefit analysis of spraying and Vector Control in general to help the CDPH make an informed decision on allocation of resources to combat this virus that has costs the US almost 778 million USD in healthcare and lost productivity costs.

## Capstone: Customer Segmentation Analysis with Starbucks: One Size Does Not Fit All
As one of the most successful loyalty programs, 'Starbucks Rewards' has a staggering 16 million active members and represents a significant portion of the coffee chain’s growth. Starbucks attributes 40% of its total sales to the loyalty program and has seen same store sales rise by 7%. The Rewards Program is available on mobile devices as the 'Starbucks' App, which the company uses to market products, send out offers, collect payments, and earn stars (rewards) for freebies.

While mass marketing tactics are still able to get results, the assumption that simply all the members will be interested in what is being promoted is time-consuming, inefficient and expensive.

In this context, the aim of this project is to:

Identify and perform customer segmentation based on their commonalities towards offers
Understanding customer behaviour and providing specific business insights:
What offers should be sent to each customer ?
Which customers we should focus for retention / our most profitable customers?
Which customers to nurture / focus for potential growth?

Our data set contains 17,000 anonymised customer demographics, 306,534 simulated data that mimics customer behavior and customer transactions, and 10 promotional offers or advertisement presented to customers on the Starbucks Rewards mobile app.

Data usually does not usually come in a clean and ready-to-analyze format, and this was the case for my project. The real hard part was to transfer the data in its awkward form to a form I want it to. I had to establish a plan to extract and aggregate the data from 3 different datasets into a segmentable dataset. I used exploratory analysis to see what type of customers existed, and most importantly, their transaction / promotional engagement habits. Among the feature extraction / cleaning efforts, great challenges resulted from customers having repeat exposures to the same offer, identifying valid offer completions and views (in other words, identifying misattributions), and finally aggregating them into view and convertion rates for each offer type to each customer. I have also calculated recency, frequency and monetary (RFM) scores, which is a common method used for analyzing customer value. Ultimately, I created a customer-centric data, where each row represents a unique customer profile whose demographic attributes and spending behaviours are connected to each other. The data disctionary can be seen below.

Customers without complete profiles are also a customer. We had 12.8% of total customer profile that had missing demographics. Rather than imputing their data or removing them completely, I decided to separate their profile to evaluate. Then, I used K-Means clustering, an unsupervised machine learning model, to break up the customers into different segments based on how they would respond to promotions. To optimize the model, I used two evaluation metrics to search for the optimal number of clusters:

Silhouette coefficient (Intercluster distance)
Inertia Scores / Sum of Squared Errors (Intracluster distance)
After running through many iterations using different sets of features, I decided to select only 11 offer-related / behavioural attributes for segmentation (segmentation attributes), and use the remaining demographic (profiling attributes) only to profile the clusters.

My results showed that Starbucks customers fell into 9 different clusters, based mostly on their response and conversion to offers, frequency (number of transactions) and monetary (total spent). I presented an overall summary of their behaviours, demographics and profile.

In addition, I performed an analysis on the offer responsiveness of each cluster. This helps improve marketing focus on what offers to send to customers to ensure effectiveness and optimize our customer acquisition costs. Furthermore, the profitability and life stages of the clusters were also presented. This gives insights into the clusters to focus for retention and clusters to focus on maintaning the relationship / keeping them happy while increasing their purchases. Lastly, I have discovered pockets of potential growth in 4 segments, which Starbucks can focus on to shift these customers into more profitable segments. Two other interesting findings include the misallocation of rewards from non-offer influence and the average revenue generated from offers vs non-offers.

Being aware of these findings and placing priority on important customers will enable Starbucks to optimize their business and drive growth.

