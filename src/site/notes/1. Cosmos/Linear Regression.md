---
{"dg-publish":true,"permalink":"/1-cosmos/linear-regression/","created":"2025-01-22T11:17:14.234-05:00","updated":"2024-12-07T09:58:34.793-05:00"}
---

202411252015
Status: #idea
Tags: [[1. Cosmos/Machine Learning\|Machine Learning]]
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

## A Statement about Frequentist Confidence Intervals
When trying to do [[1. Cosmos/Inference\|inference]] on parameters of a linear regression we often use [[1. Cosmos/Confidence Intervals\|confidence intervals]] which are a tool that allow us to estimate both the variance of the parameters if it was recomputed multiple times on different training sets $Tr$.

The catch is that when taking a $95\%$ interval, we are NOT saying that the population parameter will lie in the computed interval $95\%$ of the time.

After all, we have numbers, they are either within the range with a probability $1$, or not in it with probability of being in the range $0$.

What is meant by $95\%$ confidence interval or any percentage for that matter is that:
If we were to repeat the procedure used to obtain the training set on various training sets, $95\%$ of them would contain the population parameter.

Instead of giving us a probability of being or not in the interval, it gives us a measure of how confident that or intervals actually capture the population parameter based on how many samples we take.

At that confidence level, it is not impossible that the first three or even four confidence intervals fail to contain the population parameter, but as the amount of samples increase, the more confident we can be that a sizable proportion of them contain the population parameter.



## References
