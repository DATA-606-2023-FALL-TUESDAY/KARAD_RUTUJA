# FAKE NEWS DETECTION<br><br>
Prepared for UMBC Data Science Master's Degree Capstone by Dr. Chaojie (Jay) Wang<br>
Author: Rutuja Karad <br>
<a href="https://github.com/RUTUJA8599">Github</a><br>
<a href="https://www.linkedin.com/in/rutuja-karad/">LinkedIn</a><br>
<a href="https://www.youtube.com/channel/UCy_nRgyLsoAWP6w29-_n7zg">YouTube</a><br>
<a href="https://docs.google.com/presentation/d/1OhL_sn4j4BHtAmBepcAW6N8YUbZaW_Hro7BVr1VS-_s/edit?usp=sharing">Presentation</a>
</p> </h1>

<p style="font-size:16px">

</p>


## About the project
The project focuses on detecting fake news, addressing the urgent need for reliable information in today's digital landscape. Fake news can distort public opinion and threaten societal harmony. Thus, the aim is to develop an effective tool for automated fake news detection to enhance information credibility and combat misinformation.

In an age where false information can disrupt societies and even impact national security, our work seeks to empower individuals and organizations to make more informed decisions.

This project aims to answer research inquiries including but not limited to evaluating machine learning and natural language processing algorithms for fake news detection, analyzing metadata and linguistic patterns, and understanding the spread of fake news in society.

## Goal
This project aims to use natural language processing techniques and machine learning algorithms to classify whether a piece of news is fake or real.<br>

## Dataset
Source: <a href="https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset">Link</a><br>
The dataset is a collection of news articles collected in the span of 2015-2017.

Total files: 2  <br>
Size : 116.37 MB <br>

File 1: Fake.csv <br>
Size: 62.79MB <br>
Rows: 23481 <br>
Columns: 4 <br>

File 2: True.csv <br>
Size: 53.58MB <br>
Rows: 21417 <br>
Columns: 4 <br>


## Data Columns

|  #  | NAME     | NON-NULL ENTRIES  | DATA TYPE   | DESCRIPTION
|---|------------------|------------------|---------| --------|
|  1  | title    | 23481  | object  | The title of the article. |
|  2  | text     | 23481   | object  | The content in the article. |
|  3  | subject  | 23481   | object  | Main subject of the article ('News', 'politics', 'Government News', 'left-news', 'US_News', 'Middle-east') |
|  4  | date     | 23481   | object  | Date on which the article was posted. |


## Features
On initial perusal, the input variables will be 'title' and 'text'. Other features can be incorporated later on for enhancements.

The output variable will be a categorical with values '0' for fake news and '1' for news that is true.The category feature has been added to both the datasets manually after importing them as dataframe.

## Preprocessing and Models
Preprocessing will involve removing stopwords, removing punctuation, stemming, lemmatization.

Initially, the plan is to use naive-bayes, logistic regression, linear support vector machine, stochastic gradient descent, and random forest classifiers for classifying the fake news from true news. <br>

## Application Interface
The project will involve a webapp (made using streamlit) that allows the user to enter any news article or news extract. The webapp would then provide an assessment of whether the news is real or fake. <br>

## Web Hosting:
The current plan is to host this webpage on a web hosting service like 000WebHost or AWardSpace. <br>
