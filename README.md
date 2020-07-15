# Toxic Comment Classification

This challenge was posted in Kaggle by Jigsaw in collaboration with Google’s Alphabet. The reason I chose this dataset is to classify and remove or block rude comments online. All the comments were drawn from Wikipedia talk page where people can post their opinions and experiences online. By implementation of this project, we can reduce online harassment to provide freedom to post publicly.

## Overview 

The Aim of the project is to Build a model that is capable of correctly classifying comments into 6 categories based on level of toxicity. It is a multi label classification problem i.e. one comment can be classified in more than one category. The area of focus is to study the negative online behaviors, like toxic comments (i.e. comments that are rude, disrespectful or otherwise likely to make someone leave a discussion)

## Techniques used -
Natural Language Processing\
Text Mining\
Feature Extraction\
Classification

## Dataset Info

Source: Kaggle
About Data: Large number of Wikipedia comments which have been labeled by human raters for toxic behavior
Number of variables: 8
Number of observations: 159571
Missing values:  0
Total size: 109.6 mb

Classification Categories(Output variable):
Toxic - 1\
Severe_toxic - 2\
Obscene - 3\
Threat - 4\
Insult - 5\
Identity_hate - 6

![data_summary](https://user-images.githubusercontent.com/53157141/87509374-63edf580-c63f-11ea-8954-beb9c1d7a8d6.JPG)

![road_map](https://user-images.githubusercontent.com/53157141/87509186-0f4a7a80-c63f-11ea-9549-5d4a044fcf40.JPG)

1. Started with Exploratory data analysis to draw insights from the data and accomplish the following tasks.
    * Understand the type of Data, it’s distribution.
    * Visualize data to help detect relevant relationships between variables or class imbalances.
    * Are there any missing Values? If so, plan out the approach to impute them.
  
2. Perfomred text mining to extract valuable information.

    * Converting the text to lower case. This would ensure our similar words with different cases are treated as duplicates.
    * Removing Punctuation, Punctuation does not add any value to the text and therefore removing it won’t cause loss of information, on the contrary it would help to reduce the length of the text.
    * Removing Stop words. These are the most common words (such as “the”, “a”, “an”, “in”) used in sentences, which do not add any information. We have used the predefined list of words defined in the library- stopwords of NLTK package to filter out the common words.
    * Performed lemmatization. Lemmatization is the process of converting the word into its dictionary form. For e.g., through Lemmatization, ‘am’, ‘are’, ‘is’ will be converted to ‘be’.

3. Performed text feature extraction which is the process of taking out a list of words from the text data and then transforming them into a vectors which would be used as predictors for classification.There are many ways to extract features using NLP techniques, in this project we have used the following two approach-

    * Count Vectorization
    * Term Frequency - Inverse Document Frequency (TF-IDF)

4. Once I have extracted the features, built the following models and compared their performance.
    * Naive Bayes
    * Logistic Regression
    * Random Forest
    * XGBoost
	
## Model Performance summary
Compared models from count(CV) and TF-IDF Vectorization based on 4 model performance parameters:
1. Accuracy
2. Recall
3. Precision
4. F1 Score

![model_comparison](https://user-images.githubusercontent.com/53157141/87509706-1cb43480-c640-11ea-9e1a-56bbbceec931.png)

Random forest using TF-IDF input features provides us with the best subset of performance parameters. Hence, selected random forest as the final model.


## Conclusion
Through this project, I have tried to build a classifier that can predict the toxicity level in a comment and thus can be used to filter out such comments. Achieved 91% accuracy with the Random forest using TF-IDF input features. In 2018, Mark Zuckerberg said - "By the end of this year we're gonna have more than 20,000 people working on security and content review," This toxicity classification model can come to their rescue. 

While building the models, the major challenge I faced was with random forest and Gradient Boosting algorithms, they were time-consuming and required more computational resources; it took hundreds of megabytes of memory and was slow to evaluate.
The future scope of this project could be to implement Neural Network to improve the efficiency of the model.
