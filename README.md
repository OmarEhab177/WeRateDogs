# WeRateDogs
Project about data wrangling and analyzing tweet archive of Twitter user @dog_rates, also known as WeRateDogs.

The dataset that was wrangled (and analyzed and visualized) is the tweet archive of the Twitter account @dog_rates,
also Known as WeRateDogs. This twitter account rates pepole's dogs with a humorous comment about the dog. 
These ratings almost always have a denominator of 10. the numerators, thought? 
Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." 
WeRateDogs has over 4 millino followers and has received international media coverage.

## The wrangling process is divided into three steps 
------------------------------------
- Data wrangling, which consists of
  - Gathering data
  - Assessing data
  - Cleaning data

we gathered each of the three pieces of data as described below in a Jupyter Notebook titled wrangle_act.ipynb.
**The WeRateDogs Twitter archive by downloading it from source tab**

**The tweet image predictions, we downloaded it programmatically by using the Requests library and 
the following URL:** https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv




**Each tweet's retweet count and favorite ("like") count and more interesting data Using the tweet IDs in the WeRateDogs Twitter archive,
query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file.
Each tweet's JSON data should be written to its own line. Then read this .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count.**



------------------------
##Assessing Data for this Project
After gathering each of the above pieces of data, assess them visually and programmatically for quality and tidiness issues.

I found this following issues
- Tidiness Issues
  - Dog stage data is seperated into 4 columns instead of one.
  - All data is related but divided into 3 seperate dataframe.
- Quality Issues
  - archieve_df
    - tweet_id is int64 --> convert to string
    - timestamp is string --> convert to datetime
    - 181 retweets --> must be removed
    - some dog name are None --> replace them to Nan
    - 440 numerator less than 10
    - raw 313 has 0 denominator id= 835246439529840640
    - 23 rating denominator not equal 10
  - image_predictions_df
    - missing photos for some ids
    - underscores are used in malti_word names in p1, p2,& p3 instead of spaces
    - some P names starts with upper case letter and other starts with lower case
  - api_df
    - missing entries (2331 instead of 2356)

##  Cleaning Data
The previous issues were cleaned as appropriate resulting in a high quality and tidy master pandas DataFrame

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

