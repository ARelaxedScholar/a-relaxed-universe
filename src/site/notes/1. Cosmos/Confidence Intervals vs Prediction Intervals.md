---
{"dg-publish":true,"permalink":"/1-cosmos/confidence-intervals-vs-prediction-intervals/"}
---


202405181450
Status: #idea
Tags: 
# Confidence Intervals vs Prediction Intervals in Simple Linear Regression
[[1. Cosmos/Confidence Intervals\|Confidence Intervals]] and [[1. Cosmos/Prediction Intervals\|Prediction Intervals]] are tightly bound concepts. 

### Confidence Intervals
I am writing this in the context of [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]]. A [[1. Cosmos/Confidence Intervals\|confidence interval]] is what I use if I am trying to find the range of values in which my mean observation will fall, this is what I use because the $E(\hat Y)$ is $Y$ which nukes the error term (variation around the mean), thanks to that the calculations are simplified and I get that for $N(mean, variance)$
$$
Y \text{ is distributed according to }  N(\beta_0 + \beta_1x, \sigma^2(\frac{1}{n}+\frac{(x_0-\bar X)^2}{SS_{xx}}))
$$
Where $x_0$ is the value at which I am trying to estimate the mean of $Y$.

### Prediction  Intervals
On the other hand, when I try to estimate the range of values for a **specific** observation, I need to consider the fact that at a given value of $x$ there is a natural variance around the mean. I cannot simply eliminate the error which gives me a new formula being:
$$
Y \text{ is distributed according to }  N(\beta_0 + \beta_1x, \sigma^2(1+\frac{1}{n}+\frac{(x_0-\bar X)^2}{SS_{xx}}))
$$
### The $\sigma^2$ problem (Just Replace with MSE)
As usual, since we basically never actually know $\sigma^2$ we replace it by the mean squared error $MSE$ which is an unbiased estimator. 
### Warning
Since we know that $Y$ follows a normal distribution, once we've found its variance we've won and can do [[1. Cosmos/Hypothesis Test\|Hypothesis Test]] and [[1. Cosmos/Confidence Intervals\|Confidence Intervals]] easily. 

We just need to stay cognizant of WHAT exactly we're trying to estimate, a specific observation? ([[1. Cosmos/Prediction Intervals\|Prediction Intervals]]) 

The mean response at a given value? [[1. Cosmos/Confidence Intervals\|Confidence Intervals]]

### An Example
Say I have a linear model, that relates the time I study to my grades. If I try to predict on average how much I would get if I studied 200 hours, something crazy for me, I would use a confidence interval. Because I am trying to see what is the mean response of my grades to the time I study. This will be tighter.

If on the other hand I wanted to compute for the same amount of time, the range of grades I should expect for my next exam then I use a prediction estimate. In the former, I do not have to worry about the variation around the mean since we know that the expected value of Y hat is just my estimator which is what I am using, in the prediction estimate case, since I want to know the range for a specific value I need to account for the fact that for the same amount of time studied I might get less for a harder exam, and more for an easier exam (variability around the mean) which changes how I derive the formula. Is that the right idea?

### Summary
In general, they are **NOT** the same. In fact we would only expect them to be the same if the $MSE$ is $0$ and there's no variation around the mean.

## References
