# Humor-detection-on-tweets
MLG Apprentice Capstone project - Humor detection 
Swapnil P

Things accomplished:

So far, I have been able to 
•	Scrape and clean the data required for project. Augment it with an additional humor corpus found online.
•	Create a baseline model and evaluate different models for accuracy and recall metrics

A short description of all scripts is provided below.

00_Scrape_Following.ipynb
This script will scrape the twitter users that my favorite funny twitter acct(@AbbieEvansXO) herself follows. This is my hack to get a mostly correct list of funny accounts. (Otherwise, I'd have had to individually find them & then create a list of accounts to scrape - may be later)

01_Scrape_Tweets_From_Funny_Accounts.ipynb
This script will scrape tweets from the 'following' list of twitter accounts that was output of 00_Scrape_Following.ipynb. A csv is created for tweets from every account and saved as username_date.csv

02_Append_All_Tweets_Together.ipynb
This simple script will append all the individual csv files created by 01_Scrape_Tweets_From_Funny_Accounts.ipynb. Those will be cleaned (using preprocessor library). Also, we filter out tweets that have RT (retweet) count < 50 (assumption here is that RT>=50 is mostly going to be a funny tweet). Final O/P saved in Tweets_Combined.csv

03_Read_All_Data.ipynb
This script reads the following inputs.
I.	Our processed tweets i.e.  (O/P of 02_Append_All_Tweets_together.ipynb)
II.	Readily available humor corpus(positive as well as negative class) - One-liners, Proverbs, Wikipedia sentences, Reuters news headlines. Found at https://github.com/CrowdTruth/Short-Text-Corpus-For-Humor-Detection
It creates a final dataframe with (sentence, class) columns that we will use later for modelling.

04_Baseline_Models_With_Word2Vec_Dimensions.ipynb
This script will create Word2Vec dimensions for every row in our dataset and then run a few baseline models.   
I.	First, we create word vectors for every row, then just average those word vectors to create sentence vectors.
II.	Apply baseline models using following scoring metric and plot them for comparison
   -accuracy
   -recall (positive class i.e. jokes important not to miss)

