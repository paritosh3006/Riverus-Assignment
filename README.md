# Riverus-Assignment
Sentiment Analysis


Firstly I have imported 1.txt, 2.txt, 3.txt and stored them in df1, df2, test_df. After that to build a single training dataset I combined df1 and df2 into a single dataset named as df and on the 'Text' column of df performed some preprocessing steps and after that droped all the duplicate rows and shuffled all the rows of dataset to get a unbaised model. After that I analysed the data and checked whether there is a need to remove stopwords or not and also observed that there is not a large difference between the counts of both sentiments available to us in our training dataset. Now before spliting the dataset in train and validation dataset, I performed stemming on the text column to reduce the inflected words to their root form. Now after spliting data I have used sklearn's CountVectorizer to convert the text into a matrix of token counts. Now fit the model on our training dataset after tuning our hyperparameters using gridsearchcv and predict on our validation set and find the accuracy for the same. I have performed the above process for two classifiers 1. LogisticRegression and 2. Naive Bayes's MultinomialNB and observed that we are getting more accuracy for MultinomialNB. And thus I trained my complete training dataset on Naive Bayes's MultinomialNB model and predicted the sentiments for our test dataset.

Report for our validation set:

Model 1:
Classifier: LogisticRegression Best parameters: {'C': 1, 'class_weight': None, 'penalty': 'l2'}
Accuracy: 0.8698315467075038 Confusion Matrix: [[253 44] [ 41 315]]

Classification Report : precision recall f1-score support

       0       0.86      0.85      0.86       297
       1       0.88      0.88      0.88       356
micro avg 0.87 0.87 0.87 653 macro avg 0.87 0.87 0.87 653 weighted avg 0.87 0.87 0.87 653

Model 2:
Classifier: MultinomialNB Best parameters: {'alpha': 1}
Accuracy: 0.889739663093415 Confusion Matrix: [[261 36] [ 36 320]]

Classification Report : precision recall f1-score support

       0       0.88      0.88      0.88       297
       1       0.90      0.90      0.90       356
micro avg 0.89 0.89 0.89 653 macro avg 0.89 0.89 0.89 653 weighted avg 0.89 0.89 0.89 653
