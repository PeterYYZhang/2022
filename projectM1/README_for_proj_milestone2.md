# Let us make the most popular beer!

## Abstract
<!--
Over the 20 years, beer rating websites have attracted plenty of users to give ratings and reviews about beers.
As time passes, what is the trend of people's favorite beer styles changing in a specific region? How can breweries make changes to their products? Which areas should breweries lay more emphasis on? Meanwhile, how can we detect fake reviews and ratings? Because we cannot ensure that all the reviews are trustworthy, breweries might pay users to give high ratings, or some users rate the beer carelessly.
In this project, we aim to solve the above questions.-->

Over the 20 years, beer rating websites have attracted plenty of users to give ratings and reviews about beers.
As time passes, people may change their preference for beer. We intend to use the review and scores of different beers on BeerAdvocate and RateBeer websites. To determine which factors have the most significant influence on beer's overall rating. And give production or sales suggestions to the breweries in the different regions.
Due to the increasing number of negative reviews and water army, the consumer would easily be affected by these grading. We would like to know if this phenomenon also happened in our dataset. Because negative reviews are generally random text, we intend to train the model using reviews as input and ratings as labels. Thus detecting malicious reviews and eliminating this affection.



## Research questions
1. Which aspect of the beer influences the overall rating of the beer the most?
2. What is the relation between descriptive reviews and Overall scores? 
3. What is the shift in people's preference for beer style over some time? How do we use the trend to give some brewing advice to Brewery?
4. Whether the data exist fake reviews and rating. How do we distinguish the sham rating and reviews?

## Main datasets
**RateBeer**
**BeerAdvocate**



## Method
### Data preprocessing
**Data slice**
Although the initial rating data was saved in text format, they were too big to parse and analyze. Before the analysis, we used Python bash to slice and prepare the data for CSV loading by pandas.

**Clean Data**
- We first filtered out the beer data, which has less than 120 ratings. If the number of ratings is insufficient, the ratings may be biased. Also, in order to minimize the *Herding Effect* proposed in the paper *'Learning Attitudes and Attributes from Multi-Aspect Reviews'*, we need more data, so we manually set the threshold to 120 after trying several values.
- We also find that nan values in ```overall``` coexists with ```['appearance', 'aroma', 'palate', 'taste', 'overall']```, We also checked the website manually and found that we should rate the appearance, aroma, palate, taste, and overall. So, these data are meaningless if all of these features are nan values. So we also deleted data like this.
- Some reviews' *overall* scores are significant incompatible to the other 4 scores. For example, if the each of the 4 scores is less than 3, while the overall score is greater than 4, then we considered them to be invalid.
- We will also delete the data without review text.

### Analytic methods
**Visualization**
- We first plot some figures about the rating distribution of the two websites, and notice that the distribution are similar, therefore we may do similar analysis on the two datasets.
- We plot the distribution about abv values, and figured out that the most popular ones range from 4 to 10 Vol.
- We plot an **interactive** graph that shows the top 10 most popular beer styles in a specific region in a particular year. We will use these graphs and relevant dataframes to do future analysis. *(These may also help us with the data story and the website we will create then)*
- We plot the change of the number of ratings of one particular beer style *(interactive)* over the years which helps to show whether people's preferences are shifted. We will also conduct hypothesis test on the conclusion.
- We plot the number of reviews as well as the overall score over the time. These help us to know how time affects the overall score.

**Statistical tests** (Finish in MileStone3)
+ To determine whether the time has affected the overall score. We take the Overall score before 2011 and the Overall score after that making an independent t-test. 
+ To search the relation between descriptive reviews and Overall scores. We calculate the number of positive words and negative words for each review. Then compare the difference between them. Making the paired T-test between the difference and overall score to determine whether they have the same distribution.  


<!--
**Detect fake rating** (In Milestone 3)
利用Nlp分词工具将每条评论分解成Embedding，将Embedding作为input，rating作为label，进行逻辑回归训练。最后将review输入到训练好的模型当中。若预测的评分和实际的评分相差较大（相差2分以上）；则判定此为无用的评论。
-->





## Proposed timeline

15.11.22 Slice and preprocess the dataset
18.11.22 Explore the factors associated with the beer ratings.
18.11.22 **Milestone 2** deadline
22.11.22 Pause project work.
02.12.22 **Homework 2** deadline
08.12.22 Begin developing a rough draft of the datastory.
09.12.22 Finish Statistical tests
11.12.22 Complete all code implementations and visualisations relevant to analysis.
14.12.22 Complete datastory.
21.12.22 Complete the website
23.12.22 **Milestone 3** deadline


## Organization within the team
datastory: member 1 & 2
website: member 3 & 4
Code implementation: Work together
Analysis: Group discussion
    

    


