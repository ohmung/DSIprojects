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
