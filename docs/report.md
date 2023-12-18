# DATA606 - Capstone Project

## Title and Author
- **Title** : Fake News Detection
- **Author** : Rutuja Karad
- **Semester** : Fall 2023
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
  
  <a href="https://github.com/RUTUJA8599">Github</a><br>
  <a href="https://www.linkedin.com/in/rutuja-karad/">LinkedIn</a><br>
  <a href="https://www.youtube.com/watch?v=naDmZWVk2JY&ab_channel=RutujaKarad">YouTube</a><br>
  <a href="https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/blob/main/docs/FINAL_CAPSTONE_PPT.pdf">Presentation</a>

## 1. Background:

The project focuses on detecting fake news, addressing the urgent need for reliable information in today's digital landscape. Fake news can distort public opinion and threaten societal harmony. Thus, the aim is to develop an effective tool for automated fake news detection to enhance information credibility and combat misinformation.

In an age where false information can disrupt societies and even impact national security, our work seeks to empower individuals and organizations to make more informed decisions.

This project aims to answer research inquiries including but not limited to evaluating machine learning and natural language processing algorithms for fake news detection, analyzing metadata and linguistic patterns, and understanding the spread of fake news in society.

## 2. Goal:

This project aims to use natural language processing techniques and machine learning algorithms to classify whether a piece of news is fake or real.<br>

## 3. Data:

Source: <a href="https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset">Link</a><br>
The dataset is a collection of news articles collected in the span of 2015-2017.

Total files: 2 <br>
Size : 116.37 MB <br>

File 1: Fake.csv <br>
Size: 62.79MB <br>
Rows: 23481 <br>
Columns: 4 <br>

File 2: True.csv <br>
Size: 53.58MB <br>
Rows: 21417 <br>
Columns: 4 <br>

## 4. Data Columns

|     | NAME    | NON-NULL ENTRIES | DATA TYPE | DESCRIPTION                                                                                                |
| --- | ------- | ---------------- | --------- | ---------------------------------------------------------------------------------------------------------- |
| 1   | title   | 23481            | object    | The title of the article.                                                                                  |
| 2   | text    | 23481            | object    | The content in the article.                                                                                |
| 3   | subject | 23481            | object    | Main subject of the article ('News', 'politics', 'Government News', 'left-news', 'US_News', 'Middle-east') |
| 4   | date    | 23481            | object    | Date on which the article was posted.                                                                      |

## 5. Features:

The input variables will be 'title' and 'text'. The output variable will be a categorical with values '0' for fake news and '1' for news that is true.The category feature has been added to both the datasets manually after importing them as dataframe.

## 6. Preprocessing and Data Inspection - Part I

1. **Checking for Null Values:**
   ![nullvalues](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/37034af6-1623-4107-bdcb-cd776f07accc)

   The dataset (combined) does not contain any null values.

3. **Dataset Information:**

- Fake.csv <br>
  ![fakeinfo](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/bc0229b8-62ff-46b7-8c46-1a31c2aa3132)
<br><br>
- Real.csv: <br>
![realinfo](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/ee79b30f-8a68-4ede-9ad0-d2077f9b3449)

  

3. **Concatenation of Datasets:** <br>
   The dataset is divided into two CSV files - `Fake.csv` and `Real.csv`. It is necessary to combine them and add a target variable - 0 for Fake News and 1 for True/Real News.

![combined](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/8197d8ff-e587-4345-a782-2fdab10785bf)


4. **Text Cleaning:**
   - **Removed Noise**: Stripping text of formatting (e.g., HTML tags, special characters, emojis).
   - **Lowercasing**: Converted the text to lowercase to maintain consistency since "Hello" and "hello" should be the same word for analysis.
   - **Removed Punctuation**: Punctuation was discarded.
   - **Removed Stop Words**: Common words like "is", "and", "the", etc., which do not contribute much meaning to the sentences were removed.
   - **Removed Numbers**: Numbers were removed or converted into textual representations.

## 7. Exploratory Data Analysis (EDA)

1. **Distribution of Fake and Real News:**

   ![piechart](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/79c13272-2b17-498c-b228-d832bcd93701)


- From the distribution of the total articles, 44.7% is real news and 55.3% is fake news. The distribution is pretty much equal.
- This will be advantageous in training as there is less chance of overfitting and high chances of good generalization.
  <br>
  <br>

2. **Timeline Visualization - Fake and Real News Articles Over Time:**

![timeline](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/4740798e-dc2b-4b00-9a2c-e71ed63f4820)

- The above graph describes the relation between the number of articles and the date when they were released.
- In general, there are a lot of fake articles compared to true articles, but we can observe a sharp spike during the 2016 election period.
- There seems to be a spike of true news articles during late 2017 which can be attributed to either being outliers or the data collection process.
  <br>
  <br>

