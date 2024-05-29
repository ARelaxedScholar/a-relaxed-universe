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
<!--ID: 1716933481434-->
END

START
Cloze
Assuming that we are talking about [[1. Cosmos/Indicator Functions\|indicator functions]]: What is the other side of this equation?
{{c1::$I_{A \Delta B}$}} = {{c2::$(I_A-I_B)^2$}} 
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
END

START
Cloze
When referring to the $\liminf$ of a sequence of sets $A_n$, an equivalent definition to {{c1::$\bigcup_{n=1}^\infty\bigcap_{m=n}^\infty A_m$}} is that {{c2::$A_n$ fails to occur only a finite number of times}}.
Back Extra:
Tags: lecture_2
END

START
Cloze
When referring to sequence of sets $A_n$, the fact that {{c1::$\liminf A_n$}} occurred cues me to the fact that {{c2::$\limsup A_n$ occurred}}. This is due to the fact that {{$\liminf A_n \subseteq \limsup A_n$}}
Back Extra:
Tags: lecture_2
END

START
Cloze
When referring to sequence of sets $A_n$, the fact that {{c1::$\liminf A_n$}} occurred cues me to the fact that {{c2::$\limsup A_n$ definitely occurred}}. This is due to the fact that {{$\liminf A_n \subseteq \limsup A_n$}}
Back Extra:
Tags: lecture_2
END

START
Basic
We have a sequence of sets $A_n$, we are told that $\limsup A_n$ occurred, what can we conclude about $\liminf A_n$ occurring.
Back:
Nothing, since $\limsup A_n \supseteq \liminf A_n$. We only know that $\liminf A_n$ occurred if we know as well that $\lim A_n$ exists, in which case, $\liminf A_n = \limsup A_n = \lim A_n$.
Tags: lecture_1
END