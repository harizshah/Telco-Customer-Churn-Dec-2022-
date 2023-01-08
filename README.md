# Telco-Customer-Churn-Dec-2022-
Side-Projects for one week

## Churning Summary
- The risk of a categorical feature tells us if a group that has the feature will have
the condition we model. For churn, values lower than 1.0 indicate low risk of
churning, whereas values higher than 1.0 indicate high risk of churning. It tells
us which features are important for predicting the target variable and helps us
better understand the problem we’re solving.
- Mutual information measures the degree of (in)dependence between a categorical variable and the target. It’s a good way of determining important features: the higher the mutual information is, the more important the feature.
- Correlation measures the dependence between two numerical variables, and it
can be used for determining if a numerical feature is useful for predicting the
target variable.
-  One-hot encoding gives us a way to represent categorical variables as numbers.
Without it, it wouldn’t be possible to easily use these variables in a model.
Machine learning models typically expect all input variables to be numeric,
so having an encoding scheme is crucial if we want to use categorical features
in modeling.
- We can implement one-hot encoding by using DictVectorizer from Scikitlearn. It automatically detects categorical variables and applies the one-hot
encoding scheme to them while leaving numerical variables intact. It’s very convenient to use and doesn’t require a lot of coding on our side.
- Logistic regression is a linear model, just like linear regression. The difference
is that logistic regression has an extra step at the end: it applies the sigmoid
function to convert the scores to probabilities (a number between zero and
one). That allows us to use it for classification. The output is the probability of
belonging to a positive class (churn, in our case).
-  When the data is prepared, training logistic regression is very simple: we use the
LogisticRegression class from Scikit-learn and invoke the fit function
- Model outputs probabilities, not hard predictions. To binarize the output, we cut the predictions at a certain threshold. If the probability is greater
than or equal to 0.5, we predict True (churn), and False (no churn) otherwise. This allows us to use the model for solving our problem: predicting customers who churn. 
-  The weights of the logistic regression model are easy to interpret and explain,
especially when it comes to the categorical variables encoded using the one-hot
encoding scheme. It helps us understand the behavior of the model better and
explain to others what it’s doing and how it’s working.

## Metrics Summary
-  A metric is a single number that can be used for evaluating the performance of
a machine learning model. Once we choose a metric, we can use it to compare
multiple machine learning models with each other and select the best one
- Accuracy is the simplest binary classification metric: it tells us the percentage of
correctly classified observations in the validation set. It’s easy to understand and
compute, but it can be misleading when a dataset is imbalanced.
- hen a binary classification model makes a prediction, we have only four possible outcomes: true positive and true negative (correct answers) and false positive and false negative (incorrect answers). The confusion table arranges these
outcomes visually so it’s easy to understand them. It gives us the foundation for
many other binary classification metrics.
- Precision is the fraction of correct answers among observations for which our
prediction is True. If we use the churn model to send promotional messages,
precision tells us the percentage of customers who really were going to churn
among everybody who received the message. The higher the precision, the
fewer non-churning users we incorrectly classify as churning.
-  Recall is the fraction of correct answers among all positive observations. It tells
us the percentage of churning customers who we correctly identified as churning. The higher the recall, the fewer churning customers we fail to identify.
-  The ROC curve analyzes binary classification models at all the thresholds at
once. The area under the ROC curve (AUC) tells us how well a model separates
positive observations from negative ones. Because of its interpretability and
wide applicability, AUC has become the default metric for evaluating binary
classification models.
- K-fold cross-validation gives us a way to use all the training data for model validation: we split the data into K folds and use each fold in turn as a validation
set, and the remaining K – 1 folds are used for training. As a result, instead of a
single number, we have K values, one for each fold. We can use these numbers
to understand the performance of a model on average as well as to estimate
how volatile it is across different folds
-  K-fold cross-validation is the best way of tuning parameters and selecting the
best model: it gives us a reliable estimate of the metric across multiple folds.



