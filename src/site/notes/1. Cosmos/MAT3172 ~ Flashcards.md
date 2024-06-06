---
{"dg-publish":true,"permalink":"/1-cosmos/mat-3172-flashcards/"}
---

TARGET DECK
Scholarly::University Notes::MAT3172
FILE TAGS: Probability

-----
## Lecture 1
START
Basic
![Pasted image 20240528151914.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240528151914.png)
Back:
![Pasted image 20240528151930.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240528151930.png)
Tags: lecture_1
<!--ID: 1716931679792-->
END

START
Basic
![Pasted image 20240528151948.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240528151948.png)
Back:
![Pasted image 20240528152002.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240528152002.png)
Tags: lecture_1
<!--ID: 1716843809304-->
END

START
Cloze
Assuming that we are talking about [[1. Cosmos/Indicator Functions\|indicator functions]]: What is the other side of this equation?
{{c1::$I_{\bigcup_{i=1}^\infty A_i}$}} = {{c2::$1-\prod_{i=1}^\infty (1-I_{A_i})$}} 
Back:
Tags:
<!--ID: 1716931679851-->
END

START
Basic
Assuming that we are talking about [[1. Cosmos/Indicator Functions\|indicator functions]]: Sketch a proof for the following fact:
$I_{\bigcup_{i=1}^\infty A_i}$ = $1-\prod_{i=1}^\infty (1-I_{A_i})$
Back:
### Proof by Professor Mahmoud Zahrepour
![Pasted image 20240528153712.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240528153712.png)
![Pasted image 20240528153746.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240528153746.png)Tags:
<!--ID: 17169334814-->
END

START
Cloze
For some [[1. Cosmos/Random Variable\|random variable]] $X$, the expected value is an operator such that:
1. If $X \geq 0 \implies E(X) \geq 0$
2. If $c \in \mathbb R \implies E(cX) = cE(X)$ 
3. $E(X_1+X_2)=E(X_1)+E(X_2)$
4. For some constant $c$, $E(c)=c$
5. If $0\leq X_n(\omega)\uparrow \text{in } n \text{ such that } X_{n+1}(\omega) \geq X_n(\omega) \text{ for all } n \implies E(X_n)\uparrow E(X)$ [[Monotone Convergence Theorem\|Monotone Convergence Theorem]]
Back Extra:
Tags:
<!--ID: 1717165475337-->
END

START
Cloze
Assuming that we are talking about [[1. Cosmos/Indicator Functions\|indicator functions]]: What is the other side of this equation?
{{c1::$I_{A \Delta B}$}} = {{c2::$(I_A+I_B)^2 ~mod ~2$}} 
Back Extra: 
Tags: You can prove this fact pretty easily using [[Truth tables\|truth tables]]
<!--ID: 1716931679913-->
END

START
Basic
We have a decreasing sequence $a_n$ which is bounded below by $M$ what can we conclude about the existence of its limit?
Back:
It exists! This limit will be $\inf a_n$ 
Tags: lecture_1
<!--ID: 1716931680082-->
END

START
Basic
We have an increasing sequence $a_n$ which is bounded above by $M$ what can we conclude about the existence of its limit?
Back:
It exists! This limit will be $\sup a_n$ 
Tags: lecture_1
<!--ID: 1716931680142-->
END

START
Basic
We have an increasing sequence $a_n$ which is bounded below by $M$ what can we conclude about the existence of its limit?
Back:
Nothing, it might exist, it might not.
Tags: lecture_1
<!--ID: 1716931680203-->
END

START
Basic
We have a decreasing sequence $a_n$ which is bounded above by $M$ what can we conclude about the existence of its limit?
Back:
Nothing, it might exist, it might not.
Tags: lecture_1
<!--ID: 1716931680274-->
END

START
Basic
We have an increasing sequence $a_n$ which is bounded below by $M$ what can we conclude about the existence of its limit?
Back:
Nothing, it might exist, it might not.
Tags: lecture_1
<!--ID: 1716987931977-->
END

## Lecture 2

