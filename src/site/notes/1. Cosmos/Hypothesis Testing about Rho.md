---
{"dg-publish":true,"permalink":"/1-cosmos/hypothesis-testing-about-rho/","created":"2024-08-31T23:47:13.574-04:00","updated":"2024-06-07T21:20:50.404-04:00"}
---

202406061356
Status: #idea
Tags: [[Regression Analysis\|Regression Analysis]], [[2. White Holes/References/MAT3375 ~ Regression Analysis\|MAT3375 ~ Regression Analysis]]
State: #nascient
# Hypothesis Testing about Rho

The estimator for $\rho$ is:
$$
r = \frac{S_{xy}}{\sqrt{S_{xx} S_{yy}}} = \hat\beta_1 \sqrt\frac{S_{xx}}{S_{yy}}
$$

## The Simple Case
To check for significance of the correlation, we use an hypothesis test with the following t stat, under the assumption that $\rho=0$
$$
T = \frac{r\sqrt{n-2}}{\sqrt{1-r^2}} \sim t(n-2)
$$
In R, we use cor.test

## The Harder Case
Sadly, when we want to check for cases where we thing $\rho$ is different from $0$, we need to use a transformation. Indeed, if $H_0$ is $\rho=\rho_0 \ne 0$ , then we use:
$$
Z_{obs} = \frac{1}{2}[ln(1+r)-ln(1-r)] = \frac{1}{2}[ln(\frac{1+r}{1-r})]\sim N(\mu_z; \frac{1}{n-3})]
$$
Where $\mu_z$ is:
$$
\mu_z= \frac{1}{2}ln(\frac{1+\rho}{1-\rho})
$$

Besides the fact these formulas come from nowhere, since $Z_{obs}$ is normally distributed, we can reject if $|Z_{obs}|>Z_{\frac{\alpha}{2}}$ 
## References
