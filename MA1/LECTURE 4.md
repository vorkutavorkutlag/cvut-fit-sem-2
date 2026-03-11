### Limits of Sequences

##### Finite

We say that a real sequence $(a_n)_n \in N$ has a finite limit $\alpha \in R$ if and only if 
for every $\epsilon > 0$ there exists $n_0 \in R$ such that $a_n \in (\alpha - \epsilon, \alpha + \epsilon)$.

$$(\forall \epsilon > 0) ~ (\exists n_0 \in R) ~~~ a_n \in (\alpha - \epsilon, \alpha + \epsilon),~~ \forall n \in N ,~ n \geq n_0$$

Which is to say, that eventually, the sequences' values will be indistinguishable. 
This is a formal way to define the sequence **converging**.

The fact that a sequence has a limit is shortly written as $$lim_{n\rightarrow+ \infty} a_n = \alpha, ~~~lim~ a_n = \alpha, ~~~ a_n \rightarrow \alpha$$
Note that the only cluster point is at positive infinity for sequences, so that's where we can define the limit.

The following equations are equivalent in the definition of a finite limit.
- ($\forall \epsilon > 0) (\exists n_0 \in R) (\forall n \in N) (n \geq 0) ~~ a_n \in (\alpha - \epsilon, \alpha + \epsilon)$
- $(\forall \epsilon > 0) (\exists n_0 \in R) (\forall n \in N) (n \geq 0) ~~~~|a_n - \alpha| < \epsilon$  

For example, let's prove $lim_{n\rightarrow +\infty} \frac{1}{n} = 0$ 

$|a_n - 0| = |\frac{1}{n}| = \frac{1}{n} < \epsilon$ 
Then, we can use the definition, and define that for every possible epsilon, we can have $n_0 = \frac{1}{\epsilon}$. We have found the $n_0$, therefore the limit is correct.


##### Infinite

We say the limit of a real sequence $(a_n)_n \in N$ is $+\infty$, if and only if
for every $K \in R$ there exists $n_0 \in R$ such that $a_n \in (K, +\infty)$ for every $n \geq n_0$.
$$(\forall K \in R) (\exists n_0 \ni R)(\forall n \in N)(n \geq n_0) ~~ a_n \in (K, +\infty)$$
This is to say that $(a_n)_n$ **diverges**.
$$lim_{n\rightarrow +\infty} a_n = +\infty,~~~~lim~a_n = +\infty,~~~~a_n \rightarrow +\infty$$

For example,
$lim~_{n\rightarrow +\infty} ~n^4+2 = +\infty$ 
The sequence is only ever increasing, and the idea it is unbounded and diverges can be made formal through the definition.
$\forall K > 0, |n^4+2| = n^4+2 \geq K$ 
Then we can fine the $n_0$ that satisfies this.
If $K\geq 2$, $n_0 = \sqrt[4]{K-2}$ 
If $K < 2$, that statement is always true, so we may choose an arbitrary $n_0$. Even $n_0=0$!


We say a sequence $(a_n)_n \in N$ is
- **convergent** if the sequence has finite limit $\alpha \in R$. Then we say the sequence converges to $\alpha$.
- **divergent** if the sequence has an infinite limit $+\infty$ or $-\infty$. In this case we also say that the sequence diverges to $+\infty$ or $-\infty$.

It can also be neither. For example, look at any periodic function.
Or, a little less boring, $a_n = (-1)^n$

The limit of a sequence does not always exist. However, if it does, it is unique.

A sequence that does not have a limit is called **regular**.
"The limit does not exist, therefore it is divergent" is a false sentence.

By theorem, every real sequence has at most one limit.

To prove a limit is not correct, we need to find one element of the sequence, which is not the neighborhood. Essentially, we take the negation of the definition. $$(\exists \epsilon > 0) (\forall n_0 \in R) (\exists n \geq n_0) ~~ a_n \not \in (\alpha - \epsilon, \alpha + \epsilon)$$
#### Part II

We can exchange limits and modulus. This is by theorem.
For every real sequence. Then, $$lim~_{n \rightarrow +\infty} a_n = \alpha \iff lim~_{n\rightarrow +\infty} |a_n| = |a|$$

We can define algebraic operations on the extended real line.
We have some undefined expressions, like $-\infty +\infty$. Stating it zero is false. 
However, for $a \in \overline R$ we define:
- $a > -\infty: a + +\infty = +\infty + a = +\infty$
....I won't write the rest, it is pretty intuitive. The infinity, negative or positive, absorbs the $a$ like a black hole. Only outlier is multiplication, where $a$ may change the sign of the infinity.

Also,
- $\frac{1}{+\infty} = \frac{1}{-\infty} = 0$
- $a \neq 0$: $|\frac{a}{0}| = +\infty$

All these are indeterminate: $\pm \infty \mp \pm \infty, 0 \cdot \pm \infty, \frac{\pm \infty}{\pm \infty}, \frac{0}{0}$ 

Consider two sequences, $(a_n)_n := (-1)^n,~~~ (b_n)_n := (-1)^{n+1}$
The sum of the two sequences has a limit, despite the fact that the sequences on their own do not have limits.

Given that two sequences have limits, we can decompose the limit into two.
For example, $2n^3 + 4n$ can be decomposed into $2n^3$, and $4n$. We find their limits, and sum them up. Trivially, in this case, we have $+\infty + +\infty$, which gives $+\infty$.

In cases of indeterminate expressions, primarily with polynomials, we can factor the highest degree, and then every fraction's limit will be 0. Then, we are left with the coefficient of the highest degree polynomial as our limit's solution.

According to theorem,
$lim~_{n\rightarrow +\infty}~a^n$ is:
- if $a>1$: $+\infty$
- if $a=1$: 1
- if $|a| < 1$: 0
- if $a \leq -1$: $\not \exists$

We can take constants out of the limit.
For example, if we know $lim~_{n \rightarrow +\infty} ~a_n = \alpha$, then $lim~_{n \rightarrow +\infty} \sqrt[k]{a_n} = \sqrt[k]{\alpha}$ 
The proof involves the monotonicity of the root. 

Be careful of indeterminate expressions, we must look at the order of the infinity.
$\sqrt[n]{n}$ goes to $1$, yet $\sqrt[n]{n!}$ goes to $+\infty$
Be aware of: $1^{\pm \infty}, (\pm \infty)^0, 0^0$

...

The supermum and infimum of a sequence is the supermum and infimum of the image of the sequence.

By theorem, every monotonic sequence has a limit.
If the sequence is increasing and bounded from above, then the limit equals its supermum.
If the sequence is increasing and not bounded from above, then its limit equals $+\infty$.
If the sequence is decreasing and bounded from below, then its limit equals its infimum.
If th sequence is decreasing and not bounded from below, then its limit equals $-\infty$.
