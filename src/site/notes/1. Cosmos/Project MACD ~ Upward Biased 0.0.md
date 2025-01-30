---
{"dg-publish":true,"permalink":"/1-cosmos/project-macd-upward-biased-0-0/","created":"2025-01-22T11:17:14.078-05:00","updated":"2024-09-18T19:29:53.472-04:00"}
---

202409181136
Status: #idea
Tags: [[Algo-Trading\|Algo-Trading]]
State: #nascient
# Project MACD ~ Upward Biased 0.0

Since here I am writing as a "scientist", the personal we will be used, but keep in mind that I worked on this project alone.

So recently I have started learning about algo-trading because a man gotta eat, and I want to make money. I also quite like the idea of working at a bank and learning about how money works, and therefore figured this kind of project was probably the best portfolio piece.

Here, this is a learning project. My first trading algorithm so to speak. I do not expect ridiculous success from the algorithm, the goal is to see if we can beat S&P with simple entry and exit rules and proper risk management.

Working through the development of this algorithm I realized how crucial it was to have proper risk-management. After all, you could have the best entry signal, in a volatile market your stop-loss could be hit stopping you out before reaching your target. On the other hand, while your investment is growing, it is quite possible that as the position grows, something happens that pushes the price down. Likely related to news, this is why you need a good take profit rule.

It thus goes without saying that without proper risk management, any trading algorithm is bound to fail.

I will now share my pseudo-code for the algorithm. Why? 
Two reasons:
- This is a portfolio piece, therefore to show my thinking process it makes sense to share the technique along with my rationale.
- I am long-term swing trading, so anything I pieced together is unlikely to be revolutionary and even if it was people knowing about it is unlikely to change a thing.
- (As a programmer obligary off by one joke)

That said here is the pseudo code:
## Iteration 1.5: Pseudo-code
```
The goal is to trade trends, specifically positive trends.

We want to limit the number of trades to avoid excessive transaction costs, so we will trade an index

  

We want to minimize losses, while maximizing profit. I want a win rate of 60% at least.

Timeframe: Trade at the Daily Level (swing trading approach)

  

Entry:

Use MACD combined with AMA for main indicator && ADR

If MACD crosses over signal line (positive MACD) && ADR > 25:

Check if price is above 50-period SMA: If so => Buy here (1% of account) and hold until exit condition

set a trailing stop loss with a 3ATR (lock in)

Take Profit:

6xATR Risk (Take 50%)

9xATR Risk (Take another 30%)

Let the rest ride until exit condition is hit.

  

If invested:

If MACD crosses below signal line (negative MACD):

Liquidate shares

If Stochastic indicates overbought but K% crosses below D%, tighten stop loss to 2ATR

  

If Stochastic falls below 80 partial exit (liquidate 75%)
```

### Why 1.5?
There's a few things to address. First, why do we start with 1.5? My first pseudo-code was in many things the same, but had static stop-losses and take profits. Out of worry about being stopped out early, and taking profits too quickly, I opted for a more dynamic approach to this problem. I also changed the timeframe from a really fast timeframe of minutely, to a higher timeframe of daily.

This might be an overcorrection, but I do not have big enough funds to stomach the transaction fees of super frequent transactions, and I do not have a setup nor did I write the code in a quick enough language to warrant doing scalping.

Taking these things into account I modified the approach to work on a daily timeframe. I will be exiting and entering trades based on that.

I also reduced the amount of equities traded from a varying set of 5 highly liquid stocks on a uptrend, to one index (QQQ) that is known for its volatility. This was for simplicity. In the future, I would want to trade this algorithm (or a more refined version of it) on as many equities (likely indexes) and other instruments as possible. Still, for a first algorithm this is  a bit too ambitious.

This gives me the 1.5. This is the main difference with my first algorithm.

### My Thinking
#### Entry
I am writing this before doing any backtesting, therefore it is quite possible that my ideas do not pan out in practice.

Still here is the thinking.
I wanted a way to detect trends, after watching a youtube video by Ross from Warrior Trading on the MACD indicator, I opted in favor of using it as the basis for my strategy. At first I wanted this to be a scalping model. If you are familiar with the youtuber, my original direction for the model is now explained.

For everyone else, in the video he was reporting how he had made 40K+ in one day thanks to trading over 30 minutes windows of the MACD crossover. I researched the indicator and saw that it was an indicator often used for trend detection.

The important bit being that when the MACD line--usually computed as the difference of two [[Exponential Moving Averages (EMA)\|exponential moving averages (ema)]]--went above the signal line (the ema of a given number of MACD values typically 9), this became a strong signal for a uptrend, and when the opposite happened then we had a signal for a downtrend. 

