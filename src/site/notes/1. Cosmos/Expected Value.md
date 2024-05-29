---
{"dg-publish":true,"permalink":"/1-cosmos/expected-value/"}
---

202405031126
Status: #idea
Tags: [[Statistics\|Statistics]], [[Probability\|Probability]]
# Expected Value
It is a weighted average of all the values that a [[1. Cosmos/Random Variable\|random variable]] under consideration can take. It is weighted to account for the it is computed as follows:
$$
EV = \sum P(X_i)\times X_i
$$
Where each probability is weighted by the actual value of its observation.

This value gives us on average, what would be the most likely value that $X$ would take.

## Properties
1. $E(\sum c_iX_i) = \sum c_i E(X_i)$
2. $X \leq Y \leq Z \implies E(X) \leq E(Y) \leq E(Z)$

I spent an ungodly amount of time explaining expected value in [[1. Cosmos/Probability Measure (Based on Expected Value)\|Probability Measure (Based on Expected Value)]] so you can check the details there (at least until I bring it here.)
## References
