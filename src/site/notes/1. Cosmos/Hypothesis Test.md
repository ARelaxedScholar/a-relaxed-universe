---
{"dg-publish":true,"permalink":"/1-cosmos/hypothesis-test/"}
---

202405181216
Status: #idea
Tags: [[Statistics\|Statistics]]
# Hypothesis Test

It's a really important concept in statistics that is always based around two hypotheses called the null hypothesis ($H_0$) and the alternative hypothesis denoted $H_1$.

It is crucial to realize that in hypothesis testing, we never "accept" the alternative hypothesis similarly to how in a court we never declare someone "innocent". Instead we "reject" the null hypothesis. While outwardly has a similar effect, the nuance is different. 
This tells us that we're on the defensive, all we can do is try to see if something is so unlikely that it has to be false, as a result that leads us to say the $H_1$ might be true, but that's beside the point.

To the concept of Hypothesis Testing and [[1. Cosmos/Confidence Intervals\|Confidence Intervals]] is always attached the concept of [[Confidence Levels\|Confidence Levels]] generally denoted $1-\alpha$. This is nothing more and nothing less than the level of confidence we have that the population parameter on which we're doing the inference falls in the range.
## Data is Normally Distributed

The normal distribution is a symmetric distribution, so depending of whether we're doing a two sided or one sided test, we will be careful to ensure that the sum of our reject area is $\alpha$.

No matter which it is, we want to ensure that for the level of confidence we have $|t_\alpha|$ or $|t_\frac{\alpha}{2}|$ is less than $|t_{datum}|$ so that we can reject $H_0$, this condition failing we say we lack the evidence to reject $H_0$.

Hypothesis testing problems are formulated in such a way that typically we WANT the $H_0$ to be false, but that varies on case.
### Hypothesis Test ~ Sigma Is Known
Then you can use the standard normal.
You [[Standardization\|Standardization]] your datum and then can use the obtained value as a Z-statistic.

You will now look at the normal distribution for it.
### Hypothesis Test ~ Sigma is Not Known
You will standardize but use a t-distribution with the relevant degrees of freedom. For [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] for example, you will need to use a $t$ distribution with $(n-2)$ degrees of freedoms.


## References