START
Cloze
When referring to the $\limsup$ of a sequence of sets $A_n$, an equivalent definition to {{c1::$\bigcap_{n=1}^\infty\bigcup_{m=n}^\infty A_m$}} is that {{c2::$A_n$ occurs infinitely many times}}.
Back Extra:
Tags: lecture_2
<!--ID: 1717164510284-->
END

START
Cloze
When referring to the $\liminf$ of a sequence of sets $A_n$, an equivalent definition to {{c1::$\bigcup_{n=1}^\infty\bigcap_{m=n}^\infty A_m$}} is that {{c2::$A_n$ fails to occur only a finite number of times}}.
Back Extra:
Tags: lecture_2
<!--ID: 1717164510416-->
END

START
Cloze
When referring to sequence of sets $A_n$, the fact that {{c1::$\liminf A_n$}} occurred cues me to the fact that {{c2::$\limsup A_n$ occurred}}. This is due to the fact that {{c2::$\liminf A_n \subseteq \limsup A_n$::rationale for why}}
Back Extra:
Tags: lecture_2
<!--ID: 1717164510498-->
END

START
Cloze
When referring to sequence of sets $A_n$, the fact that {{c1::$\liminf A_n$}} occurred cues me to the fact that {{c2::$\limsup A_n$ definitely occurred}}. This is due to the fact that {{c4::$\liminf A_n \subseteq \limsup A_n$}}
Back Extra:
Tags: lecture_2
<!--ID: 1717164510559-->
END

START
Basic
We have a sequence of sets $A_n$, we are told that $\limsup A_n$ occurred, what can we conclude about $\liminf A_n$ occurring.
Back:
Nothing, since $\limsup A_n \supseteq \liminf A_n$. We only know that $\liminf A_n$ occurred if we know as well that $\lim A_n$ exists, in which case, $\liminf A_n = \limsup A_n = \lim A_n$.
Tags: lecture_1
<!--ID: 1717164510619-->
END

## Lecture 3
START
Cloze
When it comes to the property of the **EXPECTED VALUE** operator, for some {{c1::[[1. Cosmos/Random Variable\|random variable]]}} $X$, the expected value is an operator such that:
1. If {{c2::$X \geq 0 \implies E(X) \geq 0$}}
2. If {{c3::$c \in \mathbb R \implies E(cX) = cE(X)$}} 
3. {{c4::$E(X_1+X_2)$}}$=${{c5::$E(X_1)+E(X_2)$}}
4. For some constant $c$, $E(c)$$=${{c6::$c$}}
5. If {{c7::$0\leq X_n(\omega)\uparrow \text{in } n \text{ such that } X_{n+1}(\omega) \geq X_n(\omega) \text{ for all } n$}} $\implies$ {{c8::$E(X_n)\uparrow E(X)$}}{{c9:: [[Monotone Convergence Theorem\|Monotone Convergence Theorem]]}}
Back Extra: The last property especially is really important
Tags: lecture_3
<!--ID: 1717164510679-->
END

START
Basic
When talking about the properties of Expected Value, give a statement that is equivalent to the following:
If $0\leq X_n(\omega)\uparrow \text{in } n \text{ such that } X_{n+1}(\omega) \geq X_n(\omega) \text{ for all } n \implies E(X_n)\uparrow E(X)$ 
Back: If $0\leq X_n(\omega)\uparrow \text{in } n \text{ such that } X_{n+1}(\omega) \geq X_n(\omega) \text{ for all } n \implies \lim_{n \rightarrow \infty} E(X_n) = E(\lim_{n \rightarrow \infty} X_n)$ 

This statement is restatement of the [[Monotone Convergence Theorem\|Monotone Convergence Theorem]]
Tags: lecture_3
<!--ID: 1717164510740-->
END

START
Cloze
When talking of probability of unions, {{c1::$P(\bigcup_{i=1}^\infty A_i)$}} {{c2::$\leq$}} {{c3::$\sum_{i=1}^\infty P(A_i)$}}
Back Extra: You can prove that fairly easily if you use [[1. Cosmos/Probability Measure (Based on Expected Value)\|Probability Measure (Based on Expected Value)]]
Tags: lecture_3
<!--ID: 1717164510800-->
END

