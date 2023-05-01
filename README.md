# Project Report | YOUTUBE VIDEOS: SENTIMENT ANALYSIS AND TREND PREDICTION

## SP23-IN-INFO-H516: Cloud Computing For Data Science
### May 2nd, 2023

### Group 7 Members: Alka Kumari, Shivani Raut, and Tina Joseph


### Table Of Content

- Table of Contents
- Introduction
- Project Brief
- Data Description
- Methodology
- Exploratory Data Analysis-Emojis
- Exploratory Data Analysis-Comments
- Sentiment with Trend
- Model Evaluations and Results - Sentiment Prediction
- Model Evaluation and Trend Prediction
- Future Scope
- References
- Appendix

## INTRODUCTION
With more than 2 billion active users each month, YouTube has become a significant player in the online video content market recently. It has become an essential platform for businesses, individuals, and organizations to sell their products, services, and ideas as a result. The platform receives millions of video submissions every day, making it a hub for information, education, and entertainment.
It is a platform where YouTubers and YouTube Channels upload content in the form of videos and can also receive feedback in the form of likes, comments, and several shares, from the audience. The YouTube audience watch these videos as per their likings and share their feedback in the form of views, likes, dislikes, comment, and sharing content with other audiences. 
## PROJECT BRIEF
In this project, we are trying to examine the relationships and importance of interactive features on YouTube like views, likes, dislikes, and comment counts that affect the trendiness of a video. 
What we did:
- Performed Sentiment Analysis on the Comments received on the Youtube     videos and comments dataset.
- Prediction of Trending period of Youtube videos using Random Forest 
- Prediction of sentiments using Logistic Regression
- Emoji Analysis from Youtube video Comments
## DATA DESCRIPTION
We used Kaggle.com to obtain the data for our analysis. Data from daily popular YouTube videos for the countries of the United States, Great Britain, Germany, Canada, France, Russia, Mexico, South Korea, Japan, and India are included in the collection, which spans several months. Each location has a different video file that we've used. The following features are included in the file data:
List of Files:
- Sentiment Analysis for Comments: https://www.kaggle.com/datasets/datasnaek/youtube
: GBcomments.csv, GBVideos.csv, UScomments.csv, USVideos.csv
- Trending Youtube Videos: https://www.kaggle.com/datasets/datasnaek/youtube-new
: 10 countries data files : CAvideos.csv, DEvideos.csv, FRvideos.csv, GBvideos.csv, INvideos.csv, JPvideos.csv, KRvideos.csv, MXvideos.csv, RUvideos.csv, USvideos.csv
## METHODOLOGY
## Data Understanding
For this project, we worked on multiple files in order to identify trends among various YouTube videos. We counted 420029 records in total after reading the files. Special characters have been found in variables like the title, channel title, tags, and description. The existence of duplicate observations was an additional issue that came out during data processing. We found many rows with the same video_id since videos may trend for several days. We chose to only take into account the most recent instance of a trending video clip while evaluating the dataset in order to eliminate duplicate observations.
## Data Preparation:
1. Data Cleaning - Removed obtrusive data such as null values and special characters from both files and discarded duplicate observations. Added more columns to the file that were required to do the evaluations to predict the sentiment analysis and prediction of trending videos.
![img for data cleaning of comments](https://myoctocat.com/assets/images/base-octocat.svg)
For emojis and comments sentiment analysis, we separated emojis from the comments file.
![img for data cleaning of comments for emojies](https://myoctocat.com/assets/images/base-octocat.svg)
We included columns like diff_days for the video file to determine the number of days a video is trending for.

2. Data Preprocessing - For emojis and comments, we performed sentiment analysis to see how the sentiments affect the trendiness of a video. We also performed an Emoji analysis to see how separate emoji counts can affect the videos.
![img for data processing for sentiments](https://myoctocat.com/assets/images/base-octocat.svg)

We chose elements such as the title, channel title, tags, and description for the video file to examine the variables that affect YouTube video popularity. We chose these factors to learn more about the terms and subjects most frequently related to popular YouTube videos.
![img for data processing for trend](https://myoctocat.com/assets/images/base-octocat.svg)
## EXPLORATORY DATA ANALYSIS: Emojis
![img for EDA emojis](https://myoctocat.com/assets/images/base-octocat.svg)
From the emoji analysis we can say that for top commented videos the emoji count is still not that high as expected. The viewers are not making use of emojis in a significantly large amount. However, the emoji analysis can be used in the future to compare the sentiments predicted from the text comment analysis.
## EXPLORATORY DATA ANALYSIS: Comments
![img for EDA comments](https://myoctocat.com/assets/images/base-octocat.svg)
The box plot of Sentiment distribution over all the data analysis shows that many trending videos have neutral-to-positive sentiments(0.10 - 0.20). The likes_per_view ratio is not that high for many videos.
## EXPLORATORY DATA ANALYSIS: Sentiment with Trend
![img for EDA sentiment with trend](https://myoctocat.com/assets/images/base-octocat.svg)
To see if the you-tube comment's sentiments affect the trend or not, we plotted sentiments vs views and likes. From the heatmap and regression plots, we can say that sentiments do not correlate with the trend. But we observed a high correlation between views, likes, dislikes, and comment count. 
So finally, we decided to use, tokenized and then count-vectorized comments(features) for sentiment prediction. And we decided to use vectorized features: views, likes, dislikes, and comment count for predicting the trend.
## RESULTS AND DISCUSSION: 
- The dataset features and labels were imbalanced before. So, we balanced the dataset after considering neutral comments as negative comments, increasing weights to that class in the tree. We got 99% accuracy after balancing the data which was 86% before
- For the trend prediction model we used two labels: Tier and Trend. Both columns were calculated from date columns. The tier column gives the number of days the video took to get on the trending list while the Trend column gives the number of days the video was on the trending list. This means we are predicting both: the number of trends and the number of days that will trend for a video.
- Again we had to balance the trend data and the accuracy improved significantly after that. Final accuracy is 86.76% for predicting the number of days the video will take to trend and 97.3% accuracy for the number of days the video will trend. The overall results of the evaluation are given below.
### SENTIMENT PREDICTION
![img for sentiment prediction results](https://myoctocat.com/assets/images/base-octocat.svg)
One observation was noted after looking at the probabilities that as the number of views on video are increasing, the probability of the prediction is increasing and gets stabilized around 0.5. This can help to state that the views are contributing more than likes for the trend of the video on you-tube. So, the you-tubers can focus on increasing views more.
### TREND PREDICTION
![img for trend prediction results](https://myoctocat.com/assets/images/base-octocat.svg)

## POSSIBLE CLOUD MIGRATION OF THE PROJECT
![img for cloud project](https://myoctocat.com/assets/images/base-octocat.svg)

## FUTURE SCOPE
- Sentiment Analysis using BERT:  BERT (Bidirectional Encoder Representations for Transformers) is a “new method of pre-training language representations” developed by Google and released in late 2018.
- A website can be made where you-tuber can monitor the statistics through Dashboards of their videos. The Dashboards will show the predictions of the Trends and Sentiments of the videos.
- Sponsors or the Advertisers of the you-tube channel can take the decisions to sponsor/advertise on specific you-tube channels based on the predictions.


## REFERENCES
1. 	Sentimental Analysis using Logistic Regression: https://www.ijera.com/papers/vol11no7/Ser-2/F1107023640.pdf
2. 	YouTube Videos Prediction: Will this video be popular?: https://cs229.stanford.edu/proj2019aut/data/assignment_308832_raw/26647615.pdf
3. 	LSTM, VADER and TF-IDF based Hybrid Sentiment Analysis Model: https://thesai.org/Downloads/Volume12No7/Paper_30-LSTM_VADER_and_TF_IDF_based_Hybrid_Sentiment.pdf
4. 	On the Reusability of Sentiment Analysis Datasets in Applications with Dissimilar Contexts: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7256387/
5. 	A Comparative Study on TF-IDF Feature Weighting Method and its Analysis using Unstructured Dataset: https://ceur-ws.org/Vol-2870/paper10.pdf
6. 	Real-time Twitter Sentiment Analysis for Moroccan Universities using Machine Learning and Big Data Technologies: https://online-journals.org/index.php/i-jet/article/view/35959
7. 	Social media analytics for YouTube comments: potential and limitations: https://www.tandfonline.com/doi/abs/10.1080/13645579.2017.1381821?journalCode=tsrm20
8. 	How useful are your comments? Analyzing and predicting YouTube comments and comment ratings: https://www.researchgate.net/publication/221023733_How_useful_are_your_comments_Analyzing_and_predicting_YouTube_comments_and_comment_ratings
9. 	Visualizing YouTube’s comment space: online hostility as a networked phenomenon: https://journals.sagepub.com/doi/pdf/10.1177/1461444818792393
Appendix 1: Contributions from each member
There was no clear-cut division of work in this team. Everybody worked on every part of the project to get good learning out of the project. However, by contribution:

## APPENDIX
Shivani Raut contributed more to Data analysis, Emoji Analysis, Comments analysis, and report review, Trend Prediction.
Alka Kumari contributed to the Sentiment Analysis and prediction, project presentation, and project report. 
Tina Joseph contributed to Data exploration, Data cleaning, and report reviewing Trend Prediction.

