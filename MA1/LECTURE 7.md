
Proved limit of Euler's number using logarithm properties.

Fundamental limit: $\lim_{x \rightarrow 0} \frac{e^x-1}{x} = 1$

#### Asymptotic Dominance of infinities

When we get an indeterminate expression with infinities, we don't know which quantity is going to infinity faster, so we cannot compute it. However, due to a theorem, in many cases, we can compare the infinities.

The ratio test for sequences.
Assume a sequence (which with Heine's theorem we will convert to functions), take the limit of the quotient $\frac{|a_{n+1}|}{a_n}$.
If that limit is smaller than 1, then the limit of the sequence at infinity is zero.
Otherwise, in absolute value, the sequence goes to positive infinity.
If they are equal then we cannot say anything, this test fails.

We can use it for the limit, for example, $\lim_{n \rightarrow +\infty} \frac{n}{e^n}$
Then, we say $a_n = \frac{n}{e^n}$. No need for absolute value as it is positive.

We now also have theorem:
$$\lim_{x \rightarrow a} \frac{|f(x)|}{|g(x)|} = 0 \iff f \in o(g)$$ $f$ will be asymptotically smaller than $g$.
We can find the definition for little $o$ using the definition of the limit in this case.

We can also prove $\lim_{n \rightarrow +\infty} \frac{\ln(n)}{n} = 0$ . Proof is long and technical, but it simply uses the definition of the limit.
Then, $\ln(n) \in o(n)$

Hierarchy:
$$log_a n \ll n^a \ll b^n \ll n! \ll n^n$$

If the limit of the quotient is equal to a finite number, then by the definition of limit, we can find a neighborhood of that point such that big O is satisfied. 
$\lim_{x \rightarrow a} \frac{|f(x)|}{|g(x)|} = L \geq 0 \implies f\in O(g)$ 

...

...

We will be doing limits by formulas:
- $\lim_{x \rightarrow 0} \frac{\sin(x)}{x}=1$
- $\lim_{x \rightarrow 0} \frac{\ln(1+x)}{x}=1$
- $\lim_{x \rightarrow 0} \frac{e^x-1}{x}=1$

As we discussed in the TA session, we can substitute anything in place of any of these $x$'s and they will still apply. For example, $\frac{\sin(5x)}{x}$. or $\frac{e^x}{x+1}$

`3.35)` $\lim_{x \to 0} \frac{\sin(2x)}{\sin(3x)} = \lim_{x \to 0} \frac{\sin(2x)}{\sin(3x)} \cdot \frac{3x}{2x} \cdot \frac{2}{3} = \frac{2}{3}$ 
We do this thanks to $\frac{x}{\sin(x)} = \frac{1}{\frac{\sin(x)}{x}} \to 1$

`3.41)` $\lim_{x \to 0} \frac{e^{3x}-1}{x} = \lim_{x \to 0} \frac{e^{3x}-1}{x} \cdot \frac{3}{3} = \frac{e^{3x}-1}{3x} \cdot 3 = 3$
Same trick as earlier more or less.

`3.42)` $\lim_{x \to 0} \frac{e^{3x}-e^{4x}}{x} = \lim_{x \to 0} \frac{e^{3x}-1}{x} - \frac{e^{4x}-1}{x} = 3-4 = -1$

We can also derive $\lim_{x \to 0} \frac{\sin(x^2)}{x^2} = 1$ by substitution.
They both decrease/increase at the same speed, so the formula holds.

`3.53.d)` $\lim_{x \to 0} \frac{e^{x^2} - \cos(x)}{x^2} = \lim_{x \to 0} \frac{e^{x^2}-1+1-\cos(x)}{x^2} = \lim_{x \to 0} \frac{e^{x^2}-1}{x^2} + \frac{1-\cos(x)}{x^2} \cdot \frac{1+\cos(x)}{1+\cos(x)} =$
$= \lim_{x \to 0} 1 + \frac{1-\cos^2(x)}{x^2} \cdot \frac{1}{1+\cos(x)} = 1 + 1 \cdot \frac{1}{2} = \frac{3}{2}$ 
Note that we use the trigonometric identity: $1=\sin^2(x)+\cos^2(x)$