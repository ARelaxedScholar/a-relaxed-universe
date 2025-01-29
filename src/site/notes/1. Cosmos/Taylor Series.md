---
{"dg-publish":true,"permalink":"/1-cosmos/taylor-series/","created":"2025-01-22T11:17:14.008-05:00","updated":"2024-07-20T03:48:21.142-04:00"}
---

202407200348
Status: #idea
Tags: [[Calculus\|Calculus]]
State: #nascient
# Taylor Series

[【大学数学】テイラー展開の気持ち【解析学】 - YouTube](https://www.youtube.com/watch?v=qzd5iXKHkiU&list=PLDJfzGjtVLHnu5l4QEpWZiXdDKF5mFnhh)

The Taylor series is a smart and convenient way to approximate a function **near a point $a$**. It is typically written in the form
$$f(a) = f(a) + f'(a)(x-a)+\frac{1}{2!}f''(a)(x-a)^2+\frac{1}{3!}f'''(a)(x-a)^3+\ldots$$
The idea is that the more degrees you add to that polynomial approximation, the more accurate the approximation will be in the neighborhood. In most school cases, or practical applications, going to the 2nd or 3rd derivative will be more than enough.

**To Note**: It is amazing *because* of it's ability to turn any function, no matter how complex and tortuous, into a simple polynomial equation which is both much easier for a computer to compute, and easier for a human to visualize.

## MacLaurin Series
MacLaurin series are best scene as a special case of the [[1. Cosmos/Taylor Series\|Taylor series]], where the neighborhood we're trying to approximate around is 0. 
In essence it would look like this:
$$f(0) = f(0) + f'(0)(x)+\frac{1}{2!}f''(0)(x)^2+\frac{1}{3!}f'''(0)(x)^3+\ldots$$
It looks simpler (and it is). It's simply a Taylor series, with an a that is 0. Thus the $x-a$ simplifies to $x$, and we're looking for each function and derivative's height at 0.

## References
