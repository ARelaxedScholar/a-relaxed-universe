---
{"dg-publish":true,"permalink":"/1-cosmos/generative-additive-models-gam/","created":"2024-12-11T17:13:53.698-05:00","updated":"2024-12-11T17:27:51.626-05:00"}
---

.202412111713
Status: #idea
Tags: [[Machine Learning\|Machine Learning]]
State: #nascient
# Generative Additive Models (GAM)

Extremely powerful method that essentially allows you to treat each feature of a multivariate dataset as an independent variable from the other variables under consideration and fit models which precisely captures the relation between the response and each individual predictor precisely without needing to experiment.

It makes the rather strong assumption of additivity, that is that the contribution of each term can be computed in isolation and added to the model similarly to the independence assumption that holds in [[Principal Components Regression (PCR)\|Principal Components Regression (PCR)]].

Additivity and independence are not the same, while they are related and the latter implies the former, additivity is telling us that the contribution of the features to the response can be modeled independently. This is a different statement from saying that the features themselves are independent.

If I know two twins that are always together, but one is a math nerd and the other is a litterature major, I can model their contribution to a conversation based on the subject even though the twins themselves are pretty closely related and knowing how much one contributed definitely tells you about the other. In a similar vein, additivity assumes the contributions of each predictor to the response are independent in their effects, even if the predictor themselves are correlated or even dependent.

It can be used both for [[1. Cosmos/Regression\|Regression]] as for [[1. Cosmos/Classification\|Classification]] and can use any combination of the basis functions outlined as Lego blocks for constructing the model.


### Pros
- Relatively easy to interpret (behaviour of model can be analyzed by considering the plot of the feature with respect to its transformation with the response and the importance is given by the coefficient)
- Quick and dirty, while being powerful
- The fact we go beyond linearity allows for more expressiveness in fit
- Smoothness of each thing is obvious thanks to the degrees of freedom
### Cons
- Additivity
- Interaction term must be added in manually (more of an inconvenience than a con)

## References
[[1. Cosmos/Basis Expansions\|Basis Expansions]]