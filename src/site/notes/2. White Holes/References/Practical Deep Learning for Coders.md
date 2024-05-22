---
{"dg-publish":true,"permalink":"/2-white-holes/references/practical-deep-learning-for-coders/"}
---

dg-publish: true
202404272238
Status: #reference
Tags: [[Deep Learning\|Deep Learning]]
# Practical Deep Learning for Coders

## Chapter 1 ~ Introduction
[[Walter Pitts: An Eccentric Genius?\|Walter Pitts: An Eccentric Genius?]]

Scientists are dumb at times and unable to read through a book--that what my first thought as I went through the episode and the kind of problems [[Deep Learning\|Deep Learning]] encountered. While to be fair, if I was reading about a revolutionary invention and half way through I learned it couldn't do basic stuff I'd want it to do, I'd likely put the book back as well, still. Two decades setback for AI! This was so that I could get in the industry in time, thank you God. I will not waste this time.

This one chapter gives a foray into the subjects of [[Computer Vision\|Computer Vision]], [[Segmentation\|Segmentation]], [[Tabular Models\|Tabular Models]], and [[Collaborative Filtering\|Collaborative Filtering]].

Each of these subjects are not presented in depth, but code is provided to implement a state-of-the-art version of the model that can be used on our own data if modified.

It also presses the importance of splitting your dataset into a [[1. Cosmos/Validation Set\|Validation Set]], [[Training Set\|Training Set]], and even a [[Test Set\|Test Set]] while the first two are mandatory, the latter is STRONGLY recommended.

## Chapter 2 ~ Deploying a Model
Outlines a few steps:
1. Get Data
2. Clean Data
3. Train Model
4. Be stupid!!
What? Indeed, while this is the traditional way to do it, it is often better and more efficient to train the model with the uncleaned data, and then use the model to clean the data. So...  the actual procedure should be:
1. Get Data
2. Train Model
3. Use Model to Clean Data
4. Retrain Model on that Data
5. Enjoy!

[[1. Cosmos/Data Augmentation\|Data Augmentation]] is the art of turning 1 into 10. The actual definition is any transforms that you apply to an image to effectively multiply our dataset by a factor. Each epoch the same data (images in this context) are being slightly warped and modified to allow the model to better generalise to unseen data. If you are not planning to run multiple epochs it might not be necessary, but if you do want to run more epochs it is not a terrible idea to do so.

A rarely considered approach is to think deeply about the effects of the technology not in the case of what if everything went poorly (as I like to do to prepare), but rather what would be the consequences if everything went as expected. This can have the same effects depending of your psyche, but this is an interesting perspective nonetheless.


[[Backtest:  A Surprisingly Common Term\|Backtest:  A Surprisingly Common Term]]
## Chapter 3 ~ Neural Net Foundations
Here he goes over what is [[Stochastic Gradient Descent (SGD)\|Stochastic Gradient Descent (SGD)]]
what is [[1. Cosmos/Loss\|Loss]] and why do we need it?

How do to the two aforementioned concepts relate to training a model.

The idea is that [[2. White Holes/References/Practical Deep Learning for Coders\|Practical Deep Learning for Coders]] all [[Machine Learning\|Machine Learning]] is, is [[Curve-Fitting\|Curve-Fitting]]. How can I find the cuve that best models the observations I have. 

The issue with most other methods is that they make assumptions about the shape of that curve, like the [[Assumption of Linearity\|Assumption of Linearity]] for [[Linear Regression\|Linear Regression]] models and because of that have a high [[Bias\|Bias]]. More importantly than that, each problem has its own function that models it, and that function can be arbitrarily complex. How painful would it be if you had to find that function by hand?

This is where [[1. Cosmos/Neural Networks\|Neural Networks]] come into play.

The very simple idea is that [[1. Cosmos/Neural Networks\|Neural Networks]] are simply mathematical functions that are composed of summations of [[Rectified Linear Units (RELUs)\|Rectified Linear Units (RELUs)]] which by a theorem known as the [[Universal Approximation Theorem\|Universal Approximation Theorem]] have been shown to be able to approximate any arbitrary function as long as enough compute and layers are provided.  

Now, since [[1. Cosmos/Neural Networks\|Neural Networks]] like any other mathematical functions are exactly that, functions, they require weights. Which must be tuned for the model to be of any use, after all since they can approximate anything, there is a HUGE variety of things that a randomly generated set of weights could predict and it is highly unlikely that it will be of any use to us.

It'd be amazing if there was some automatic way to find in which direction to optimize the weights instead of haphazardly, trying and failing until we get something that approximates a solution.

Cue, [[Stochastic Gradient Descent (SGD)\|Stochastic Gradient Descent (SGD)]] the secret sauce and fundamental underpinning of **ALL** of machine learning (and by proxy Deep Learning.)

Understand that algorithm properly, and you got the foot in the door to [[Deep Learning\|Deep Learning]].

## Chapter 4 ~ Intro to Natural Language Processing
Honestly for this one I didn't learn much. It was mostly review of stuff I already knew. Graphing data is important, learning steps are important, yadda yadda yadda.

To make sure I understand what is happening it would be a good idea to try to train the model from scratch, on my own. To better understand what's happening.

At the very least, this gave me an introduction to using pretrained models, in HuggingFace. Not sure if this is what UMLFit is, but oh well.




## References
