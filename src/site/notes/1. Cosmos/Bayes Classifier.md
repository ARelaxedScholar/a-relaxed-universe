---
{"dg-publish":true,"permalink":"/1-cosmos/bayes-classifier/","created":"2024-12-11T09:52:18.807-05:00","updated":"2024-12-11T10:00:47.800-05:00"}
---

202412110952
Status: #idea
Tags: [[1. Cosmos/Classification\|Classification]]
State: #nascient
# Bayes Classifier

This is provably the best classifier possible on data that will achieve the lowest classification rate short of literal divination. It makes use of the [[Bayes Theorem\|Bayes Theorem]] to compute the posterior probabilities of a class $k$ having generated an observation $X$. It's as good as we get, as a testament of that, the lowest possible classification error attainable is called the [[Bayes Error\|Bayes Error]]. It is optimal under perfect knowledge conditions and is thus often used as a reference of how well a model is performing on toy datasets. It could be seen as a counterpart of the [[Null Classifier\|Null Classifier]] which would always take the laziest/most naive approach to classification giving us the worst error rate that someone actively trying could get.

So what is the catch? Why is is that we have so many classifiers then?
Well, the issue is that the parameters needed to fit it are basically never known and so it serves as a pie in the sky goal that other models try to approximate either directly like in the case of [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]], [[1. Cosmos/Quadratic Discriminant Analysis (QDA)\|Quadratic Discriminant Analysis (QDA)]], or [[1. Cosmos/Naive Bayes\|Naive Bayes]], where we approximate both  the likelihood and the prior and do something with it.

Or indirectly where we skip the Bayes theorem and try to estimate the posterior probability directly without computing priors like in the case of [[1. Cosmos/Logistic Regression\|Logistic Regression]], or [[1. Cosmos/Neural Networks\|Neural Networks]], [[Support Vector Machine\|support vector machines]] as well.


## References
