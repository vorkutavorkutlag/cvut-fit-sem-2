
Starting with exercise.
`1.17.c)` $f(x) = \arcsin(x^4-1)$

Note that arcsine is the inverse function of sine. Its domain is $[-1, 1]$.
Note that sine is not injective, as it is periodic, so it is not an exact inverse.
How can we speak of the inverse then? What we can do, is restrict ourselves to the largest injective set. The interval, $[-\frac{\pi}{2}, \frac{\pi}{2}]$. Also image of arcsine.

This is a composition of two functions. One function $h(x)$ is arcsine, the other function $g(x)$ is the 4th degree polynomial.
Then, $g(h(x)) = \arcsin^4(x)$  and $h(g(x)) = \arcsin(x^4-1)$

The only function that can "create problems" for the domain is arcsine, defined in between $-1$ and $1$.
Then, we need $x^4-1$ to be in the interval $[-1, 1]$.
$-1 \leq x^4 -1 \leq 1$. Let $u = x^2$
$-1 \leq u^2-1 \leq 1 \implies 0 \leq u^2 \leq 2 \implies u^2 \leq 2 \implies x^4 \leq 2 \implies -\sqrt[4]{2} \leq x \leq \sqrt[4]{2}$
Note, we got rid of the zero since the expression is always $\geq 0$.

`1.17.a)` $f(x) = \arccos(x^2-1)$
Same deal. Domain of arccosine is also $[-1, 1]$, so we ask then $-1 \leq x^2-1 \leq 1$.
$\implies 0 \leq x^2 \leq 2 \implies x^2 \leq 2 \implies -\sqrt2\leq x \leq \sqrt2$ 

We also have $tan(x)$ or $tg(x)$, defined $\tan(x) = \frac{\sin x}{\cos x}$
Sine and cosine have period $2\pi$, and tangent has period $\pi$.
For the inverse, we restrict tangent on **open** interval $(-\frac{\pi}{2}, \frac{\pi}{2})$
In that interval, we map to all real numbers.
Then, the inverse, arctangent, maps $R \rightarrow (-\frac{\pi}{2}, \frac{\pi}{2})$.

`1.17.h)` $f(x) = \sqrt{\arctan x - \frac{\pi}{4}}$ 
Since arctangent is defined for all real numbers, we only need to worry about condition $\arctan x - \frac{\pi}{4} \geq 0 \implies \arctan x \geq \frac{\pi}{4}$
Then, we can apply tangents to both sides. We get $x \geq 1$.
Note, we can only, only do this because tangent is increasing!!
As in, we have a guarantee that $x \geq y \iff \tan x \geq \tan y$
(as long as they are in the same period...)
Finally, $x \in [1, +\infty)$ 

We also have $\cot x := \frac{\cos x}{\sin x}$, as in $\frac{1}{\tan x}$ 
Domain is all real numbers but $x \neq k\pi$, as opposed to tangent's $x \neq \frac{\pi}{2} + k\pi$
Additionally, it is strictly decreasing in every period!
Then, in-case of inequality $arccot(x) \geq \frac{\pi}{4}$, we get $x \leq 1$ 

It is useful to remember the graphs.

### Part II

#### Sequences

By definition, a **real sequence** is a mapping from $N \rightarrow R$
Usually, we denote them by lowercase Latin letters. Additionally, instead of $a(n)$, we write $a_n$ as the n-th member of the sequence.
We will also denoted all elements in sequence  as $(a_n)_{n \in N}, ~~~ (a_n)^{+\infty}_{n=1}, ~~~ (a_n)$ 

Note that we can renumerate the sequence, for example, for sequence $a_n = \sqrt{n-5}$ , we should write $(a_n)_{n \in J}$ where $J$ would be the appropriate domain.

Consider the sequence $a_n = (-1)^n$, then the image set $(a_n) = \{-1, 1\}$
The plot of a sequence is a set of points.

This is an explicitly defined sequence. However, there could also be recursively defined sequences. Similar to weak/strong induction in DML.
For example, $a_1 = 1$, and $a_{n+1} = \frac{a_n^2 + 2}{2a_n}$

Some sequences can only be defined recursively.

An arithmetic sequence with parameters $a, d$ s.t. $a_1 = a, ~~~ a_{n+1} = a_n + d$
All elements of the sequence are at a fixed distance $d$.
The explicit formula is $a_n = a+d(n-1)$

A geometric sequence with parameters $a, q$ s.t. $a_1 = a, ~~~ a_{n+1} = qa_n$
The explicit formula is $a_n = aq^{n-1}$

The factorial: $a_1 = 1, ~~~a_{n+1} = (n+1)a_n$, has the explicit formula $n!$ 

We say a sequence is:
- constant $\iff a_n = a_m$ for every $n,m \in N$
- injective $\iff$ $a_n = a_m \implies n_m$ 
- bounded from above $\iff$ its image $(a_n)$ is bounded from above.
- bounded from below $\iff$ its image $(a_n)$ is bounded from below.
- bounded $\iff$ its image is bounded from above and from below.
- increasing $\iff$ $a_n \leq a_{n+1}$ for every $n \in N$.
- decreasing $\iff$ $a_n \geq a_{n+1}$ for every $n \in N$.
- strictly increasing $\iff$ $a_n < a_{n+1}$ for every $n \in N$.
- strictly decreasing $\iff$ $a_n > a_{n+1}$ for every $n \in N$.
- (strictly) monotonic $\iff$ is (strictly) increasing or (strictly) decreasing.

A **tail** or say $k-1$ tail of a sequence, is all the members of the sequence except the first $k$.

A sequence is called eventually (strictly) increasing/decreasing if there exists a tail for that sequence which is (strictly) increasing/decreasing.

We can speak of Big O and Little O notations for sequences for $n \rightarrow \infty$.

Let $(a_n)_{n \in N}$ be a real sequence and $(n_k)_{k \in N}$ be a strictly increasing sequence of natural numbers. Then we say $(a_{n_k})_{k \in N}$ is a **subsequence**.


...

Split the absolute value of the sum into the sum of absolute values for proofs, for example of Big O and Little O.