The basic approach since we wanted to only deal with one of them at the time, is to consider the cross above as an entry signal and the cross below as an exit signal.

So we are happy with the basic rule, except that MACD while a good indicator has two pretty consequent problems. 

First it is a lagging indicator so waiting for its signal would cause us to enter the market late. In practice this might not be a huge issue at a daily time frame, still we'd want to get the signal in as timely a fashion as possible. To solve this issue, we thought about replacing the typical EMA with an AMA. The hope was that this would slightly increase the speed of signal which would lead to quicker execution and being able to jump in at the right moments.

The second problem, is the problem of false signals. MACD is a great indicator in a trending market, but it falls short when we have a choppy market where most of the movement goes sideways. We want to avoid being caught in those trades, therefore we shall combine the MACD with another indicator to give us the strength of the signal.

We chose the ADR directly. Why? Because I just needed a good indicator of trend strength. For trend direction, the MACD takes care of that. There is an issue of lagging, but we preferred the stability of the ADR to the reactiveness of the Stochastic Indicator for entry.

As a result, if we have a combination of crossover + ADR > 25, we will take a position of 1% of our account's size, else we will pass on the trade.

Now we got about the first quarter of the problem solved.

To the exit!
#### Exit
The exit here is done a carefully. The ground is still we do not want to be left holding a bag when we have confirmation that the momentum has shifted, therefore whenever the MACD line crosses below the signal line, we want to liquidate our entire position.

The issue of lagging is still there however. Hopefully, our change from EMA to AMA is consequent enough to allow us to exit at the right moment. But still, we'd like to be careful and consider other signs.

Research showed us tha tthe MACD is often used in conjunction with the stochastic indicator. We implemented the approach outlined by Investopedia with a few tweaks. When K% crosses below D%, we expect a reversal to be coming. We do not sell mainly because we can't confirm how accurate the signal is, and using other indicators to do so would complexify the system. But when that happens we tighten our stop losses, so that if the market starts crashing down at least we dipped before that happened.

If the oscillator goes below 80, then we consider this an early sign of the trend getting exhausted and therefore sell 75% of current holdings. This is a safety measure to ensure that when the market goes down we were able to move out. On the other hand, if this does not happen we didn't fully leave our position.

The definite exit signal is the MACD crossing below the signal line. When that happens, while it could be a false signal we do not wait and liquidate all our remaining shares. Everything liquidated at this point is what we held out for.

So this concludes our exit strategy. We're about 50% of the way there.
#### Risk & Take Profits
So,  let it be known that I have a bias for simple approaches. Why? A background in data science (I am an undergrad in it) showed me how easy it is to overfit to data and convince ourselves that we did the right thing. As a result the more easy to interpret and explainable the relations are, the better. This typically means less flexibility in the model itself, but that's a tradeoff I am willing to make.

The second is, this is not a "prediction" task. Or at least I do not envision algorithmic trading as that. While it would be technically possible to chance upon a model that predicts the future of price action to a very high level of accuracy, and that such an oracle would likely be the holy graal for money making, it is practically impossible that such a model could be developed by mere humans. I would go as far as saying as it's liekly a fool's errand, at least until one has built a system that already generates consistent profits in such a way that they can afford to pursue such foolishness.

Foolishness is not meant as pejorative here, it is not meant as positive either. I understand "foolishness" as **whatever action that detracts an individual from reaching their end-goals**. If my end goal is learning japanese to a fluent level, it might be fooolish for me to sit down and **only** read haikus.

Still, this foolishness is only bad if one mistakenly believes that they're doing something "productive," as long as one is aware of their foolishness and actively chooses it, it means that at least for that individual there is something good beyond the bad one my instinctly think of.

Rambling aside, I am biased in favor of simple systems. Defined as a rule-based system that could feasibly be traded by anyone given the amount of brain compute a computer has, and we'd expect similar returns.

If humans (us included) weren't dumb and foolishly blinded by the past and greed, it would maybe be possible to use a trading bot that trades a black box, leave it our money  and analyze backtests and results without overreaction. However, we do not trust ourselves to do that, and even if we did how would we be able to differentiate overfitting to past data VS a magical algorithm that could work if one does not have a clear understanding of the moving pieces.

This is why, I lean towards dumb and simple systems. Me being a noob definitely plays a part in that.

This gives us a clear entry and exit. Since the edge here is not magic, and the technique alone will probably not give results that are incredible we suspect that risk management will be the biggest component. For generalization and adaptivity, we will be using ATR based risk and take profits.

We want a roughly 2:1 risk to reward ratio for the bulk of our trades, with the possibility to let the trade go for longer if the trend is strong enough.







### My Thinking After Backtesting


[[Project MACD ~ Upward Biased 0.1\|Project MACD ~ Upward Biased 0.1]]



## References
