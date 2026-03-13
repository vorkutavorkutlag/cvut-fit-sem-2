
If $f(x) \in o(g(x))$ then $g(x) \not \in o(f(x))$.

#### Limits

When doing limits, we encounter indeterminate forms.

$lim~_{n \rightarrow +\infty} (5n^3-7n+1)$
We have infinity minus infinity, indeterminate.
To solve it, we could factor out the highest degree, and get 
$lim~_{n \rightarrow +\infty} n^3(5-\frac{7}{n^2}+\frac{1}{n^3})$ 
Then, we can look at the individual limits here.
Any non-zero number over infinity goes to zero. Thus, we have $5n^3$, which naturally, goes to $+\infty$.
Thus, $lim~_{n \rightarrow +\infty} (5n^3-7n+1) = +\infty$

L'Hopital is only useful for fractions. It works only for $\frac{0}{0},~ \frac{\pm \infty}{\pm \infty}$.

$lim~_{n \rightarrow +\infty} \frac{5n^3-7n+1}{n^2-3}$ 
We once again factor out the highest degree both the nominator and denominator.
$lim~_{n \rightarrow +\infty} \frac{n^3(5-\frac{7}{n^2}+\frac{1}{n^3})}{n^2(1-\frac{3}{n^2})} = lim~_{n \rightarrow +\infty} ~5n = +\infty$ 

Now, more interesting,
$lim~_{n \rightarrow +\infty} \frac{5n^3-7n+1}{n^3-3}$
Factoring out the highest degree,
$lim~_{n \rightarrow +\infty} \frac{n^3(5-\frac{7}{n^2} + \frac{1}{n^3})}{n^3(1-\frac{3}{n^2})} = \frac{5}{1} = 5$ 
The $n$'s cancel out entirely, leaving us with a real number.

In another example, $lim~_{n \rightarrow +\infty}~ \frac{5n^3-7n+1}{n^4-3}$ we will get zero. Following the same steps, we are left with $n$ in the denominator, and anything real over infinity is zero.

