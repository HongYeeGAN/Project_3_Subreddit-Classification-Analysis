# Project 3 - Subreddit Classification Analysis


## Problem Statement

The goal of the project is to use predictive models to predict which subreddit does a post came from and to identify words that can help to differentiate 2 chosen subreddits.
 
Questions that we need to answer:
- Which words will most differentiate our two chosen subreddits?
- How can we use predictive modeling to best predict which subreddit a post came from?

To answer these questions, we have to build an appropriate natural language processing(NLP) or logistic regression model, which classifies a post with missing labels using top predictive words trained on it.

Success of the model will be evaluated based on classification accuracy. Best model will have the least difference in classification accuracy between the training and test dataset. This is to ensure no overfitting and model can still perform upon applying to unseen data. The model is then further interpreted using confusion matrix parameters.

Our stakeholders are data scientists in Reddit whereby they experience a server technical problem and the labels of posts were lost. This server issue can cause users to lose track of their posts or posts being end up at the wrong subreddit. This might sound like a trivial mistake but users can lose confidence in Reddit. Advertising revenue can be lost because the advertisments ended up at the wrong subreddits. Data Scientists in Reddit can make use of my Production model to classify post back to their respective subreddit within a short time frame, automatically without reviewing the content manually by human. This model evaluation is not only a method to address this missing post label issue, its techniques also have application beyond the scope of this project. Example, an email service wants to detect spam emails.

The subreddits selected were [r/PS5](urlhttps://www.reddit.com/r/PS5/) and [r/XboxSeriesX](urlhttps://www.reddit.com/r/XboxSeriesX). Both are home video gaming consoles, going to be luanched this November at the same price. The 2 subreddits are similar in many ways and often being compared against. Their key differences will be manufacturer - Playstation is by Sony and Xbox is developed by Microsoft.


# Executive Summary

The project evaluates the number of times each word appears in the 2 chosen subreddits. The top frequently appearing words identified during initial exploratory data analysis showed that product names, manufacturer names are the best words to differentiate them. These findings helped us built an appropriate predictive model (Logistic Regression with CountVectorizer) which is able to classify a post without label back to its respective subreddit. We evaluate the success by choosing a model with lowest difference in classification accuracy, between the test and training dataset. By interpreting the confusion metric, we can tell how each word predicts the subreddit classification.

Paired with the knowledge of how these words associate with the subreddits, Data Scientists in Reddit can now make use of the model, to trace posts with missing post labels back to their respective subreddit. This production model can serves as a contingency plan during a server system glitch, which can in turn prevent the loss of users and advertising customers. It is therefore a good solution for Reddit's Data Scientists.

Areas for Reddit Data Scientists' expansion and future exploration:
- moving forward, the model can be continuously improved by introducing more new data to it. Model accuracy and other metrics can be improved if more words were introduced. Hence better predictions for Reddit Data Scientists and their users/advertising customers.
- data from other subreddits can also be added to expand the model to not limited just to r/PS5 and r/XboxSeriesX use. The model can be applied to all the subreddits, eventually making classification predictions for the entire Reddit's posts in the future.
- consistant update of words into the model is needed as old generation games like 'ps3' will be slowly phase out and became irrelevant in this project. 


# Data Dictionary

| Feature 	| Type 	| Dataset 	| Description 	|
|-	|-	|-	|-	|
| title 	| object 	| df_xboxseriesx / df_ps5 	| title of each   reddit post 	|
| selftext 	| object 	| df_xboxseriesx / df_ps5 	| body text of   each reddit post 	|
| combined_text 	| object 	| df_xboxseriesx / df_ps6/ps5_xboxseriesx_sentiment/ps5_xboxseriesx 	| title + selftext 	|
| score 	| int64 	| df_xboxseriesx / df_ps7/ps5_xboxseriesx_sentiment 	| number of   upvotes a post has 	|
| upvote_ratio 	| float64 	| df_xboxseriesx / df_ps8/ps5_xboxseriesx_sentiment 	| number of   upvotes a post has, divided by the total number of votes the post received 	|
| num_comments 	| int64 	| df_xboxseriesx / df_ps9/ps5_xboxseriesx_sentiment 	| number of comments a post has 	|
| is_xbox 	| int64 	| ps5_xboxseriesx 	| binary variable:  1 for   xbox, 0 for PS5 	|
| date_created 	| datetime 	| df_xboxseriesx / df_ps5 	| date and time   the post is created 	|


# Conclusions and Recommendations

## Conclusion

**From the results from this technical report, our stakeholders are now able to:**

- Use predictive modeling to best predict which subreddit a post came from.
    - This is done by comparing the performance of all models.
    - The best model is Logistic Regression model with CounterVectorizer because the train and test score is closest to each other, with only 2% difference. 
    - We can predict with an accuracy of 88.7% where a given post came from.
    - From exploratory data analysis and the study of our coefficients generated by our model, we have found out the important predictive words for r/XboxSeriesX subreddit are 'xbox', 'series', 'microsoft', 'order', 'pre' and 'ps5', 'sony', 'ps4', 'playstation', 'soul' for r/PS5. These words were most able in differentiating our two chosen subreddits.
    - Paired with the knowledge of how these words associate with the subreddits, Data Scientiests in Reddit can make use of the model to trace posts with missing post labels back to their respective subreddit.
    - This production model can serves as a contingency plan during a server system glitch, which can in turn prevent the loss of users and advertising customers. It is therefore a good solution for Reddit's Data Scientists.

Technique of model can apply to other scope example, identify spam emails, automate CRM tasks based on topic matching, recommending similar articles to readers.

## Recommendation

Areas for Reddit Data Scientists' expansion and future exploration:
- moving forward, the model can be continuously improved by introducing more new data to it. Model accuracy and other metrics can be improved if more words were introduced. Hence better predictions for Reddit Data Scientist and their users/advertising customers.
- data from other subreddits can also be added to expand the model to not limited just to r/PS5 and r/XboxSeriesX use. The model can be applied to all the subreddits, eventually making classification predictions for the entire Reddit's posts in the future.

Other recommendations for Reddit Data Scientist to improve model for better accuracy and predictions for their users and advertising customers:
- try to explore other models eg Random Forest, Gradient Descent and SVM
- remove more overlapping words such as 'luanch' and 'console'
- explore comment texts
- Use ensemble modeling methods like sklearn’s VotingClassifier to improve accuracy
- Further explore if there is other ways to detect sentiment of the posts as that could bring revenue for advertisments.
- Spend more time on existing features webscraped eg study relationship of number of comments, length of words, scores, upvote_ratio on classification accuracy of a post

Areas for web developers for improvement:
- Combined two similar subreddits into 1 to reduce complexity and less classification errors. 
