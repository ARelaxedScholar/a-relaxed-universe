---
{"dg-publish":true,"permalink":"/1-cosmos/chapter-3-neural-net-foundations/"}
---


 202405012320
Status: #idea
Tags: [[Neural Networks\|Neural Networks]]
# Chapter 3 ~ Neural Net Foundations

Here he goes over what is [[Stochastic Gradient Descent (SGD)\|Stochastic Gradient Descent (SGD)]]
what is [[1. Cosmos/Loss\|Loss]] and why do we need it?

How do to the two aforementioned concepts relate to training a model.

The idea is tha[[2. White Holes/References/Practical Deep Learning for Coders\|Practical Deep Learning for Coders]]t all [[Machine Learning\|Machine Learning]] is, is [[Curve-Fitting\|Curve-Fitting]]. How can I find the cuve that best models the observations I have. 

The issue with most other methods is that they make assumptions about the shape of that curve, like the [[Assumption of Linearity\|Assumption of Linearity]] for [[Linear Regression\|Linear Regression]] models and because of that have a high [[Bias\|Bias]]. More importantly than that, each problem has its own function that models it, and that function can be arbitrarily complex. How painful would it be if you had to find that function by hand?

This is where [[Neural Networks\|Neural Networks]] come into play.

The very simple idea is that [[Neural Networks\|Neural Networks]] are simply mathematical functions that are composed of summations of [[Rectified Linear Units (RELUs)\|Rectified Linear Units (RELUs)]] which by a theorem known as the [[Universal Approximation Theorem\|Universal Approximation Theorem]] have been shown to be able to approximate any arbitrary function as long as enough compute and layers are provided.  

Now, since [[Neural Networks\|Neural Networks]] like any other mathematical functions are exactly that, functions, they require weights. Which must be tuned for the model to be of any use, after all since they can approximate anything, there is a HUGE variety of things that a randomly generated set of weights could predict and it is highly unlikely that it will be of any use to us.

It'd be amazing if there was some automatic way to find in which direction to optimize the weights instead of haphazardly, trying and failing until we get something that approximates a solution.

Cue, [[Stochastic Gradient Descent (SGD)\|Stochastic Gradient Descent (SGD)]] the secret sauce and fundamental underpinning of **ALL** of machine learning (and by proxy Deep Learning.)

Understand that algorithm properly, and you got the foot in the door to [[Deep Learning\|Deep Learning]].
## References

[[2. White Holes/References/Practical Deep Learning for Coders\|Practical Deep Learning for Coders]]
