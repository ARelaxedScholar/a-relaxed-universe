---
{"dg-publish":true,"permalink":"/1-cosmos/grammar-design/","created":"2025-05-30T17:20:19.825-04:00","updated":"2025-06-02T14:18:40.492-04:00"}
---

202505301720
Status: #idea
Tags: [[1. Cosmos/Grammatical Evolution\|Grammatical Evolution]]
State: #nascient
# Grammar Design
Arguably one of the most important components of grammatical evolution. There is often an infinite number of potential grammars to explore any one problem, but similarly to how "natural languages" are ill-fitted to express algorithms with the degree of specification needed for implementation, some grammar designs are just better at expressing the problem.

This is crucial as better grammar design leads to quicker convergence, and better solutions.

Since the evolution process is exceptionally robust, you can often get by with a subpar setup, but that is far from ideal.

### Some principles
- Recursive symbols are crucial:
	- If you want solutions to be varied, and you want the generated solutions to be able to have varyign lengths, you need recursion. Without it, you are always limited to a given size. There's a few caveats though.
		- Too many recursive symbols make for a hard to understand grammar.
		- It is easy to create a grammar that actually doesn't solve the problem
		- We don't want "explosive" grammars (where there is a symbol with more recursive productions than consuming ones.)
     So we want "balanced" grammars, that is a grammar that isn't overly biased towards recursion. This way we have a search process that can actually complete, and we can hope to get useful solutions.
- Unlinked productions, use them! You want to allow your GE to explore freely, linked productions kinda forces you to pick repeatedly the same options. So don't use em. In practice, [[Functional Linkage\|Functional Linkage]] comes from having two symbols with a related number of productions. If say X has 12 productions, then X mod 12 will be a number from 0 to 11, if Y has 6 prods, then if X had chosen 5, for example. 5mod12, will give you 5. 5 mod 6, iwll also give you 5. So even though, they are two different productios they make the same choice. Which is bad cause this bias prevents us from exploring the search space efficiently. In practice, to unlink, just pick your starting symbol, it stays unchanged. Go to the next one, multiply its number of prods to your starting one. This will give you how many prods the symbol should have now (you'll obtain it, by essentially duplicating the productions you have until you reached the number). Whatever number you obtained at the previous step, you will take it and multiply it by the number of prods of whatever symbol is next and do the same thing. This careful engineering will functionally unlink your symbols in such a way that the modulos don't consistently pick the same choice index from context to context.
- Avoid grammar bias: You should make it so all operators have the same bias (so basically they don't have a bias.) Failure to do so, will lead to a suboptimal exploration of the search space. In practice, the simplest fix is to collapse all terminals to one symbol to generate the operations.
- Use **Prefix/Postfix**, but NOT **infix**!: Prefix/postfix are nice because they are unambiguous, whether we have parentheses or not, the expressions are always read the same way. As a result, when using genetic operators, the resulting expressions make sense. While we might lose some locality of search space, we gain unambiguousness. Infix provides us with a connectedness of the search space locally, but breaks as soon as crossover starts because nonsensical or ambiguous expressions can be derived from the process.
- Compromise grammars: 
	- All the transformations and principles mentioned above can be achieved algorithmically. But at times, their use might lead to an explosive growth of the grammar itself making it hard to understand (think about the unlinking algorithm for example.) At times, adding a single well-chosen terminal symbol to maintain the readability of the grammar (at the loss of some crossover locality.) In practice, this well-chosen symbol will just extract the elements from the previous humongous symbol and take its terminals.

### Caveats:
These changes we do and principles are for the ensurance or proper utilization of the search space, ti should be noted that whether or not it increase performance depends. IF a problem search space has a biased nature (some solutions just do better when using some operators,) then of course unbiasing will make performance worse. 

## References
Too many 