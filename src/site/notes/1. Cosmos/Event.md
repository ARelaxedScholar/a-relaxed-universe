---
{"dg-publish":true,"permalink":"/1-cosmos/event/","created":"2025-01-22T11:17:14.224-05:00","updated":"2024-05-29T17:47:53.957-04:00"}
---

202405240847
Status: #idea
Tags: [[1. Cosmos/Probability Theory\|Probability Theory]]
State: #nascient
# Event
Informally, an [[1. Cosmos/Event\|event]] is any subset of of the sample space $\varOmega$ which is of interest to the experimenter. If we take a coin toss, technically it is possible for the coin to fall on its side and that neither tail nor head show up. This would be a possible outcome (that we might, or not account for) but not an event since we don't care about it. Rigorously tho an event is any element of the $\sigma-$algebra that is equipped by our $\varOmega$. Simply because any measure we could muster will only work on that $\varOmega$ and anything else cannot be measured.

An event will often be worded similarly to a filter in programming languages. Like we are trying to capture a subset of the data and think about its specific properties. ie: We are looking for the outcomes that are even.
```python
event_even = df.loc[df['count_of_heads'] % 2 == 0] # checking for even
```
### Consequences of this definition
- If something occurring is of interest, then it **not** occurring is also of interest (it's the dual of it in a sense)
```python
# if we try to create a event_even, then
even_even_prime = df.drop(event_even.index) # the odd subset is created at the same time
```
- If two events are occurring? Then their interaction with each other will be of interest as well. What is their union? their intersection?
- The sample space is always an [[1. Cosmos/Event\|event]] by definition, it is literally the thing we are working on. Our workbench so to speak.

These altogether give us what's referred to as an [[1. Cosmos/Algebra\|Algebra]].

## Independence of Events
We say two events $A$, $B$ are independent when:
$P(A\cap B) = P(A)P(B)$

If $A_1, A_2, A_3, ...$ are independent then any combination of elementary set operations on those sets will be independent (assuming obviously you do not reuse sets.)

A set $A$ is independent of itself in only two cases by the definition, either $A$ is $\varOmega$ or $A$ is $\varnothing$.

By that same definition, except in the aforementioned cases, $A$ and $A^c$ are never independent. And after all this makes perfect sense, informally independence tells us that knowledge about one event occurring gives us no information about the other occurring. But here $A$ and $A^c$ are quite the opposite, in fact they are perfectly dependent. $A$ occurs iff $A^c$ does not!




## References

