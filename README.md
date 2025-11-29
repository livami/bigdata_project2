# YouTube Sentiment Analysis - Project for the Big, Semi- and Unstructured Date Module (FHNW) 

This project and the respective Python code performs a sentiment analysis on Ken's YouTube comments, generates word clouds for positive and negative comments, analyzes trends and identifies active users. It uses **Pandas, NLTK VADER, WordClous and Matpltlib** to process and visualize data. 

## Requirements 

All required libraries are installed using the following commands:
- pip install pandas
- pip install vaderSentiment
- pip install ntlk
- pip install wordcloud

## Input File 

The project uses the CSV file:
- kens_comments.csv

The example dataset used was donwloaded and copied on this Github repository for the project's purpose. Link: https://github.com/hellotinah/youtube_sentiment_analysis/blob/main/kens_comments.csv.

## Data Cleaning and Exploration 

The script:
- loads the CSV file
- checks for missing and duplicate values
- displays the data types and sample rows
- counts the comments per video
- filters out the videos with fewer than **50 comments**

This then creates a "cleaned" dataset called data2.

# Sentiment Analysis 

This project applies **VADER sentiment scoring** to each comment:
- neg = negative
- neu = neutral
- pos = positive
- compound

Two thresholds are used in the code: 
- General filtering: compound >= 0.05 = positive
- Second pass (stricter categorization):
-   Positive: compound >= 0.55
-   Negative: compound <= - 0.001
-   Neutral: everything in between 

The results are then stored in a new dataset called "data3". 

## Positive Comment Export 

The function filter_positive_from_csv() saves all positive comments to: kens_positive_comments.csv

The analyzed dataset sorted by sentiment score is saved to: data3_sorted.csv

## Video Sentiment Metrics 

The script calculates: 
- the number of positive, negative and neutral comments per video
- the percentages per video
- the overall sentiment score (positive_% - negative_%) per video

It then identifies:
- the video with the highest % positive = **best video**
- the video with the highest % negative = **worst video**

## Word Clouds 

The code generates two word clouds. One with the **positive comments from the best video** and one for the **negative comments from the worst video**. 
This is where the functions **wordcloud and matplotlib** are used.

## Sentiment Trend Over Time 

If a date column exists in the CSV, the script:
- detects it automaticall
- assigns each video a timestamp
- computes sentiment score per video
- plots a chronoligical trend line of the video sentiment

## Most Active YouTube Channel Subscriber 

User the column "author_name", the script finds:
- the user with the highest total comments
- the number of the comments per video from that user

# How to Run the Script / Code 

1. Place "kens_comments.csv" in the same directory
2. If you are using Jupyter, run the notebook. Or else use any other program that runs the Python script
3. Outputs produced:
-   kens_positive_comments.csv
-   data3_sorted.csv
-   Sentiment tables and metrics
-   Trend plots
-   Word clouds

# Disclaimer 

This project is merely for educational and research purposes. 
