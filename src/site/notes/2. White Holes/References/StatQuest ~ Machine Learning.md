---
{"dg-publish":true,"permalink":"/2-white-holes/references/stat-quest-machine-learning/","created":"2025-01-22T11:17:14.714-05:00","updated":"2024-12-11T22:59:04.627-05:00"}
---

dg-publish: true
202404291928
Status: #reference
Tags: [[1. Cosmos/Machine Learning\|Machine Learning]]
# StatQuest ~ Machine Learning
## Episode  1 ~ A Gentle Introduction to Machine Learning

#### Classification vs Regression
[[Decision Tree\|Decision Tree]] as simple and silly as they can be are a type of machine learning algorithm that are used because of how simple and easily interpret-able they are. While it is typically used for binary classification, it can be used on datasets where there are more than one labels. The point is that decision trees are used when what we're dealing with a [[1. Cosmos/Classification\|classification problem]].

[[1. Cosmos/Regression\|Regression]] is about how to find the relation between [[Independent Variables\|Independent Variables]] in the context of the video the amount of yam consumed, and the [[Dependent Variables\|Dependent Variables]] which is typically the variables that we do not have easy access to. In general, we can have many many independent variables, but we're going to have one dependent one. 

#### Bias vs Variance
It teaches us the important lesson that while we train a model on training data, it will always be tested on either a validation set or a test set. The reason is simply because it is really really easy to [[Overfitting\|overfit]] the model to our testing data in such a way that our model is excellent on the training data, but terrible on the test data. It does not generalise.

The [[Bias\|bias]] is the error due to the assumptions our models make, in a [[1. Cosmos/Linear Regression\|Linear Regression]] for example, the bias will be the error due to the [[Assumption of Linearity\|Assumption of Linearity]].

On the other hand, the [[1. Cosmos/Variance\|variance]] can be understood as the error due to the sensibility of our model to fluctuations, or how much each data point strays from the sample mean. In general the less of a bias we have, the bigger the variance will be, and vice versa this is what's called the  [[Bias-Variance Tradeoff\|Bias-Variance Tradeoff]]. In an  ideal world you'd minimize both, but in that world you are God. 

In reality, you just try to minimize the error as much as you can making sure to not [[Underfit\|underfit]] so that there's no predictive power due to the model not capturing the patterns properly, or on the other other hand not [[Overfitting\|overfitting]] due to the model capturing all the slight fluctuations in the training data instead of learning the patterns, henceforth becoming useless.

## Episode 2 ~ Cross Validation

Shown : 4-Fold
Common: 10 Fold Cross Validation
Extreme: Leave One Out Cross Validation

The idea of [[Cross Validation\|Cross Validation]] which was a thing I was thinking about is how to be sure that whatever model you trained was the best possible model for the task? Let's say you're doing [[1. Cosmos/Classification\|classification]] you could use a [[1. Cosmos/Support Vector Machine (SVM)\|Support Vector Machine (SVM)]], you could use a [[Decision Tree\|Decision Tree]], you could use their papi the [[Random Forest\|Random Forest]], you could use a simple [[1. Cosmos/Logistic Regression\|Logistic Regression]], etc.

Well in the process of doing that, you're going to need a [[Training Set\|Training Set]] and a [[1. Cosmos/Validation Set\|Validation Set]], the issue is that a lot of time especially in data that are not [[Time Series\|Time Series]] the way we split the data is quite arbitrary and it is entirely possible that a given type of model happens to do better just because the given split is more kind to its specific properties.

Cross Validation is a clever technique that consists of splitting a dataset into slices and taking a proportion of those slices to train, using the remainder for training. The smart thing is that it will loop through making sure that all possible splits are used at some point as training and validation set. At it cycles through the options, it will tally the results and check which many data points each model got correct and vice versa. 

At the end of this process, we are able to know which model is the best for a given task. How exactly we implement that wasn't explained in the video, but that is quite interesting.

