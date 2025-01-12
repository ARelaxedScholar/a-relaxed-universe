---
{"dg-publish":true,"permalink":"/1-cosmos/hill-climbing/","created":"2025-01-12T00:19:14.446-05:00","updated":"2025-01-12T09:03:52.448-05:00"}
---

202501120019
Status: #idea
Tags: [[1. Cosmos/Optimisation\|Optimisation]]
State: #nascient
# Hill Climbing

It is a generalization of [[Gradient Descent\|Gradient Descent]]. Gradient descent when it works is great, it's intuitive, it makes sense, it's mathematically elegant, etc.

Like gradient descent, they are a type of [[Single-State Optimisation Methods\|single-state optimisation method]], that is methods who are only ever evolving/improving one solution at a time.

The catch is that it requires a gradient. If your objective function is non-differentiable or wouldn't have a meaningful derivative (i.e: count of failures of agent within an environment) then it will not work.

Hill climbing is a generalization ofgradient descent that does away with the gradient and instead approximates it through the process of doing a tweak (kind of like adding a small dx) and comparing to the previous solution (skips the calculating slope and extimates it by instead checking if we are higher ahead than the previous solution.)

They are a kind of local optimization algorithm which means that like gradient descent, it would not be a bad idea to run them a few times from random starting points to allow us to eventually convege to the global optimum.

This generalization also allows us to more easily introduce the cocnept of accepting degradation, the proposed algorithm by defautl is greedy but since this implementation no longer relies on gradient but rather the binary idea of betterworse, we can then code logic to under certain circumstances accept degradation.

Different approaches to hill climbers are:
- [[Simulated Annealing\|Simulated Annealing]] ~ Add a probability component to compute how likely we are to accept degradation.
- [[Steepest Ascent\|Steepest Ascent]] ~ approximates gradient computation by generating a unch of soltuions to approximate the direction of the gradient and then compares the retained solution retained the step before.
- [[Steepest Hill Climbing with Degradation\|Steepest Hill Climbing with Degradation]] ~ You are much more lenient, accepting any degradation no matter what, except that you keep track of the best encountered during the entire optimization journey. Still to ensure that we don't go entirely down the drain, at each step the solution that gets to go the next step is the best from the tweaks of the candidate solution.

## References
