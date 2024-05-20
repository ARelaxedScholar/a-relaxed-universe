---
{"dg-publish":true,"permalink":"/1-cosmos/episode-2-cross-validation/"}
---


20204291948
Status: #idea
Tags: [[2. White Holes/References/StatQuest ~ Machine Learning\|StatQuest ~ Machine Learning]]
# Episode 2 ~ Cross Validation

Shown : 4-Fold
Common: 10 Fold Cross Validation
Extreme: Leave One Out Cross Validation

The idea of [[Cross Validation\|Cross Validation]] which was a thing I was thinking about is how to be sure that whatever model you trained was the best possible model for the task? Let's say you're doing [[Classification\|classification]] you could use a [[Support Vector Machine\|Support Vector Machine]], you could use a [[Decision Tree\|Decision Tree]], you could use their papi the [[Random Forest\|Random Forest]], you could use a simple [[Logistic Regression\|Logistic Regression]], etc.

Well in the process of doing that, you're going to need a [[Training Set\|Training Set]] and a [[1. Cosmos/Validation Set\|Validation Set]], the issue is that a lot of time especially in data that are not [[Time Series\|Time Series]] the way we split the data is quite arbitrary and it is entirely possible that a given type of model happens to do better just because the given split is more kind to its specific properties.

Cross Validation is a clever technique that consists of splitting a dataset into slices and taking a proportion of those slices to train, using the remainder for training. The smart thing is that it will loop through making sure that all possible splits are used at some point as training and validation set. At it cycles through the options, it will tally the results and check which many data points each model got correct and vice versa. 

At the end of this process, we are able to know which model is the best for a given task. How exactly we implement that wasn't explained in the video, but that is quite interesting.

## References
