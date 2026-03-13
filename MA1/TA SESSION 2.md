
### Limits

Formal definitions, proofs, etc.

Last week we saw sequences.
A real sequence is a mapping $f: N \rightarrow R$.
We have countably many naturals, mapping to real numbers.

We can also express them with explicit notation $(3,4,5,6, ...)$. Pattern is clear.
We can write this explicitly as function $f(n)=n$.

If we consider $(1, \frac{1}{4}, \frac{1}{9}...)$ The formula then is $f(n)=\frac{1}{n}$.

We want to consider the eventual behavior of such sequences for large $n$.

 
Let $L \in R$ and $f: N \rightarrow R$ be a real valued sequence.
We say $L$ is the **limit** of $f$ if and only if$$(\forall \epsilon>0)(\exists N \in R) n > N \implies |f(n) - L| < \epsilon$$
If for any such positive big number $\epsilon$, we can find another number $N$, such that for any index larger than $N$, the sequence is within $\epsilon$ of our limiting value.
You can view it as  game. Epsilon is given to you, and for any such epsilon, no matter how small, we can respond for some big $N$, that for every $n > N$, we are within that limit.

Consider  the sequence $f(n) = \frac{1}{n}$.
We are going to do some simplification.
$|\frac{1}{n} - 0| < \epsilon \implies |\frac{1}{n}| < \epsilon \implies \frac{1}{n} < \epsilon \implies n > \frac{1}{\epsilon}$ 
This is not part of the proof, this is just a demonstration of simplification.
Scratchwork.
Note that we can choose the $n$. So, let $N=\frac{1}{\epsilon}$.
Suppose $n>N = \frac{1}{\epsilon} \implies \frac{1}{n} < \epsilon \implies |\frac{1}{n} - 0| < \epsilon$ 
Proven.

Show $\lim~_{n \rightarrow \infty} \frac{1}{n^2} = 0$.
We want to get $n > ...$
$|\frac{1}{n^2}-0| < \epsilon \implies |\frac{1}{n^2}| < \epsilon \implies \frac{1}{n^2} < \epsilon \implies n^2 > \frac{1}{\epsilon} \implies n > \frac{1}{\sqrt \epsilon}$   
Scratchwork.
Now, Let $N = \frac{1}{\sqrt \epsilon}$
Assume: $n > \frac{1}{\sqrt \epsilon}$ 
Then we want to reverse engineer into our scratch work. Backpedal.
$n > \frac{1}{\sqrt \epsilon} \implies n^2 > \frac{1}{\epsilon} \implies \epsilon n^2 > 1 \implies \epsilon > \frac{1}{n^2} \implies \epsilon < |\frac{1}{n^2} - 0|$ 

When a sequence has a limit, we say that the sequence converges into $L$.
Sometimes sequences can diverge, we tend to infinity or negative infinity.
Sometimes, sequences do not have limits.
For example, periodic functions - they cannot satisfy our definition.

Let us negate the statement .
$\neg((\forall \epsilon>0)(\exists N \in R) n > N \implies |f(n) - L| < \epsilon)) \equiv$
$(\exists \epsilon > 0)(\forall N) (n > N) \land (|f(n)-L| \geq \epsilon)$ 

We can be bigger than your claimed $N$ and we still do not get in the limit of epsilon.
If we can satisfy this with some value of epsilon, then we have shown that $L$ is not the limit.

For sine, for example, we can assume it has a limit $L$, and then contradict it.

...

This gets more interesting when we talk about more than one sequence.
We can calculate the limit of sums of sequences.
A sum of sequences, $(f+g): N \rightarrow R$
We can calculate the limit of via $lim~_{n \rightarrow \infty} (f(n) + g(n))$
If the limit of $f$ exists in finite, and the limit of $g$ exists and is finite, then the limit of the sum is $f+g$.

The limit of a constant is a constant.

Limit of products is the product of the limits once more. Always simplify in the product, and make sure it is finite.

...

When we cannot split it and we cannot simplify...
For example $lim~_{n \rightarrow \infty} sin^2(n) \cdot \frac{1}{n}$
Looking at the upper limit and bottom limit of sine squared, we see...
$\frac{0}{n} \leq sin^2(n) \cdot \frac{1}{n} \leq \frac{1}{n}$
We can use the squeeze theorem, like, sandwiching this expression between two equal values...
Taking the limits of both of them, we get $0 \leq sin^2(n) \cdot \frac{1}{n} \leq 0$
Thus, $lim~_{n \rightarrow \infty} sin^2(n) \cdot \frac{1}{n} = 0$

Let $f,g,h$ be real sequences.
If for $n>N$, $g(n) \leq h(n) \leq f(n)$, and $lim~_{n \rightarrow \infty} g(n) = lim~_{n \rightarrow \infty} f(n) = L$, then $lim~_{n \rightarrow \infty} h(n) = L$.