3. **Analyzing the Distribution of Article Lengths by Category:**
   ![distbylengths](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/bc3b5724-6a3a-4bfd-9f4c-4d3dd1b2d334)
   - An important trend can be identified in this graph: fake news articles are much more verbose.
   - A study by Hanock and Dunham found that in written statements, if a person is lying or is not sure what they are saying is true, they often embellish the details of their conversation [1].
   - From the above graphs, we can see that the fake texts contain more characters and more words per article thus reinforcing the hypothesis laid down by the previous visualization.

4. **Word and Character Lengths in Articles by Category:**

|          Words          |          Characters           |
| :---------------------: | :---------------------------: |
| ![wordcomparison](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/2e741d33-406e-4569-b9d7-605ac571f065) | ![characterscomparison](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/16e09369-afe1-4ed6-9ba8-63d60ae00eea) |

- From the above visualization, we can conclude that articles categorized as true have a higher average word length than articles categorized as fake.
- Generally, when a person is falsifying statements, they will make use of articles, prepositions abundantly [1].
- A person telling the truth will be much more articulate and concise in their use of words [1].
- Thus, the above inference that true news articles having less average word length holds true.
  <br>
  <br>

Thus, from the above graphs, we can see that the fake texts contain more characters and more words per article thus reinforcing the hypothesis laid down by the previous visualization.
<br>
<br>

6. **Word Cloud:**<br><br>
   
   ![wordcloud](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/6087bf2b-853f-4b53-b966-38504d5a1dc7)

   - From the word cloud, we can observe that the most commonly used words in fake news articles seem to be "said", "Donald Trump", "American", "think", "that", "Hillary Clinton", "will", "say", "might", "want", "country", "left".
   - Most of the above words can be used to represent suggestion and supposition in speech.
  
7. **Bi-Gram Analysis:**
   
   - Donald Trump is a common topic in both fake and true news titles, but the context or surrounding words differ.
   - White House is a prevalent bi-gram in both categories, indicating that many articles (whether fake or true) focus on events or happenings related to the White House.
   - Some terms like Fox News, Hillary Clinton, and Bernie Sanders are more frequent in fake news titles.
   - In true news titles, there's a broader range of topics covered, such as North Korea, Islamic State, Supreme Court, and Puerto Rico.

8. **Tri-Gram Analysis:**

   - "pic twitter com": This tri-gram frequently occurs in the fake news dataset. It suggests that many fake news articles might include Twitter image links.
   - "21st century wire" and "news 21st century": These phrases suggest that there might be recurring sources or mentions in the fake news dataset.
   - "black lives matter": This topic seems to be prevalent in the fake news dataset.
   - Common Phrases: Phrases like "president donald trump" and "president barack obama" are common in both datasets. However, their contexts might differ.
   - In the true news dataset, there are mentions of specific sources like "reuters president donald" and "new york reuters", which might indicate the origin or reference of the news

## 8. Preprocessing - Part II (NLP):

The following preprocessing steps required in NLP were performed.

1. **Tokenization:**

   - **Sentence Tokenization**: The text was split into individual sentences.
   - **Word Tokenization**: The text was split into individual words or tokens.

2. **Part-of-Speech Tagging:**

   - Assigned part-of-speech tags to each token to understand sentence grammar.

3. **Stemming and Lemmatization:**

   - **Stemming**: Reduced words to their base form (e.g., "running" to "run").
   - **Lemmatization**: Contextually linked words with similar meanings to one word (e.g., "better" to "good").

4. **Word2Vec Embeddings:**
   - Word2Vec is an approach to word embeddings that involves mapping words into a dense vector space where semantic meanings of words are captured based on their context in the corpus.
   - Convert a sentence to its average word vector representation using a Word2Vec model.

## 9. Model Training:

#### 9 a. Model Training Setup:
- As it is a classification task the models selected are classifier model: Random Forest, Stochastic Gradien Descent, Linear SVM, and Logistic Regression.
- Google Colab was used as development environment for the ease of package imports.
- 20% of the dataset was used for testing and 10% was used for validation with a fixed random state to generate the same split in case environment stops or fails.
- In assessing model performance, the F1 score, which balances precision and recall, proved to be a more reliable metric than accuracy, particularly in scenarios with class imbalances and where both false positives and false negatives carry significant implications. 

Packages used:
|    # | PACKAGES    | 
|    1 | Numpy       | 
|    2 | Pandas  | 
|    3 | Seaborn    | 
|    4 | Plotly    | 
|    5 | Matplotlib    | 
|    6 | Scikit Learn    | 
|    7 | NLTK    | 
|    8 | Gensim    | 
|    9 | Joblib    | 
|    10 | Streamlit    | 

