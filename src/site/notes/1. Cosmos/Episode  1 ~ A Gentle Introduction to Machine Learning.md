---
{"dg-publish":true,"permalink":"/1-cosmos/episode-1-a-gentle-introduction-to-machine-learning/"}
---


## Episode  1 ~ A Gentle Introduction to Machine Learning
### 202404291944
Status: #idea
Tags: [[2. White Holes/References/StatQuest ~ Machine Learning\|StatQuest ~ Machine Learning]]
# Episode  1 ~ A Gentle Introduction to Machine Learning

## Classification vs Regression
[[Decision Tree\|Decision Tree]] as simple and silly as they can be are a type of machine learning algorithm that are used because of how simple and easily interpret-able they are. While it is typically used for binary classification, it can be used on datasets where there are more than one labels. The point is that decision trees are used when what we're dealing with a [[Classification\|classification problem]].

[[1. Cosmos/Regression\|Regression]] is about how to find the relation between [[Independent Variables\|Independent Variables]] in the context of the video the amount of yam consumed, and the [[Dependent Variables\|Dependent Variables]] which is typically the variables that we do not have easy access to. In general, we can have many many independent variables, but we're going to have one dependent one. 

### Bias vs Variance
It teaches us the important lesson that while we train a model on training data, it will always be tested on either a validation set or a test set. The reason is simply because it is really really easy to [[Overfitting\|overfit]] the model to our testing data in such a way that our model is excellent on the training data, but terrible on the test data. It does not generalise.

The [[Bias\|bias]] is the error due to the assumptions our models make, in a [[Linear Regression\|Linear Regression]] for example, the bias will be the error due to the [[Assumption of Linearity\|Assumption of Linearity]].

On the other hand, the [[Variance\|variance]] can be understood as the error due to the sensibility of our model to fluctuations, or how much each data point strays from the sample mean. In general the less of a bias we have, the bigger the variance will be, and vice versa this is what's called the  [[Bias-Variance Tradeoff\|Bias-Variance Tradeoff]]. In an  ideal world you'd minimize both, but in that world you are God. 

In reality, you just try to minimise the error as much as you can making sure to not [[Underfit\|underfit]] so that there's no predictive power due to the model not capturing the patterns properly, or on the other other hand not [[Overfitting\|overfitting]] due to the model capturing all the slight fluctuations in the training data instead of learning the patterns, henceforth becoming useless.


## References
[[2. White Holes/References/StatQuest ~ Machine Learning\|StatQuest ~ Machine Learning]]