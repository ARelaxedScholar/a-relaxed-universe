---
{"dg-publish":true,"permalink":"/1-cosmos/random-forests/","created":"2024-08-31T23:47:14.989-04:00","updated":"2024-12-13T08:46:11.066-05:00"}
---

202407200337
Status: #idea
Tags: [[Deep Learning\|Deep Learning]], [[1. Cosmos/Decision Trees\|Decision Trees]], [[1. Cosmos/Machine Learning\|Machine Learning]]
State: #nascient
# Random Forests
The Random Forest is a genius technique that essentially takes the simple idea that if you have multiple guesses, some terribly off one way, others biased another way by virtue of them being numerous enough, the error of the ensemble will converge towards 0 or as close as a predictor for this would be. If I were to go on a leg, I'd suggest it has to do with the central limit theorem.
It is an improvement from the [[1. Cosmos/Bagging (Boostrapped Aggregation)\|Bagging (Boostrapped Aggregation)]] method used on trees which while potent at reducing the variance of trees, is not as good as it could be considering the correlation between trees which might inflate the variance rather than decrease it. After all, if it happens that a dataset have a few very good predictors for splitting, regardless of whether we are in tree 1 or tree 1,000,000 (we'd never go remotely that high but still) most if not all the trees will use these parameters to start the split and will look rather similar, averaging results of correlated results is not as good as averaging results of uncorrelated processes.

So how do we use random forests.

PreReq: 
1. Tabular dataset

Steps
1. Create a decision tree at each split splitting picking only from a random sample of $m$ parameters
2. Repeat step 1 a shit ton (in practical applications, a 100 trees is usually enough)
3. Store them all in a data structure that allows you to access all the trees.
4. Basically cannot overfit (overfits in ways opposite to common wisdom, increasing the number of trees to infinity will not lead to over fitting, having not enough trees will since not enough people are voting and only the opinion of a few potentially stupid people matters. Increasing the number of trees just reduces variance, but after some point we can't go down lower and adding more just kinda does nothing.)
5. Bam, you got a random forest.

Using it is as simple as traversing that data structure and taking the means of the inferences. By Central Limit Theorem (CTL) this mean, will likely be a good inference or at least as close as you can get with a "naive" approach.

Advantages
1. Understanding the how of it is as simple as seeing through limpid water.
2. As opposed to [[1. Cosmos/Bagging (Boostrapped Aggregation)\|Bagging (Boostrapped Aggregation)]] trees which will often have correlated trees, this approach ensures that each tree is uncorrelated.
3. Computing confidence on an inference is as simple as computing the standard deviation of the averages.
4. We can easily compute feature importance
5. Hard to mess up
6. Etc.

### Cons
- Like [[1. Cosmos/Bagging (Boostrapped Aggregation)\|Bagging (Boostrapped Aggregation)]] trees, they can be computationally intense as we must fit many models
- They lose the best trait of decision trees which are their interpretability.

It's an ideal model to use as a baseline when dealing with tabular data because of how simple and straightforward it is. It also gives you deeper insight on your data and shows you which features to focus on/study deeper.

Reducing variance is not the only way to go for increasing the performance of trees though, a really powerful method is called [[1. Cosmos/Boosting\|Boosting]] which often performs better than random forests in terms of pure accuracy. They are also remarkably flexible, a must know for a data scientist.

Questions:
- Why is it that you cannot overfit a random forest?
- Why does the error rate asymptotes instead of dropping to zero?
- True or False: Random Forests are resistant to junk data.



#mylearning



## References
