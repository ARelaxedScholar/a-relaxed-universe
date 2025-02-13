---
{"dg-publish":true,"permalink":"/1-cosmos/grammatical-evolution/","created":"2025-02-03T21:30:39.139-05:00","updated":"2025-02-03T22:03:24.555-05:00"}
---

202502032130
Status: #idea
Tags: [[Evolutionary Algorithms\|Evolutionary Algorithms]] 
State: #nascient
# Grammatical Evolution

[[Genetic Programming\|Genetic Programming]]

[[Context Free Grammars\|Context Free Grammars]]

[[Closed Grammar\|Closed Grammar]]

A branch of research in the field of [[Formal Languages\|Formal Languages]] and [[Computation Theory\|Computation Theory]]. 

It tries to automatically generate new computer programs, and to do so generally makes use of [[Context Free Grammars\|Context Free Grammars]] as they are expressive enough for most purposes, they use a constrained form of those called [[Closed Grammar\|Closed Grammar]] where the programs always returns values of the same type.

While CFGs are by far the most use, due to the fact they are limited to context free and regular languages, they come with their limitations.

But there are many alternative grammars that one can use to get more expressive power for given purposes.

[[Attribute Grammars (AG)\|Attribute Grammars (AG)]]

Genetic Programming evolves key components:
- Grammars: Use the most powerful grammar necessary, but no more.
- Genetic operators: Many are good, but for a simple GE, [[Effective Crossover\|Effective Crossover]] is a good choise.
- Initialisation: It plays a crucial role. A naive random initialisation will yield highly biased populations which are not useful for evolution
- Parameter Settings: Bigger problems typically require a bigger population size, be careful.
- Variants: There are definitely variants that exist and that have been shown to outperform GE on some problems. Explore them!
## References
