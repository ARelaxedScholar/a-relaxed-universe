---
{"dg-publish":true,"permalink":"/1-cosmos/analysis-of-variance-anova/"}
---

202406061224
Status: #idea
Tags: [[Regression Analysis\|Regression Analysis]]
State: #nascient
# Analysis of Variance (ANOVA)
## What is it?
Anova is the method that we use to analyze the variance (shockers) of elements of our model. It is used to check the statistical significance of a model as a whole.

Indeed it is used for its F statistic, which relates the MSE and the MSR and allows us to see how much explanatory power our model has.

This analysis is done through something called an ANOVA table, which is the following:
![Pasted image 20240606125243.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606125243.png)


**SSR** is called: Sum of Square of Regression (represents distance between mean line and regression line)
**SSE** is called Sum of Square of Errors or Sum of Square of Residuals (represents distance between the observations the regression line)
**SSTO** is called the Total Sum of Squares (represents the distance between the mean line and the observations)
**MS** is the Mean Square which is simply whatever *SS* is relevant divided by its degree of freedoms.

Observe that since the **SS** are computed from normally distributed parameters, the following holds:
![Pasted image 20240606125818.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606125818.png)
It follows thus 
![Pasted image 20240606125929.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606125929.png)
Since the ratio of two chi-squared divided by their respective degrees of freedom is a [[Fisher Distribution\|Fisher Distribution]].



## Inference
This is done to check whether or not our model is significant, in other words to check if all the coefficients are 0 ($H_0$) or if at least one coefficient is non 0 $H_1$.

In the [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] case, this is perfectly equivalent to a [[1. Cosmos/Test On Individual Regression Coefficient (Assuming We know our Model Is Significant)\|Test On Individual Regression Coefficient (Assuming We know our Model Is Significant)]].

Since we have a Fisher, and the Fisher is non-symmetric. We reject $H_0$ if the $F$ statistic is bigger than the $\alpha$ level. The bigger $F$ statistic is, the smaller $MSE$ the error of our model is compared to $MSR$ the deviation of the model from the means of $Y$. In other words, the model is useful to predict values. The smaller it is, the bigger the error is, and/or the smaller the deviation of the model from the mean in such a way that the coefficient is not much more useful than the mere mean line.

## Interval on Mean Response vs Interval on New Prediction
The former is typically referred to as the [[Confidence Intervals\|Confidence Intervals]] and the latter as a [[1. Cosmos/Prediction Intervals\|Prediction Intervals]]. 

While they are extremely similar, the nuance is really important. When doing an Interval on the Mean Response, we are using the model to predict what would be the average response at a given point. In other words, the variance of $Y$ at that point is inconsequential since the mean is fixed this leads to smaller error bounds. On the other hand for a prediction interval, while the point statistic is the same (since it uses the same estimator), the error becomes bigger because we HAVE to account for variation about the mean, and therefore have to make  the interval bigger to compensate for that variation.

For that reason, the confidence interval is always less than or equal to the prediction interval. The two will only be equal if the variation around the mean is null, and therefore we are dealing with a mathematical function. In other words, this will never occur in natural contexts.
## References
