
Locking in and studying limits again.
Really hard limits.
Difficult.
Challenging, even.

Definition of a sequence, limit of a sequence, and limits of a function.
Briefly, definition of limit of function:
$(\forall \varepsilon > 0) (\exists \delta > 0)~~~ |x-a| < \delta \implies |f(x) - L| < \varepsilon$ 
Conditions include, $a$ being a cluster point of domain of function.

Given a polynomial, the limit of it at a given point is the value of the polynomial.
This is due to continuity, which we will get to later.

Can decompose limit of product into product of limits if they are all defined.
Also works for limit of sums into sum of limits.
Similarly, limit of $\frac{f(x)}{g(x)}$ as long as both of them are defined.

We can simplify stuff like $\frac{x^2}{x}$ into $x$ and claim these are locally algebraically identical.

There exists bound $-x^2 \leq x^2\sin(\frac{1}{x}) \leq x^2$.
We need to write explicitly about the bound of oscillating functions.
Likewise, $-x \leq x\cos(\frac{1}{x^2}) \leq x$

Use squeeze theorem for $\frac{\sin(n)}{n}$ as $n \rightarrow \infty$.
We find wrappers for this, being $-\frac{1}{n}, ~\frac{1}{n}$.

...

Special elementary limits.
$\lim_{x \rightarrow 0}~\frac{\sin(x)}{x} = 1$
We are not expected to prove this whatsoever.
Still know that the limit is $1$.
Next semester we could do Taylor series.
Not L'Hopital though, as it is circular definition.

This is useful paired with $u$ substitutions.
For example, $\lim_{x \rightarrow 0} \frac{\sin(3x)}{x}$ 
$u = 3x, x = \frac{u}{3}, x \rightarrow 0 \iff u \rightarrow 0$
Then, $\lim_{x \rightarrow 0} \frac{\sin(3x)}{x} = \lim_{u \rightarrow 0} \frac{\sin(u)}{\frac{u}{3}} = 3$ 

Also, $\lim_{x \rightarrow 0} \frac{1-\cos(x)}{x} =0$
Also elementary, we are not expected to prove this.

Sine is roughly $x$, cosine is roughly $1$ near zero.
Then, $\lim_{x \rightarrow 0} \frac{\tan(x)}{x} = 1$

Using things that don't require these limits next semester we will use Taylor series.

Plenty of $u$-substitutions for now.

Can actually prove the cosine limit pretty easily using some algebraic manipulation and the $\sin^2(x)+\cos^2(x) = 1$ identity.

Remember the bounds of trig functions, even arcsine, arccosine, and arctangent.
Useful also for one-sided squeeze theorem.

For limit of two fractions, should get a common denominator.
Or apply sum rule. Whichever is easier.

...

The idea of continuity is that all functions are smooth, but some are smoother than others. The absolute value is smooth in a way we care about, but 'jumps' mean it is not.
It is continuous if we can draw it without lifting up our pen.

Let $a \in D(f)$. The function $f$ is said to be continuous at $a$ if $\lim_{x \rightarrow a} f(x) = f(a)$.
If the function is continuous at every point in its domain, it is said to be continuous.
All polynomials are continuous.
Sine, Cosine, Tangent are continuous. In their domains, of course...
$\frac{1}{x}$ is continuous, in its domain.

Derivative of absolute value of $x$ is not continuous.
Unless, if we poke a hole at the top, make $0$ undefined, then it is continuous.