#### 9 b. Feature Extraction:

Feature extraction was done from the text using CountVectorizer and TfidfVectorizer. The TF-IDF Vectorizer was used for POS Tags. Word2Vec features were used as is because they were in a matrix format.
<br><br>
The classifiers selected are: Random Forest, Stochastic Gradien Descent, Linear SVM, and Logistic Regression. There were two approaches - POS Tagging and Word2Vec embeddings. All the classifiers were first trained after performing POS Tagging on the preprocessed data and then after performing Word2Vec Embeddings on the preprocessed data.

#### 9 c. Comparison of Model Training:

- Word2Vec embeddings consistently outperform POS tags across all classifiers. This indicates the rich semantic information captured by Word2Vec, which is crucial for this fake news classification task.

- Logistic Regression, Linear SVM, and Stochastic Gradient Descent have similar performance when trained on Word2Vec embeddings. Random Forest, although slightly more computationally intensive, offers robustness and also performs exceptionally well with Word2Vec.

  ![model](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/17b7766e-c20c-42cd-a245-477cee1896aa)


- Given the high F1 scores and computational efficiency, Logistic Regression with Word2Vec embeddings stands out as a top candidate. Random Forest with Word2Vec is also a strong contender, offering robustness and adaptability to potential changes in the type of data.

Logistic Regression was chosen as the final classifier.

#### 9 d. Hyperparameter Optimization:

Different values of "C" were tested with L2 Penalty. Best values obtained - 10, 100. The best model was saved for later use.

![gridsearch](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/79f799b5-8717-42f2-90cf-0ce9793cc74b)

## 10. Application of the Trained Model
Streamlit was used to create a web app.Streamlit, a library that facilitates the integration of HTML and Python, was utilized for web app development. This choice streamlined the process of creating a user-friendly interface. The application features a text input field and a submit button, allowing users to input text for analysis. Upon submission, the model processes the input and displays the probability of the text being real or fake. This functionality not only makes the model accessible to users but also provides immediate, interactive feedback on the likelihood of news authenticity, showcasing the practical application of  machine learning model in a real-world setting. 

**Real News:**

![REALNEWS](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/e0318476-f2be-4a4b-a8d0-ada8e111b1e1)

**Fake News:**

![Fakenews](https://github.com/DATA-606-2023-FALL-TUESDAY/KARAD_RUTUJA/assets/144069633/ce996f55-f77e-4c3d-bd20-c92a566e4953)

## 11. Conclusion

#### 11 a. Summary of Work:

The project focused on developing a system to detect fake news, a critical issue in the digital age. The approach involved training various classifier models, namely Random Forest, Stochastic Gradient Descent, Linear SVM, and Logistic Regression. These models were trained on a dataset with careful consideration of the data split and environment stability, using Google Colab.
A key finding was the superior performance of Word2Vec embeddings over POS tags across all classifiers, emphasizing the importance of rich semantic information for the task. Logistic Regression and Random Forest models, in particular, demonstrated high F1 scores and computational efficiency when trained with Word2Vec embeddings.
The potential applications of this work are vast, especially in the fields of media, online content regulation, and social media platforms, where accurate detection of fake news is crucial for maintaining informational integrity.

#### 11 b. Limitations:

While the study achieved significant results, there are inherent limitations. The reliance on Word2Vec embeddings, while effective, might limit the system's ability to adapt to new forms of fake news that deviate significantly from the training data. Additionally, the computational resources required for training and maintaining such models could be substantial, especially when scaled up for real-world applications.

#### 11 c. Lessons Learned:

The project underscored the importance of selecting appropriate models and embeddings for text classification tasks. It also highlighted the need to balance precision and recall, particularly in scenarios with class imbalances, through the use of metrics like the F1 score. The research process also demonstrated the value of a stable and versatile development environment.

#### 11 d. Future Research:

Future research could explore the integration of more dynamic and adaptable language models, like transformer-based models, to keep up with evolving fake news strategies. Additionally, investigating methods to reduce the computational demands without sacrificing performance would be beneficial for practical applications. There is also a scope for broadening the dataset to include more diverse and nuanced examples of fake news, further enhancing the model's accuracy and reliability. The web app can be extended to include web-scraping funtionality to allow user to directly input links to the articles instead of pasting the whole article content.

## 10. References

[1] Sarzyńska-Wawer, J., Hanusz, K., Pawlak, A., Szymanowska, J., & Wawer, A. (2023). Are Intelligent People Better Liars? Relationships between Cognitive Abilities and Credible Lying. Journal of Intelligence, 11(4), 69. https://doi.org/10.3390/jintelligence11040069