START
Basic
![Pasted image 20240529135708.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240529135708.png)
Back:
You simply make use of [[1. Cosmos/Probability Measure (Based on Expected Value)#Probability using Expected Value\|the definition of probability using expected measure]] and the proven inequality that $I_{\bigcup_{i=1}^\infty A_i} \leq \sum_{i=1}^\infty I_{A_i}$. 
![Pasted image 20240529135758.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240529135758.png)
Tags: lecture_3
<!--ID: 1717164510860-->
END

START
Cloze
When talking about probability of unions, {{c1::$P(\bigcup_{i=1}^n A_i)$}}{{c2::$=$}}{{c3::$\sum_{i=1}^n P(A_i)-\sum\sum_{1\leq i \leq j \leq n} P(A_i \cap A_j) + )-\sum\sum\sum_{1\leq i \leq j \leq k \leq n} P(A_i \cap A_j \cap A_k) + \dots$ }}
Back Extra: This can also be proved fairly simply using [[1. Cosmos/Probability Measure (Based on Expected Value)\|Probability Measure (Based on Expected Value)]] (at least more simply than using [[1. Cosmos/Probability Measure (According to Kolmogorov)\|Probability Measure (According to Kolmogorov)]].)
Tags: lecture_3
<!--ID: 1717164510920-->
END

START
Basic
When looking at this theorem, what is the crucial fact that can be used to prove it (hint: consider [[1. Cosmos/Probability Measure (Based on Expected Value)\|Probability Measure (Based on Expected Value)]].)
![Pasted image 20240529140604.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240529140604.png)
Back: 
Simply use the fact that:
![Pasted image 20240529140717.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240529140717.png)
and the fact that
$$
P(A_i) = E(I_{A_i})
$$
Tags:
<!--ID: 1716931679573-->
END

START
Cloze
From Calculus, when talking about [[Taylor Series Expansions\|Taylor Series Expansions]], what can we say about {{c1::$e^x$}}{{c2::$=$}}{{c3::$1+\sum_{i=1}^\infty \frac{x^i}{i!}$}} or equivalently {{c3::$\sum_{i=0}^\infty \frac{x^i}{i!}$::same thing but different bounds for summation}}
Back Extra: You should review Taylor Series at some point, man. 
Tags: lecture_3
<!--ID: 1717164510981-->
END


START
Cloze
From Calculus, when talking about [[Taylor Series Expansions\|Taylor Series Expansions]], what can we say about {{c1::$e^{-x}$}}{{c2::$=$}}{{c3::$1+\sum_{i=1}^\infty \frac{(-x)^i}{i!}$}} or equivalently {{c3::$\sum_{i=0}^\infty \frac{(-x)^i}{i!}$::same thing but different bounds for summation}}
Back Extra:
Tags: lecture_4
<!--ID: 1717164511041-->
END

START
Cloze
From Calculus, when talking about [[Taylor Series Expansions\|Taylor Series Expansions]], what can we say about {{c1::$e^{-x}$}}{{c2::$\geq$}}{{c3::$1-x$}}
Back Extra:
Tags: lecture_4
<!--ID: 1717164511102-->
END

START
Basic 
Sketch a proof (recall [[Taylor Series Expansions\|Taylor Series Expansions]]) for why $e^{-x} \geq 1-x$ is always true.
Back:
![Pasted image 20240529184728.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240529184728.png)
Tags:
END

START
Cloze
By the {{c1::[[1. Cosmos/Borel-Cantelli Lemma\|Borel-Cantelli Lemma]]}} if {{c2::$\sum_{i=1}^\infty P(E_i)<\infty$}} it follows that {{c3::$P(\limsup E_n) = 0$}} {{c3::$\text{ or in other words, }E_n \text{ does NOT occur infinitely often}$::conclusion based on definition of $\limsup$ in words}}
Back Extra:
Tags: lecture_4
<!--ID: 1717164511162-->
END

START
Cloze
By the second part of [[1. Cosmos/Borel-Cantelli Lemma\|Borel-Cantelli Lemma]], given a {{c1::collection of **independent** events $E_i$:}}, if {{c2::$\sum_{i=1}^\infty P(E_i)=\infty$}} then {{c3::$P(\limsup E_n) = 1$}} {{c4::$\text{ or in other words, }E_n \text{ occurs infinitely often}$}}
Back Extra: We really need independence to conclude that, if we drop the independence condition we become unable to use that fact that $\limsup E_n = E \implies \liminf E_n^c = E^c$ which while seemingly random is necessary for the proof. Because we end up using intersections and the fact that they're independent to replace these intersections with products of $E_i^c$.
You can attempt the proof to convince yourself.
Tags: lecture_4
<!--ID: 1717164511223-->
END


## Lecture 5
START
Cloze
When talking about [[1. Cosmos/Expected Value\|Expected Value]] in [[2. White Holes/References/MAT3172 ~ Foundations of Probability\|MAT3172 ~ Foundations of Probability]], what can you say about the following
{{c1::$E(X)$}}  {{c2::$=$}} {{c3::$\intop_{-\infty}^{\infty}x~dF(x)$}}
Back Extra: When the derivative of $F(x)$ exists, it can be written as $\intop_{-\infty}^{\infty}xf(x)~dx$
Tags: lecture_5
<!--ID: 1717164511283-->
END

START
Cloze
When talking about [[1. Cosmos/Variance\|Variance]] in [[2. White Holes/References/MAT3172 ~ Foundations of Probability\|MAT3172 ~ Foundations of Probability]], what can you say about the following (in terms of expected value)
{{c1::$Var(X)$}}  {{c2::$=$}} {{c3::$E(X^2)-[E(X)]^2$}}
Back Extra: When the derivative of $F(x)$ exists, it can be written as $\intop_{-\infty}^{\infty}xf(x)~dx$
Tags: lecture_5
<!--ID: 1717164511343-->
END

START
Cloze
When talking about [[1. Cosmos/Variance\|Variance]] in [[2. White Holes/References/MAT3172 ~ Foundations of Probability\|MAT3172 ~ Foundations of Probability]], what can you say about the following (in terms of [[1. Cosmos/Riemann-Stieltjes Integrals ~ Generalization of Riemann integrals\|Riemann-Stieltjes Integrals ~ Generalization of Riemann integrals]])
{{c1::$Var(X)$}}  {{c2::$=$}} {{c3::$\intop^\infty_{-\infty}(x-\mu)^2 dF(x)$}}
Back Extra: When the derivative of $F(x)$ exists, it can be written as $\intop_{-\infty}^{\infty}xf(x)~dx$
Tags: lecture_5
<!--ID: 1717164511404-->
END

## Lecture 6
START
Cloze
In the context of [[1. Cosmos/Moment Generating Function\|Moment Generating Function]], say you want to compute the $k^{th}$ without actually doing the $k^{th}$ derivative, what is the trick. {{c1::$E(X^k)$}} = {{c2::$k!$}}$\times${{c3::$\text{Coefficient of } t^k\text{ in the Taylor expansion of } M(t)$}}
Back Extra:
Tags: lecture_6
<!--ID: 1717164511464-->
END

START
Cloze
When talking about the [[Gamma Function\|Gamma Function]], what is {{c1::$\intop_{0}^\infty e^{-\beta x}x^{\alpha-1}$}} $=$ $\frac{\Gamma(\alpha)}{\beta^\alpha}$}}.
Back Extra: Teacher literally said memorize this, so yeah. It's important.
Tags: lecture_6
<!--ID: 1717164511524-->
END

