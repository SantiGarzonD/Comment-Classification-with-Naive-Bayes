# Multinomial Naïve Bayes Classifier - the YouTube Spam Collection Data Set
## Project Objective

Welcome, here I created a YouTube Spam Comments Classifier with the Naïve Bayes Classifier. I created this project in order to:

* Practice with the Naïve Bayes Classifier, that's why I only use this method.
* Practice Text Classification
* Share with fellow learners as myself how to work with it
* Go through a simple DataScience project

## Resources used:

- Python
- Jupyter Notebooks

**Packages:**
  - numpy
  - seaborn
  - matplotlib
  - scikit-learn
  - pandas

**Anaconda env creation** ```conda env create -f environment.yaml```

## Data
The data was downloaded from the kaggle Data Set YouTube [*"Spam Collection Data Set"*](https://www.kaggle.com/datasets/lakshmi25npathi/images).

The data are 5 different Datasets containing comments for 5 different Youtube Videos, and are already classified as:

- 1: Spam Comment
- 2: Ham Comment

## EDA

The data was pretty clean and did not contain Null Values, so the only left thing to do was to extract the columns we needed: The Comment and the Class.

Next, the data was divided into train and test sets

## Data Transformation

The data was passed through a CountVectorizer sklearn's class which turned each comment into a vector, in which each position represent how many times a specific word appeard in the comment.

The lenght of the vector ended beeing of 3814 different words (Words longer than 1 character).

## Model Building

For the classifier I created 3 Naïve Bayes Models:

- The Default MultinomialNB
- The MultinomialNB with the priors adjusted on [0.6, 0.4] for Ham and Spam Comments respectively.
- The MultinomialNB with the priors adjusted on [0.7, 0.3] for Ham and Spam Comments respectively
- The ComplementNB with the priors adjusted on [0.7, 0.3] for Ham and Spam Comments respectively

### Metrics

I chose to use the Confussion Matrix, focusing on Precision and Recall Metrics to Evaluate how the models changed their performances. I chose these Metrics in order to see how the model correctly classifies the Spam class, and because they are easy to understand.

## Model Performance

Model Performance for Spam Classification

|Model|Precision|Recall|
|-----|---------|------|
|Default MultinomialNB|89%|95%|
|MultinomialNB with [0.6, 0.4] priors|96%|95%|
|MultinomialNB with [0.7, 0.3] priors|97%|94%|
|ComplementNB with [0.7, 0.3] priors|93%|95%|