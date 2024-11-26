---
{"dg-publish":true,"permalink":"/1-cosmos/linear-regression/","created":"2024-08-31T23:47:13.806-04:00","updated":"2024-11-26T05:30:24.684-05:00"}
---

202411252015
Status: #idea
Tags: [[Machine Learning\|Machine Learning]]
State: #nascient
# Linear Regression

This is the machine learning method by excellence. Used everywhere mostly because it's simple assumptions, bluffing interpretative power and amazing interpretability makes it an amazing tool for those that want to do some kind of regression or even classification. It is an example of a high [[Bias\|bias]] (error due to rigidity of model), low [[1. Cosmos/Variance\|variance]] (error due to variability in the dataset) model. Look at [[Bias-Variance Tradeoff\|Bias-Variance Tradeoff]].

It is helped by the fact that any curvature looks like a line if looked at from close enough, and that often the scope of predictors that we will use is "close enough" or "zoomed-in enough" for a non-linear relation to be modelled really well by a linear model.

The fact that the assumptions fail can lead to problem when it comes to inference and whatnot, but apparently the world doesn't care, so I don't care either.

What does it do?

It assumes that a response variable can be related to the predictors by some linear hyperplane. Uh?

You can fit a line, or some higher dimension analog to data that will model it well.

The generalized form of it for which I have notes already is [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]]. Everything that applies over there applies here.

It and [[1. Cosmos/k-Nearest Neighbor\|k-Nearest Neighbor]] are the fundamental of ML and are the two techniques that every machine learning engineer worth their salt, and even just any student at all should be familiar (deeply) with.


## References
