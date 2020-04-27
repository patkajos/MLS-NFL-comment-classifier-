MLS & NFL comment classifications in Natural Language Processing with Reddit

- General statement

I will explore text mining using MLS and NFL comments from reddits. we will spend some time preparing the textual data. This will involve cleaning the text data, removing stop words and stemming. It contains x variable which is  the reddit comment from mls ans nfl text and one variable Y containing  2 possible outcomes. This projet is designed to build a classication tool to predict whether a comment is MLS or NLF using Natural language processing.

To infer the reddit comments, we use two classifiers: logistic regression and multinomial naive Bayes. We will tune the hyperparameters of both classifiers with grid search to optimize our search.

- Loading the data

Our data were imported from subreddit using reddit  built- in API  functionality. The request of data to the server.
narrowed down using  a size parameters ()  which  returns a json format data .There are two  class of 
comments that we are going  predict in this project  - MLS which is associated with a binary 1 and NLF with 0 

- Exploratory Data Analysis

There are 2 class labels we will predict: 1 for MLS , 0 for NFL.
The class labels are pretty much balanced. 56% for MLS and 43% for NFL

- Models used : - Logistic regression
                - Miltibinomial naive bayes 
                
the vectorizers and classifiers all have configurable parameters. To choose the best parameters, we need to test on a separate validation set. This validation set was not used during the training. Yet, using only one validation set may not produce reliable validation results. Due to chance, we might have a good model performance on the validation set. If we would split the data otherwise, we might end up with other results. To get a more accurate estimation, we perform cross-validation.we also use grid search to optimize the search for  best parameter to the model.

- Evaluation metrics

In our function grid_vectwe additionally generate the classification_report on the test data. This provides some  metrics per target class. This might be more appropriate here.These metrics are the precision, recall , sensitivity,accuracy.
Precision: Of all rows we predicted to be a certain class, how many did we correctly predict?
Recall: Of all rows of a certain class, how many did we correctly predict.

- Conclusion

Both classifiers achieve the best results when using the features of the CountVectorizer
the Multinomial Naive Bayes outperforms logistic regression  classifier
The best performance on the test set comes from the Multinomial Naive Bayes with features from CountVectorizer.