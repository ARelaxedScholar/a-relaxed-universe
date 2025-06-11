---
{"dg-publish":true,"permalink":"/1-cosmos/developing-a-grammar-for-aegis-money-speaks/","created":"2025-06-10T02:02:19.369-04:00","updated":"2025-06-11T00:35:34.084-04:00"}
---

202506100202
Status: #idea
Tags: [[1. Cosmos/Grammatical Evolution\|Grammatical Evolution]], [[1. Cosmos/Grammar Design\|Grammar Design]]
State: #nascient
# Developing a Grammar for Aegis, Money speaks!

Ok so I will use the principles of [[1. Cosmos/Grammar Design\|Grammar Design]] described here to try to design an efficient, and powerful grammar for new strategies. It should have baked in tokens for indicators (so that the algorithm can use those constructs directly) and then and have a designed pipeline that include entry strategy, exit strategy, take profit and stop losses so that strategies can be as robust as possible.

The principles denoted in [[1. Cosmos/Grammar Design\|Grammar Design]] come from the Handbook of Grammatical Evolution which I am reading at the time.

So now, let us define a starting grammar, we will use generative AI (gemini 2.5pro is my LLM of choice currently,) to help us refine our grammar, catch any potential errors and create a robust and **useful** grammar.

###  First, we must start by acknowledging how a strategy should be:
A strategy involves 2 main components. How do we enter the market (the conditions), and how do we exit it (take profit/stop losses/pull out.) To ensure that the generated strategies always have this baked in, it makes sense to create start which bakes this logic in:
ie: /<Start/> ::= /<entry-strategy/> /<exit-strategy/> /<take-profit-strategy/> /<stop-loss-strategy/>
This start symbol thus allows us to break the complex task of designing one grammar, to designing four smaller grammars with laser-focused goals. The task is still inherently quite related to the total so it's not really creating four entirely new grammars, but this way we know  always that every semantically valid strategy will always have the above.

### Now the operations:
Now this is a node that will be used by everything, and according to our principles of grammar design, we will want to ensure we use either prefix notation or suffix notation (in our case we will use suffix notation cause it works well with a stack.) The second thing is that we will want all the operations to emerge from this one node if possible (so that we don't induce accidental bias in the selection of operations.)

ie: \<ops\> ::= AND | OR | NOT | ADD | SUBTRACT | DIVIDE | MULTIPLY | GREATER_THAN | LESS_THAN | EQUAL_TO | GREATER_THAN_OR_EQUAL_TO | LESS_THAN_OR_EQUAL_TO | CROSSOVER | CROSSUNDER
The above are all binary operators (except NOT) and they are the ones I think would be used by far the most often. Everything else can be baked into the indicators themselves.
The last two are operators that I see being specifically useful for some indicators.

This raises one core issue though, yes we collapsed all operators to a single variable. The issue is that these operators don't all expect the same type. All the logical operators expect a boolean expression, while the arithmetic operations expect a number, finally the comparison operators at the end also expect a number but return a boolean.

We have a type-safety problem. If we think carefully about when and how these operators might arise, we can maybe elucidate a way to solve that issue while sticking to our principle of collapsing all operator to one; practicality however would suggest collapsing each type of operation to a different operator since in the first place, it is hard to think of situations where both a logical operator and numerical operator would make sense. Since this is a prototype in the first place, there is always space to make this grammar more mathematically robust after, but for now I suggest something along those lines:
\<ops\> ::= \<logical\_ops\> | \<arithmetic\_ops\> | \<comparison\_ops\>
\<logical\_ops\> ::= AND | OR | NOT
\<arithmetic\_ops\> ::= ADD | SUBTRACT | DIVIDE | MULTIPLY
\<comparison_\ops> ::= GREATER_THAN | LESS_THAN | EQUAL_TO | GREATER_THAN_OR_EQUAL_TO | LESS_THAN_OR_EQUAL_TO | CROSSOVER | CROSSUNDERGREATER_THAN | LESS_THAN | EQUAL_TO | GREATER_THAN_OR_EQUAL_TO | LESS_THAN_OR_EQUAL_TO | CROSSOVER | CROSSUNDER

### IF/ELSE?
We are starting to go somewhere, we have a general structure and we have operators to work on our elements. Let us revert to our talk about what a strategy is, at a high level one strategy includes four smaller strategies detailing how one should enter, and exit a trade. Then tacked along are two adjacent strategies detailing how one should handle themselves when IN a position, that is when to take-profits, and then to cut-losses without necessarily fully exiting the position (even though sometimes that is exactly what we do.)

So those smaller strategies are inherently understood as IF (something) ELSE do nothing blocks.

But what if we wanted the ability to nest such logic into the strategy itself? Of the sort, IF this is TRUE, then TRUE, else if that other thing is true then still true, ELSE false? We will need a IF/ELSE construct.

IF/ELSE however operates on boolean\_expressions, therefore it is our opinion that is makes more sense to start by defining boolean\_expressions first. Our first recursive operator! In practice we will need at least two recursive operators, one for logical expressions and the other for arithmetic expressions. 

Let us define both here, since it is quite easy to imagine a case where "IF (arithmetic\_expression) IS GREATER THAN (arithmetic\_expression) THEN x, ELSE y."

So both are needed:
Thinking carefully, starting with the boolean expression. 
If we let $x$ be our stand-in for boolean\_expression.

Then, either $x$ is TRUE, or $x$ is FALSE.
So, we can start with:
$x$ ::= TRUE | FALSE.

Then, it is clear that $x'$ (another expression) could also be TRUE or FALSE. If that is the case, then any of the following are also expressions:
$x$ AND $x'$| $x$ OR $x'$ | NOT $x$
We could introduce here, IF $x$ THEN $x'$; but this is not a necessary addition as this is equivalent to NOT $x$ OR $x'$.  I would choose at this level to keep the grammar simpler, since we don't gain any expressive power by adding it (keep in mind the construct is still useful so I'd want to insert it at a higher level.)

