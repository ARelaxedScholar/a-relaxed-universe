---
{"dg-publish":true,"permalink":"/1-cosmos/normal-distribution/","created":"2025-01-22T11:17:14.088-05:00","updated":"2024-06-02T21:27:17.910-04:00"}
---

202405310836
Status: #idea
Tags: [[Probability Distributions\|Probability Distributions]]
State: #nascient
# Normal Distribution
![Pasted image 20240531084950.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531084950.png)
## PDF
![Pasted image 20240531083621.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531083621.png)

## MGF for STANDARD Normal
![Pasted image 20240531085047.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531085047.png)
![Pasted image 20240531085233.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531085233.png)
![Pasted image 20240531085407.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531085407.png)
So
![Pasted image 20240531085637.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531085637.png)
If the $t^m$ does not occur in the [[Taylor Series Expansions\|Taylor Series Expansions]] of your MGF, then you can infer that the moment in question is 0.
## MGF for GENERAL Normal
![Pasted image 20240602212717.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240602212717.png)
![Pasted image 20240531085929.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531085929.png)
![Pasted image 20240531090049.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531090049.png)

## Properties
Given $X_i \sim N(\mu_i, \sigma_i^2)$ with $i=1,2,\dots, n$ where the $X_i$ are independent, we want $Y=\sum_{i=1}^n a_iX_i$:
Then the MGF for that linear combination will be 
$$
MGF_Y=exp(t(\sum_{i=1}^n a_i\mu_i)+\frac{t^2}{2}(\sum_{i=1}^n a_i^2\sigma_i^2))
$$
Such that the mean and variance are just:
- $\mu_Y =\sum_{i=1}^n a_i\mu_i$
- $\sigma^2_Y=\sum_{i=1}^n a_i^2\sigma_i^2$

By the above we get this supremely important result
![Pasted image 20240531091127.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531091127.png)
![Pasted image 20240531091217.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531091217.png)
![Pasted image 20240531091246.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531091246.png)
## References
