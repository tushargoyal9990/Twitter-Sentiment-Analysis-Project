# Twitter-Sentiment-Analysis

## Introduction
The project aims to classify the tweets into their respective classes. We've tried to study the use of NLTK Library, Count Vectorizer and Multinomial Naive Bayes Algorithm.

## Description of Dataset
Twitter US Airline Sentiment Dataset consists of 14640 tweets divided into 3 categories as positive, neutral or negative stored in a csv file that can be downloaded from Kaggle (https://www.kaggle.com/crowdflower/twitter-airline-sentiment). The sample of dataset is as follows:

![alt text](https://github.com/tushargoyal9990/Twitter-Sentiment-Analysis-Project/blob/main/Images/Dataset.PNG)

## Methodology

### Step 1 : Cleaning Tweets
Tweets are cleaned so as to remove the less important words known as stop words because they don't significantly influence the final output. The text is firstly tokenized by splitting it on space character (i.e. ' ') and each token is checked whether for following cases:

* If the token is a stop word (as specified in English language in NLTK library), punctuation mark or a number it is removed.
* If the token can be lemmatized, it is done. In Lemmatization, the algorithm have the knowledge of meaning of word. In fact, it can be understood that it refers a dictionary to understand the meaning of the word before reducing it to its root word, or lemma. For example, a lemmatization algorithm would know that the word better is derived from the word good, and hence, the lemme is good.

### Step 2 : Count Vectorization
CountVectorizer is used to convert a collection of text documents to a vector of term/token counts. It creates a matrix in which each unique word is represented by a column of the matrix, and each text sample from the document is a row in the matrix. The value of each cell is nothing but the count of the word in that particular text sample. 

We've created 9000 features using both 1-grams (1 word features) and 2-grams (2 word features). 2-grams has been used to keep into account the effect of "not" because it can influence the category to which the tweet belongs. For example, "good" increases the probability of a tweet to get classified as positive but "not good" increases the probability of a tweet to get classified as negative.

### Step 3 : Multinomial Naive Bayes
Multinomial Naive Bayes algorithm is a probabilistic learning method that is mostly used in Natural Language Processing (NLP). The algorithm is based on the Bayes theorem and predicts the tag of a text such as a piece of email or newspaper article. It calculates the probability of each tag for a given sample and then gives the tag with the highest probability as output.

## Results
The Classification Report of the algorithm is as follows:

![alt text](https://github.com/tushargoyal9990/Twitter-Sentiment-Analysis-Project/blob/main/Images/Report.PNG)

## Conclusion
The algorithm performs decently but is still getting confused among negative and neutral tweets. The performance can be further improved by using complex NLP alogirthms like RNNs.
