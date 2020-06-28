# Customer Segmentation Analysis with Starbucks: One Size Does Not Fit All

Qi-Wen Ng | General Assembly Singapore | DSI-14 | June 2020

## Introduction

The ‘average customer’ is a concept of the past. Hitting the average does not mean hitting the majority, and this one-size-fits-all strategy does not work for businesses anymore.  Today, understanding our customers and personalization is key to establish stronger customer relationships and ultimately, sustain a profitable business. Given a diverse set of customer attributes, how can we identify and create experiences for effective acquisition and retention? Enter "customer segmentation", where we break the customer base into groups that share similiarities such as demographics, psychographics, behavioural, geographic, etc.

Businesses need to be able to segment their customers for:
- Marketing: 
    - Create and tailor marketing messages resonating with each segments based on their real or likely behavior, so that businesses can engage with them more effectively. 
    - Better ROI from Marketing

- Sales: 
    - Identify profitable segments to target customers in that segment to boost profits or identify pockets of growth by shifting people into more profitable segments.
    - Retaining existing customers or attracting new customers with the correct profile
    - Identify the most valuable customers and understanding their trends in order to build the relationship further

- Operations:
    - Stock management by understanding the products that are in demand to reduce overstocking / storage costs or improve logistics
    
- Products:
    - Evaluate product offerings or improve specific products. 


## Problem Statement

As one of the most successful loyalty programs, 'Starbucks Rewards' has a staggering 16 million active members and represents a significant portion of the coffee chain’s growth. Starbucks attributes 40% of its total sales to the loyalty program and has seen same store sales rise by 7%. The Rewards Program is available on mobile devices as the 'Starbucks' App, which the company uses to market products, send out offers, collect payments, and earn stars (rewards) for freebies. 

While mass marketing tactics are still able to get results, the assumption that simply all the members will be interested in what is being promoted is time-consuming, inefficient and expensive. 

In this context, the aim of this project is to:
- Identify and perform customer segmentation based on their commonalities towards offers
- Understanding customer behaviour and providing specific business insights:
    - What offers should be sent to each customer ? 
    - Which customers we should focus for retention / our most profitable customers?
    - Which customers to nurture / focus for potential growth?


## Executive Summary
---
Our data set contains 17,000 anonymised customer demographics, 306,534 simulated data that mimics customer behavior and customer transactions, and 10 promotional offers or advertisement presented to customers on the Starbucks Rewards mobile app.

Data usually does not usually come in a clean and ready-to-analyze format, and this was the case for my project. The real hard part was to transfer the data in its awkward form to a form I want it to. I had to establish a plan to extract and aggregate the data from 3 different datasets into a segmentable dataset. I used exploratory analysis to see what type of customers existed, and most importantly, their transaction / promotional engagement habits. Among the feature extraction / cleaning efforts, great challenges resulted from customers having repeat exposures to the same offer, identifying valid offer completions and views (in other words, identifying misattributions), and finally aggregating them into view and convertion rates for each offer type to each customer. I have also calculated recency, frequency and monetary (RFM) scores, which is a common method used for analyzing customer value. Ultimately, I created a customer-centric data, where each row represents a unique customer profile whose demographic attributes and spending behaviours are connected to each other. The data disctionary can be seen below.

Customers without complete profiles are also a customer. We had 12.8% of total customer profile that had missing demographics. Rather than imputing their data or removing them completely, I decided to separate their profile to evaluate. Then, I used K-Means clustering, an unsupervised machine learning model, to break up the customers into different segments based on how they would respond to promotions. To optimize the model, I used two evaluation metrics to search for the optimal number of clusters:
- Silhouette coefficient (Intercluster distance)
- Inertia Scores / Sum of Squared Errors (Intracluster distance)

After running through many iterations using different sets of features, I decided to select only 11 offer-related / behavioural attributes for segmentation (segmentation attributes), and use the remaining demographic (profiling attributes) only to profile the clusters. 

My results showed that Starbucks customers fell into 9 different clusters, based mostly on their response and conversion to offers, frequency (number of transactions) and monetary (total spent). I presented an overall summary of their behaviours, demographics and profile. 

In addition, I performed an analysis on the offer responsiveness of each cluster. This helps improve marketing focus on what offers to send to customers to ensure effectiveness and optimize our customer acquisition costs. Furthermore, the profitability and life stages of the clusters were also presented. This gives insights into the clusters to focus for retention and clusters to focus on maintaning the relationship / keeping them happy while increasing their purchases. Lastly, I have discovered pockets of potential growth in 4 segments, which Starbucks can focus on to shift these customers into more profitable segments. Two other interesting findings include the misallocation of rewards from non-offer influence and the average revenue generated from offers vs non-offers.

Being aware of these findings and placing priority on important customers will enable Starbucks to optimize their business and drive growth.


### Data Dictionary