With these components we can write our first module:
\<boolean_\expression> ::= TRUE | FALSE | \<boolean_\expression> \<boolean_\expression> AND | \<boolean_\expression>  \<boolean_\expression> OR | \<boolean_\expression> NOT

Then we can define the \<arithmetic\_expression\>.
The first is that there are two types of expressions involving numbers, those returning numbers which we will refer to as arithmetic expressions, and those returning a boolean value which make use of a \<comparison\_ops\> and those that return a number that make use of an arithmetic operator.

While we will define both here, it is important to note that the first type is really just gonna be an expansion to the type of expressions included in the \<boolean\_expressions\> as this is what they really are.

Let us start by defining a \<number\> variable, which will can be replaced by a selection of often relevant numbers in finance stuff, which we will instantiate later. 

Then the second, truly arithmetic expression will be as follows:
\<arithmetic\_expression> ::= \<number\> | \<arithmetic\_expression> \<arithmetic\_expression> ADD | \<arithmetic\_expression> \<arithmetic\_expression> SUBTRACT | \<arithmetic\_expression> \<arithmetic\_expression> MULTIPLY |\<arithmetic\_expression> \<arithmetic\_expression> DIVIDE

Pretty standard business tbh. Or is it, look carefully, isn't *(2+2) - 1* also an expression? This production rule is not representing that, furthermore, while we haven't yet started talking about indicators, but in principle we'd also want the ability to compare indicator values, so \\<number\>. So let us start by making this production recursive.

\<arithmetic\_expression> ::= \<number\> | \<arithmetic\_expression> \<arithmetic\_expression> ADD | \<arithmetic\_expression> \<arithmetic\_expression> SUBTRACT | \<arithmetic\_expression> \<arithmetic\_expression> MULTIPLY |\<arithmetic\_expression> \<arithmetic\_expression> DIVIDE

Secondly, we need to replace \<number\>  which represents our preselected numbers to a more general variable which would include every numerical thing, be it the result of an indicator, or our preselected number whatever it may be.

Let us call it, \<numerical\_operand\>, we will instantiate it in details later, but yeah this will hopefully do the job.

\<arithmetic\_expression> ::= \<numerical\_operand\> | \<arithmetic\_expression> \<arithmetic\_expression> ADD | \<arithmetic\_expression> \<arithmetic\_expression> SUBTRACT | \<arithmetic\_expression> \<arithmetic\_expression> MULTIPLY |\<arithmetic\_expression> \<arithmetic\_expression> DIVIDE

As an addition, we extend the boolean expression pool as follows:
\<boolean_\expression> ::= TRUE | FALSE | \<boolean_\expression> \<boolean_\expression> AND | \<boolean_\expression>  \<boolean_\expression> OR | \<boolean_\expression> NOT | **\<arithmetic\_expression> \<arithmetic\_expression> \<comparison\_ops\>**

So now we fundamentally have all the components needed for an **IF/ELSE** block, which we will worry about later.

## References
