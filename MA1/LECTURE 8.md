# Continuity

Let $f$ be a real function of a real variable. Let $a \in D(f)$.
-  $f$ is continuous at the point $a \iff \lim_{x \to a} f(x) = f(a)$ 
- $f$ is continuous at the point $a$ from the right $\iff \lim_{x \to a^+} f(x) = f(a)$
- $f$ is continuous at the point $a$ from the left $\iff \lim_{x \to a^-} f(x) = f(a)$

By theorem, a function $f$ is continuous at a point $a \in D(f) \iff$ it is continuous at that point from the left and from the right.

By theorem, If $f,g$ are continuous at $a \in D(f) \cap D(g)$, then $f+g, f-g, f \cdot g$ are continuous at $a$, and so is $\frac{f}{g}$ if $g(a) \neq 0$.
The same applies in the composition of continuous functions.

By theorem, a function is continuous on an interval $\iff$ it is continuous at every point on the interval.

By definition, if the domain of a function can be divided to continuous intervals, then the function itself is piecewise continuous.

The previous theorem about continuity of sums, differences, multiplication and quotient works as expected on continuous intervals too.
Equivalently, the previous theorem about composition being continuous works as expected on continuous intervals too.

Since polynomials are constructed as sums and products, it is satisfied by the previous theorem. Equally, quotients with polynomials too.

Theorem about concatenating continuous intervals to state that a larger interval is continuous is trivial.

Proving continuity of sine, cosine is derived by their limit being zero, and the rest of the trig functions (such as $\tan$) can be used as composition, quotient, etc. of sine, cosine.

Proving continuity on $e^x$ needs that $lim_{x \rightarrow 0} e^x = 1 = e^0$
Then, $\lim_{x \rightarrow a} e^x = \lim_{x \to a} e^a e^{x-a} = e^a \lim_{x \to a} e^{x-a} = e^a$.
Similarly, $a^x$ is always exponential, proven with $e^{xlna}$.

Intermediate Value Theorem states:
Given continuous function $f$ on closed interval $[a,b]$, $\gamma \in R$, and $f(a) < \gamma < f(b)$, then there exists a point $c \in (a,b)$ s.t. $f(c) = \gamma$.

We may prove this constructively by using something similar to binary searching.
It is possible to binary search as the interval is continuous.
That is useful for methods such as finding roots for polynomials, and Newtonian Iteration. The **bisection method** can be used to solve $f(x) = 0$.
