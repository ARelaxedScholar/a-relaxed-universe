---
{"dg-publish":true,"permalink":"/1-cosmos/bagging-boostrapped-aggregation/","created":"2024-12-11T20:36:52.482-05:00","updated":"2024-12-13T08:41:03.416-05:00"}
---

202412112036
Status: #idea
Tags: 
State: #nascient
# Bagging (Boostrapped Aggregation)

This method relies on the very powerful technique of [[Bootstrap\|bootstrapping]] to reduce the variance of a model!

This is not as relevant for many of the traditional models, but for [[1. Cosmos/Decision Trees\|Decision Trees]] which suffer of high variance, this technique is powerful.

It essentially consists of these very simple steps:
1. Create a bunch of bootstrapped samples using [[Bootstrap\|Bootstrap]].
2. Fit [[1. Cosmos/Decision Trees\|Decision Trees]] or other high variance model to these samples
3. Aggregate the result through averaging (typically)
4. Enjoy!?

This way of doing things takes into account the fact that [[1. Cosmos/Decision Trees\|Decision Trees]] are highly variable, as a result they fit a bunch of them and then average it all in such a way that the variance of the predictions is reduced.

It makes perfect sense, if in a team, I have people that are all trying their best but all individually suck in different ways, if I take them individually, the performance will be really hit or miss, and they'll probably screw up in very different ways.

But if I take them all and every time average their answers, while I might not get an amazing boost, I get "suck" that is more consistent.

Bagging is similar, it doesn't necessarily increase prediction accuracy, but it reduces the variance of the prediction. In practice it does increase prediction accuracy as accounting for the variance helps get a more holistic picture of how the model behave and the voting/averaging procedure helps to ensure that.

While there's nothing in the way this method is defined that forces it to be used to trees, it is typically associated with standard decision trees as they are especially convenient there. Typically we do it on trees that are unpruned which means they have high bias, but low variance and then apply the bagging method on them to reduce the variance, cheating in the [[Bias-Variance Tradeoff\|Bias-Variance Tradeoff]]. 

We lose interpretability as at any given time, we might be using the predictions of a few hundreds such trees, still the improvement in accuracy can be quite substantial. There is one key problem though, if we fit the data to a bunch of [[Bootstrap\|boostraped]] samples and that there is a strong predictor that exists in the dataset, the majority if not all the trees will be using that predictor, the problem grows the more consistently strong predictors we have in such a way that in the worst case, all the trees will be correlated.

Averaging/voting will still bring down their variance down somewhat, but much less than if the trees were uncorrelated. A method that tries to do that and that is in many-cases the defacto "boostrapping" method for trees is the [[1. Cosmos/Random Forests\|random forest]].
## References