START
Basic
When talking about the [[Gamma Function\|Gamma Function]], what exactly is it? What does it do?
Back:
### What is the Gamma Function?

Imagine you know what a factorial is, right? It's when you multiply a whole number by all the whole numbers less than it. For example:

$$4! = 4 \times 3 \times 2 \times 1 = 24$$

But what if we want to find a "factorial" for numbers that are not whole, like 3.5 or 2.2? That's where the Gamma Function comes in!

### Intuitive Explanation

The Gamma Function, usually written as \(\Gamma(n)\), extends the idea of factorial to non-integer (not whole) numbers. For whole numbers, the Gamma Function is related to the factorial but shifted by one. This means:

$$\Gamma(n) = (n-1)!$$

So for a whole number like 5:

$$\Gamma(5) = (5-1)! = 4! = 24$$

### What Does the Gamma Function Do?

The Gamma Function helps in many areas of mathematics, such as:

1. **Probability and Statistics**: It's used in distributions like the Gamma distribution and the Chi-square distribution.
2. **Complex Analysis**: It helps in studying functions that have complex numbers.
3. **Calculus**: It appears in integrals and differential equations.

### Rigorous (Right Way) Explanation

Mathematically, the Gamma Function is defined for any positive number \(x\) (and also for complex numbers with positive real parts) by the following integral:

