# Project 3: Web APIs and Subreddit NLP Classifier

## Problem Statement

Technological advances have revolutionized the ways in which human communicate. It has infiltrated almost every aspect of our lives, and social media is one of the biggest recipients of its influence. With this rise, many people are now turning into social media as a source for rich and valuable information, and one of which is for personal financial advice. Today, many people are tech savvy and know how to research what they want to know before making a decision or seeking advice from advisors.

However, obtaining information from the right portals would be dependent on the nature of the portals, especially for users coming from different financial goals and conveying sensitive information in anonymity. 

With such, I aim to create a model that classifies two popular finance-related online communities on Reddit: r/povertyfinance and r/investing. Using our model, we aim to address the following problems: 

- Individuals: Which subreddit should I obtain information, seek advice from or share my experience, given my financial situation? 

- Financial Advisors: What topics would my existing or potential clients be interested about that I should study into it?

- Personal Finance Blogs / Websites: What topics are the community discussing about, and what kind of content can I share to improve engagements or visits?

## Executive Summary

Reddit, an American online community, has over 500 million registered users worldwide. It is broken up into more than a million communities known as “subreddits,” each of which covers a different topic. In this project, we have collected data via the official Reddit API for two popular subreddits:

**r/povertyfinance**: Financial advice, frugality tips, stories, opportunities, and general guidance for people who are struggling financially.

**r/investing**: Advice and opportunities for those actively participating in financial markets.

After removing duplicates and cleaning, we worked with 1890 samples of combined title and content. The samples are then split into training, validation and test dataset. We used two classification models, Naive-Bayes Multinomial and Logistic Regression, each coupled with different vectorizers, Count Vectorizer and TFIDF Vectorizer. The parameters of the vectorizers were optimized using GridSearchCV. We then compared the accuracy, precision and sensitivity scores across the different combination of models and vectorizers. The best performing model was then used to evaluate our test data.

Our final classifier model, Multinomial Naive Bayes with TFIDF Vectorizer,  was able to predict 97.4% of the posts in the test data accurately. It has a precision of 97.8% and sensitivity of 96.7%. This shows that our model was able to classify the posts rather well, which could be due to the difference in nature of the subreddits. However, misclassifications happened when words used were more generic in nature, such as the word 'bank' which in r/povertyfinance may refer to bank recommendations and in r/investing may refer to performance of banking sector. 

Our model found that:
* Topics in r/povertyfinance center around **saving up and restricting spending for the financially challenged**. This includes money-saving tips / frugality (e.g. eggs as part of meals, groceries), basic needs (e.g. dental services), insurance advice, paying debts, and living paycheck to paycheck. 
* Topics in r/investing center around **investing and making financial returns.** This includes stocks, market outlooks, discussions on companies, and earning potentials.


### Data dictionary
The data dictionary for the final dataset that was cleaned is shown below:

|Feature|Type|Description|
|---|---|---|
|subreddit|integer|1 represents r/investing, 0 represents r/povertyfinance| 
|alltext|object|Combined title and content of each in thread in the subreddits|

 
### Contents

1. Data Collection - Web Scraping
2. Data Cleaning & Exploratory Data Analysis
3. Modelling
    * Split Dataset into Train, Validation and Test
    * Classification Models
        * Naive Bayes
            * Count Vectorizer
            * TFIDF Vectorizer
        * Logistic Regression
            * Count Vectorizer
            * TFIDF Vectorizer
    * Summary of Scores
4. Model Evaluation on Test Data
5. Conclusion and Recommendations

## Conclusion and Recommendations

### Key Findings
Our final classifier model, Multinomial Naive Bayes with TFIDF Vectorizer,  was able to predict 97.4% of the posts in the test data accurately. It has a precision of 97.8% and sensitivity of 96.7%. 

Misclassifications happened when words used were more generic in nature, such as the word 'bank' which in r/povertyfinance may refer to bank recommendations and in r/investing may refer to performance of banking sector or 'index' in r/povertyfinance was a different context when in r/investing. Another example is ‘nugget’ referring to a gold nugget investing term, 'wendy' as a company in terms of share for r/investing. 


* Individuals can identify subreddits to explore based on the below:
    * Topics in r/povertyfinance center around **saving up and restricting spending for the financially challenged**. This includes money-saving tips / frugality (e.g. eggs as part of meals, groceries), basic needs (e.g. dental services), insurance advice, paying debts, and living paycheck to paycheck. 
    * Topics in r/investing center around **investing and making financial returns.** This includes stocks, market outlooks, discussions on companies, and earning potentials.

* Financial Advisors / Personal Finance Blogs / Websites: 
    * The model has been able to show what are the hot topics being discussed. 
    * The model can provide a quick overview to these blogs and websites to create more of such content, especially times-sensitive ones in order to improve engagement and visits. For example, in r/povertyfinance the word 'deposit' was commonly seen due to a recent stimulus check (or Econonomic Impact Payment) received by Americans under the Coronavirus Aid, Relief, and Economic Security (CARES) Act. https://smartasset.com/financial-advisor/coronavirus-stimulus-checks-how-much-will-you-get 
    * The model can provide insights to financial advisors on what their existing or potential clients would be interested in, to improve their advisory services to clients. For example, 'airline' and 'tesla' appear frequently in r/investing in recent posts. 


### Recommendations & Further Research
* Removal of noise words such as 'amp'. Increasing n-grams to get more context on more generic terms across subreddits.

* Explore other tools: Instead of classifying posts using frequency of words, we can consider using word similarities/analogies such as word2vec. We can also consider using stemming instead of lemmatizing for our words. 
 
* Increase our training dataset in size and of a longer timeline: Our dataset contains only a small section of the subreddit over a short period of time and may not cover a good spectrum of content. We can also consider incorporating the comments section into our data for a larger corpus. 

* Explore relationships between content, number of comments, and upvote ratios.