| Features                  | Data Type | Remarks                                                            |
| --------------------------| ----------| ------------------------------------------------------------------ |
| customer_id               | string    | unique customer identifier                                         |
| gender	                | string    | gender of the customer: male(M), female(F), other(O), none (nan)   |
| age                       | float     | age of the customer                                                |
| income                    | float     | income of the customer
| became_member_on          | datetime  | date the customer became a member                                  |
| days_as_member            | int       | number of days the customer became a member since 31 December 2018 
| bogo_received             | float     | number of bogo offers received
| bogo_viewed               | float     | number of bogo offers viewed
| bogo_completed            | float     | number of bogo offers completed
| bogo_rewarded             | float     | number of bogo offers rewarded
| bogo_viewed_rate          | float     | view rates of bogo offers
| bogo_conversion_rate      | float     | conversion rates of bogo offers
| discount_received         | float     | number of discount offers received
| discount_viewed           | float     | number of discount offers viewed 
| discount_completed        | float     | number of discount offers completed
| discount_rewarded         | float     | number of discount offers rewarded
| discount_viewed_rate      | float     | view rates of discount offers
| discount_conversion_rate  | float     | conversion rates of discount offers
| info_received             | float     | number of informational offers received
| info_viewed               | float     | number of informational offers viewed
| info_viewed_rate          | float     | view rates of informational offers
| total_received            | float     | total number of offers received 
| total_viewed              | float     | total number of offers viewed
| total_completed           | float     | total number of offers completed 
| overall_view_rate         | float     | overall view rates
| overall_conversion_rate   | float     | overall ratio of offers completed compared to how many received |
| total_rewarded            | float     | total rewards given to the customer
| num_transactions          | float     | number of monetary transactions done by the customer
| offer_num_transactions    | float     | number of offer-associated monetary transactions done by the customer
| actual_num_transactions   | float     | number of non-offer monetary transactions done by the customer
| total_spent               | float     | total amount spent by the customer across all transactions
| offer_spent               | float     | total offer-associated amount spent by the customer
| actual_spent              | float     | total non-offer amount spent by the customer
| avg_spent                 | float     | average amount spent by the customer across all transactions
| min_spent                 | float     | lowest amount spent of the customer
| max_spent                 | float     | highest amount spent of the customer
| recency                   | float     | how recent the customer spent


## 4. Conclusion & Recommendations

### Key Findings & Recommendations
- After identifying the valid completed offers, I realized that 25.67% of the rewards given were not actually completed due to offer influence, but completed as a result of the customer's normal behavior. Essentially, there would have been more revenue should these incorrectly given rewards were avoided.

- Although there were 116,752 non-offer transactions compared to only 22,201 offer-related transactions, the average offer-related spent per transaction was \\$19.73, compared to \\$11.46 for non-offer spent. Hence, running offers would help when we need to quickly generate additional revenue or hit sales targets. 

- Improve marketing focus: To optimize our customer acquisition costs for marketing campaigns, I have identified segments that resonate better with specific offers - BOGO only, DISCOUNT only, BOGO & DISCOUNT, INFORMATIONAL, and NOT INTERESTED. We can use this strategy to push offers to the relevant segments to ensure their effectiveness in convertions and response. With these costs optimized, we can reallocate funds to other campaigns or departments or to improve customer experience or the rewards program and innovate to adapt to the customer's changing needs.

- Identified the most and least profitable customers: I have distinguished our customers by their profitability and life stage or value of customer. This gives insights into the clusters to focus for retention and clusters to focus on maintaning the relationship / keeping them happy while increasing their purchases. 

- Lastly, I have discovered pockets of potential growth in 4 segments, which Starbucks can focus on to shift these customers into more profitable segments.


### Limitations & Further Research
- 12.8% of our customers had missing demographics (and although we are unaware, we will also have made-up demographics). Realistically, this is the case and we are unable to force the customers for accurate information. However, if I had such information, the segmentation and profiling may be more detailed and would provide more insights. One way to encourage users may be do incentivize this.

- Identifying misattributions took up a great amount of time. Nevertheless, as much as I try to determine these (and going back and forth after finding them), it will not be perfect. We can consider confirming completion of offers using separate redemption mechanisms (rather than auto) in the Starbucks app or implement a tracking system.

- As the dataset is only across a 30-day test period, we are unable to identify the spending patterns prior to this. Hence, the footsteps of customers become active and loyal from the start of their membership, or customers that eventually churn are unknown. If we had known this, a recommendation system of offers can be built for new members to engage them effectively. 

- There was no information on how the data was collected. Hence, some assumptions had to be made after identifying the funnel and doing exploratory data analysis.

- For model improvements, it would be interesting to explore other clustering algorithm, such as hierarchical clustering, to compare and improve our customer segmentation. In the above visualization with TSNE, there are some overlaps within clusters. Furthermore, the silhouette scores are relatively low (around 0.20-0.25). 


- Generate more accurate data by having tracking on the source of each event (receive, view, completion). This will help identify the influence of marketing channels. 

- Explore informational offers to evaluate their impact. To idenfity if there had been a purchase within the duration of the informational offer.  

- Explore in-depth the impact of offer attributes (duration, rewards, difficulty) and how they affect response and spending behaviours

- Explore data down to the product line. For example, many Starbucks BOGO offers involve new and seasonal drinks, which may receive very different reactions depending on how conservative or adventurous is the recipient of the offer.

- Building prediction models for predicting customer response to offers, customer lifetime value prediction, churn prediction, next purchase day / likelihood of purchase.