$$\Gamma(x) = \int_0^\infty t^{x-1} e^{-t} \, dt$$

This means you take an integral (a way to add up infinite tiny pieces) from 0 to infinity of \( t^{x-1} \) times \( e^{-t} \).

### Why is it Useful?

The Gamma Function is useful because it generalizes the factorial function, allowing us to work with a broader set of numbers in equations and problems. It makes calculations in advanced mathematics, physics, engineering, and statistics possible where factorials are needed but whole numbers are not enough.

### Example

If you want to find \( \Gamma(3.5) \), you use the integral definition. While calculating it directly by hand is tough, mathematicians use tables or computers to find that:

$$\Gamma(3.5) \approx 3.32335$$

So, the Gamma Function is like a magical tool that helps us extend the idea of multiplying a series of numbers to cases where the numbers don't have to be whole. It's like having a super-powerful version of factorials!
Tags: lecture_6, chatgpt_written
<!--ID: 1716931679573-->
END

START
Cloze
The moment generating function for a $\Gamma$, with parameters $\alpha$, $\beta$ what is the following $M(t)=${{c1::$(1-\frac{t}{\beta})^{-\alpha}$}}
Back Extra:
Tags:
<!--ID: 1717164511585-->
END

START
Cloze
When talking about expansion of polynomials, fill in the blanks (assume $a$ is not an integer and $k$ is a natural number):
{{c1::$(1+x)^a$}} $=$ {{c2::$\sum_{k=0}^\infty$ ${a} \choose {k}$ $x^k$}}
Where
{{c3:: $a \choose k$}}= {{c4::$\frac{a(a-1)\dots(a-k+1)}{k!}$}}
Back Extra: 
Tags:
<!--ID: 1717164511766-->
END



## Lecture 7
START
Cloze
What is the distribution for the sample mean $\bar X$ when $n$ random variables $X_i$ {{c1::are independently distributed [[1. Cosmos/Normal Distribution\|normal]] variables::the conditifon for the following distribution to hold}}?
{{c2::$\bar X \sim N(\mu, \frac{\sigma^2}{n})$::the distribution}}
Back Extra:
Tags: lecture_7
<!--ID: 1717164511827-->
END

START
Cloze
When talking about [[1. Cosmos/Moment Generating Function\|Moment Generating Function]], the MGF for a {{c1::standard normal}} distribution is {{c2::$e^\frac{t^2}{2}$}}
Back Extra: Note this is a special case of the general formula
Tags: lecture_7
<!--ID: 1717164511887-->
END

START
Cloze
When talking about [[1. Cosmos/Moment Generating Function\|Moment Generating Function]], the MGF for a {{c1::general normal::type of distribution}} distribution is {{c2::$exp(\mu t + \frac{t^2\sigma^2}{2})$.::the formula for the MGF.)}}
Back Extra:
Tags: lecture_7
<!--ID: 1717164511948-->
END