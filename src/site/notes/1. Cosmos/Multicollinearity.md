---
{"dg-publish":true,"permalink":"/1-cosmos/multicollinearity/","created":"2024-08-31T23:47:13.546-04:00","updated":"2024-06-13T15:15:07.105-04:00"}
---

202406131503
Status: #idea
Tags: 
State: #nascient
# Multicollinearity
Multicollinearity is what happens when a [[1. Cosmos/Regression\|Regression]] model with multiple predictor variables is hard to interpret because predictor varialbes interact with the response variable and each other in non-trivial ways.

It is something that we want to reduce because by assumption each $b_i$ represents the change in $Y$ when keeping all other $x$ constant, but when multicollinearity is there, this is functionally impossible since changing $x_i$ implicitly changes the value of all the $x_j$s to which it is collinear. You can check for collinearity by plotting one regressor against another and there seems to be a linear relation between the two, if there is you would fail to include one of the two.
![Pasted image 20240613151223.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240613151223.png)
In this image, $x_1$ and $x_2$ are strongly correlated which is problematic, but there doesn't seem to be correlation between the other regressors.
Therefore the only problematic pair is the first one, and we would fail to include it.

You can get that information through correlations table as well:
![Pasted image 20240613151413.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240613151413.png)
In this case since the correlation between $x_1$ and $y$ is stronger than the one between $x_1$ and $x_2$, we would pick the first one.


## References
