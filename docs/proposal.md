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


## Background
The project focuses on detecting fake news, addressing the urgent need for reliable information in today's digital landscape. Fake news can distort public opinion and threaten societal harmony. Thus, the aim is to develop an effective tool for automated fake news detection to enhance information credibility and combat misinformation.

In an age where false information can disrupt societies and even impact national security, our work seeks to empower individuals and organizations to make more informed decisions.

This project aims to answer research inquiries including but not limited to evaluating machine learning and natural language processing algorithms for fake news detection, analyzing metadata and linguistic patterns, and understanding the spread of fake news in society.

## Goal
This project aims to use natural language processing techniques and machine learning algorithms to classify whether a piece of news is fake or real.<br>

## Data
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

## 4. Exploratory Data Analysis (EDA)

- Perform data exploration using Jupyter Notebook
- You would focus on the target variable and the selected features and drop all other columns.
- produce summary statistics of key variables
- Create visualizations (I recommend using **Plotly Express**)
- Find out if the data require cleansing:
  - Missing values?
  - Duplicate rows? 
- Find out if the data require splitting, merging, pivoting, melting, etc.
- Find out if you need to bring in other data sources to augment your data.
  - For example, population, socioeconomic data from Census may be helpful.
- For textual data, you will pre-process (normalize, remove stopwords, tokenize) them before you can analyze them in predictive analysis/machine learning.
- Make sure the resulting dataset need to be "tidy":
  - each row represent one observation (ideally one unique entity/subject).
  - each columm represents one unique property of that entity. 

## 5. Model Training 

- What models you will be using for predictive analytics?
- How will you train the models?
  - Train vs test split (80/20, 70/30, etc.)
  - Python packages to be used (scikit-learn, NLTK, spaCy, etc.)
  - The development environments (your laptop, Google CoLab, GitHub CodeSpaces, etc.)
- How will you measure and compare the performance of the models?

## 6. Application of the Trained Models

Develop a web app for people to interact with your trained models. Potential tools for web app development:

- **Streamlit** (recommended for its simplicity and ease to learn)
- Dash
- Flask

## 7. Conclusion

- Summarize your work and its potetial application
- Point out the limitations of your work
- Lessons learned 
- Talk about future research direction

## 8. References 

List articles, blogs, and websites that you have referenced or used in your project.
