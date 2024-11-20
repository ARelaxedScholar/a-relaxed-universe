---
{"dg-publish":true,"permalink":"/1-cosmos/untitled-22/"}
---

202410251213
Status: #idea
Tags: 
State: #nascient
# Project Proposal

## Idea
Build a program for portfolio balancing that makes use of data and genetic algorithms to create portfolios optimized for given regimes.

It can be understood similarly to a mixture of expert portfolio balancing expert that functions as follows. We have an oracle (HMM) that estimates from data the current market regime.

Based on the given market regime, we have carefully selected portfolios that have been shown to best maximize a list of objective deployed.


## Strategy
1. Train a generative model on the S&P to make us able to generate realistic synthetic data/Alternatively simply use Monte Carlo and random data.
2. Train a Hidden Markov Model for regime identification. This will be the cortex of our algorithm and it will make deploy portfolios based on its estimation of the current market regime. We do expect some amount of delay and losses due to the time it takes to detect with a sufficient level of confidence that we are in a given regime, and we do predict it will take tuning to get a good model, but this will be the most important part of the model and we are ready to take on these losses.
3. Use reinforcement learning (evolutionary algorithms to encode portfolio allocations and test their performance.)
	   - Chromosome represent a vector of 30 or so positions, where the entries sum to 1.
	   - First 10 entry would give us coverage on equities, 10 next on bonds, and the final 10 on resources like fuel/gold/rare minerals.
4. Contrast to an "expert-based" strategy of every year investing 50% in US bonds and 50% on the S&P AND simply putting it all on the S&P without thinking about it. These are our baselines.

The goal is to see if the use of evolutionary algorithms and hidden Markov models can lead to a better performance when balancing portfolios. If this works, this could be used by banks and investment funds for the sake of better allocating capital to protect them from economical downturn whilst still maximizing profit.

## Methodology
Get data from yfinance or investing.com based on which one has the most easily available data..
Clean and filter that data, potentially create a database for it.
Leave the 10 most recent years out of the training dataset (we include COVID in on purpose to see how the algorithm copes with unforeseen events)

Train a timeseries generator based on a GAN approach. This would be combined or not with Monte Carlo to artificially expand our datasets. This will be used to test the robustness of the HMM.

For the evolutionary algorithm we'd want to reward exploration of the search space and trying novel strategies.
We'd want to give the user the ability to weight their allocation in general, such that we can encode the model and the chromosomes to have a bias towards equities, or bonds or whatever.

We'd make use of Pareto fronts to only select the most fit candidates that maximize the Sharpe ratio while minimizing the transaction costs and the spikedness of the equity curve (this should be accounted for by the Sharpe ratio but it might make sense to give it its own measurement.)
### Obvious Constraints
- probability vector for the chromosome
- negative values are not allowed


## Tools
- Python and all relevant framework
- Potentially Rust and SQL for data infrastructure
- Investing.com and Yfinance for financial data

## Data Analysis Goals
The goal is to create a data-driven portfolio strategy and then report on the performance of said strategy compared to more traditional methods such as simply putting it all on red (the S&P) or the also often seen 50/50 allocation in US equities and bonds. The first is touted to lead to the most growth and since we invest in the US stock market, it is relatively safe because of all the regulations that are involved in trading there; the other is even safer as the US government is not known to default on its debt.

Obviously here the term safe is entirely relative, investing in general is not safe and one should be cognizant of the possibility of losing money. 

## Biggest potential pitfalls
Too many moving parts, the idea sounds sensible on its head and is really just about having a portfolio of perfectly evolved portfolios to deploy in different market conditions for the sake of profit. The issue is to get there and implement the infrastructure requied to make the task possible, we might need to use a lot of different parts and train a lot from scratch. Which might be involved. This will require reassessing during the project, not training the GAN and instead simply using Monte Carlo simulations is one example of such simplification, we will need to be careful.

The other is overfitting. On financial data, the risk of overfitting is more important than usual as we are directly using said data and inferred pattern to trade and move people's money. We have to be extremely careful not to deploy strategies that make use of noise in the data rather than actual patterns.



## References
