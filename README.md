Problem Statement: What Factors Influence a Model's Ability to Make Accurate Predictions? 

To build a model that would accurately predict whether text belonged to one subreddit over another, I had to first obtain data from two subreddits of my choosing. 
I was able to scrape reddit using Pushshift’s API and create a for-loop to gather 3000 submissions for cleaning and modeling. 

Once I was able to gather 3000 submissions, I created a dataframe to use for cleaning and Exploratory Data Analysis (EDA). The subreddit, title, and selftext columns were the most important to my problem statement and analysis, so I condensed my dataframe to only those columns. After removing duplicates, submissions marked as ‘removed’ or ‘deleted,’ and null values, I was left with 1308 relationship advice submissions and 1103 jokes submissions. This would give me a baseline accuracy of 0.54 (relationship advice). 

Through EDA, I learned that the average word count of a relationship advice self text submission subreddit is more than 8 times that of a Jokes submission. 

I also used NLP’s such as stemming, tokenization, lemmatization and countvectorizer to process the text and make them machine learning friendly. Through this, I was able to find the most frequently used words and the least used words in my dataset. This is especially helpful when setting hyperparameters in my models. 

After splitting my data into train and test sets, I used Logistic Regression and Random Forest to make accurate predictions. I used GridSearchCV as my tuning technique, with pipelines to assemble several steps that can be cross-validated together while setting different parameters. My models prefer different parameters, however, they both produce high scores. 

The resulting confusing matrixes illustrated where the models were predicting inaccurately, and I was able to find the exact submissions being misclassified. Both models were better at predicting Jokes submissions rather than relationship advice submissions. 

I believe that profanity or words like "sex," "jokes," "toilet," "poop," and "fart," probably come up very often when telling jokes and speaking about relationships. 
ie; 1768: “Men how like to make sexual jokes, always looking at women their buts or boops and have perverted idea's. Do you find them attractive?” (This is an example of a relationship advice submission misclassified as jokes.)

Moreover, word count and length of posts are very telling of which subreddit a post belongs to. The word count for posts on the Jokes subreddit, on average, are 8 times shorter than those of relationship advice posts. Many of the misclassified relationship advice submissions were also shorter in length, much close to the average word count of a  joke submission. 

Overall, the models did well at predicting one subreddit over the other.  
