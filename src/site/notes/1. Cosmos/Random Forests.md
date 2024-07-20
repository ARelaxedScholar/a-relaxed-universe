---
{"dg-publish":true,"permalink":"/1-cosmos/random-forests/"}
---

202407200337
Status: #idea
Tags: [[Deep Learning\|Deep Learning]], [[Classification\|Classification]]
State: #nascient
# Random Forests
The Random Forest is a genius technique that essentially takes the simple idea that if you have multiple guesses, some terribly off one way, others biased another way by virtue of them being numerous enough, the error of the ensemble will converge towards 0 or as close as a predictor for this would be. If I were to go on a leg, I'd suggest it has to do with the central limit theorem.

PreReq: 
1. Tabular dataset

Steps
1. Create a decision tree
2. Repeat step 1 a shit ton (in practical applications, a 100 trees is usually enough)
3. Store them all in a data structure that allows you to access all the trees.
4. Bam, you got a random forest.

Using it is as simple as traversing that data structure and taking the means of the inferences. By Central Limit Theorem (CTL) this mean, will likely be a good inference or at least as close as you can get with a "naive" approach.

Advantages
1. Understanding it is as simple as seeing through limpid water.
2. Computing confidence on an inference is as simple as computing the standard deviation of the averages.
3. Through Gini and other metrics , it shows you which columns are best at predicting your data.
4. Hard to mess up
5. Etc.

It's an ideal model to use as a baseline when dealing with tabular data because of how simple and straightforward it is. It also gives you deeper insight on your data and shows you which features to focus on/study deeper.

Questions:
- Why is it that you cannot overfit a random forest?
- Why does the error rate asymptotes instead of dropping to zero?
- True or False: Random Forests are resistant to junk data.



#mylearning



## References
