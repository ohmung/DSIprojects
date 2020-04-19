# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Testing, Statistical Summaries and Inference

### Problem Statement

What insights can we extract from the 2017/2018 ACT and SAT test data to improve SAT participation rates? Are there any areas we can focus on?

### Executive Summary

In this project, I will be analyzing the participation rates and scores for students taking SAT and ACT test across US states in 2017 and 2018. I will be exploring the relationship between participation rates across years, tests and scores. State-by-state comparison will also be done. 

The data has demonstrated that high participation rates in a certain test will reflect a low participation rate in the other test. This is particularly consistent with states that set one of two tests as a mandatory test or as a graduation requirement. There is also a negative correlation between participation rates and average test scores. Averages of test scores remain similar across years. Top and low performing states, which did not see a statewide education policy change, remains similar across years.

From the analysis, I propose to increase SAT participation rates in West Virginia, which has not mandate any tests. The growth potential is high as its SAT participation rate has doubled in 2018 and ACT participation rate has had slight decrease. Geographically, it is located next to two states which has higher and increasing SAT participation rates. Strategies to increase participation rates has been suggested for West Virginia. Other than that, I have also recommended other country-wide strategies to focus on. 

### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|ACT/SAT|US state names in the data| 
|sat17_participation|float|SAT|Percentage of SAT takers among high school students in 2017| 
|sat17_read_write|int|SAT|State average scores for SAT Evidence-based Reading and Writing (ERW) in 2017| 
|sat17_math|int|SAT|State average scores for SAT Math in 2017| 
|sat17_final_score|int|SAT|State average total scores for SAT in 2017| 
|act17_participation|float|ACT|Percentage of ACT takers among high school students in 2017| 
|act17_english|float|ACT|State average scores for ACT English in 2017| 
|act17_math|float|ACT|State average scores for ACT Math in 2017| 
|act17_read|float|ACT|State average scores for ACT Reading in 2017| 
|act17_science|float|ACT|State average scores for ACT Science in 2017| 
|act17_final_score|float|ACT|State average composite scores for ACT in 2017|

### Conclusion and Recommendations
#### Key Takeaways
- Participation rates in SAT or ACT is heavily dependent on the state's policy (mandatory or optional). 
- Participation rates are negatively correlated with test scores. 
- Year-to-year average test scores does not show huge differences.
- ACT has a larger proportion of states with mandatory testing, resulting in more states with higher participation rates. 
- SAT has a larger proportion of states with lower participation rates, mostly due to self-selection. It has gained more traction on its participation rates with working with policy stakeholders to make the test state-administered.

#### Overall Recommendations
- Focus on states with no mandatory testing to increase participation rates such as providing free prep classes and working with schools on more engagement activities.
- Remarketing to states that have already made SAT mandatory or have high participation rates.
- Identify states with expiring ACT contracts and work with Education Board or stakeholders. 

#### Suggested State to Focus On
It is suggested that the College Board focuses on West Virginia to increase participation rates. West Virginia has no mandatory tests and students are not restricted to taking any particular test. The SAT participation rates for West Virginia has doubled from 14% to 28%, coinciding with a slight decrease in participation rates for ACT from 69% to 65%. There is huge growth potential. Geographically, it is located next to Pennsylvania and Virginia which has increasing SAT participation rates of more than 60%, and low ACT participation rates of less than 30%. Suggestions on how to increase participation rates are:  

- Partnership with schools by having more engagement activities such as making preparatory materials more accessible in schools, providing talks on scoring techniques and strategies, customized scoring advices, offering scholarships. 

- Increasing popularity with students online: providing preparatory materials online, webinars, working with online tutoring sites / channels.

- Engaging and establishing a good relationship with stakeholders: If SAT becomes administered at state or district level, students would be able to take them for free or at a lower price. This makes it enticing for students. 


#### Additional Data needed
- SAT and ACT test data for a wider range of years
- Participation rates and scores breakdown by district. 