Last week we saw the squeeze theorem for sequences.
Typically, we don't know the value of the limit $b_n$.
However, we could find two lower/upper bound sequences $a_n, c_n$ s.t.
$$(\exists n_0 \in \mathbb{N})(\forall n > n_0) ~~~ a_n \leq b_n \leq c_n$$
And $a_n = c_n$ , then $b_n = a_n = c_n$ 
We have the one sided squeeze theorem for infinities.

For example,
$\lim \frac{2-cos(n^2)}{\sqrt n}$
We have a finite amount divided by infinity, so most likely it will be zero.
We will use the squeeze theorem to make this idea formal.

$0 \leq \frac{|2-\cos(n^2)|}{\sqrt n} \leq \frac{2+|\cos(n^2)|}{\sqrt n} \leq \frac{3}{\sqrt n}$ 
When $n$ goes to infinity, RHS and LHS are both zero.
Then, $\lim_{n \rightarrow +\infty} \frac{2-cos(n^2)}{\sqrt n} = 0$

Usually when we want to prove the limit is zero, we can put absolute value.

Another example,
$\lim n^2-\arcsin(\frac{1}{n})$
Arcsine is bounded by $\pm \frac{\pi}{2}$ 
$n^2 - \arcsin(\frac{1}{n}) \geq n^2 - \frac{\pi}{2}$ 
Infinity plus or minus a constant is still infinity.
Then, the original sequence has limit infinity.

Remember theorem about properties of limit of exponent. $\lim_{n \rightarrow +\infty} a^n$ 
- $|a| < 1 \implies 0$
- $a = 1 \implies 1$
- $a > 1 \implies +\infty$
- $a < -1 \implies$ Does not exist

Last week we also proved that if we can find two disagreeing subsequences, then the original limit is undefined.


Heine's theorem claims all the limit theorems we found for sequences apply also for real functions.
A limit of a sequence, function is unique.

Squeeze theorem may be applied locally to real functions.

The limit of continuous functions at a defined point is the value of that point.

For $|x| < \frac{\pi}{2}$, $0 \leq |\sin(x)| \leq |x|$ 

When functions have different domains and images, they are not equal.
However, they can be locally identical in a neighborhood.
That can be used to compute the limit after simplifications.

Quadratic bound on exponentiation: $1+x-x^2 < e^x < 1+x+x^2$

