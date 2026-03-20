
Every monotonic sequence has a limit.
Supremum, Infinimum, may correspond to the limits...

The sequence of Euler's number is strictly increasing, and is bounded from above. Then, the supremum of the sequence is the limit, being the Euler number.

To prove a sequence is eventually decreasing if $(\forall n) ~a_{n+1} \leq a_n$  
We can use this to prove for sequences like $a_n = \frac{1}{2n-5}$
We must also pay attention to the signs when proving.
Emphasis on the eventually. For $n=2, 3$ it is increasing, actually

To check if a sequence is bounded,
- Above: $(\exists k \in R) (\forall n \in N) a_n \leq k$
- Below: $(\exists k \in R) (\forall n \in N) a_n \geq k$

Sometime's it's easier to find the limit, and then say whether it is bounded or not bounded respectively.

For decreasing:
- Not bounded from below = Limit = $-\infty$
- Bounded from below = Limit = Infinimum

The lower bound sometimes isn't equal to the limit, it just has to be the smallest value in the entire sequence.

Every sequence has a monotonic subsequence.
All subsequences of a sequence have to be infinite.

Bolzano-Weiestrass theorem claims for a bounded real sequence, it has a convergent subsequence. 

Constant sequences are monotonic, they are both increasing and decreasing.

If a sequence is convergent, then it is bounded.

If a sequence diverges to $\infty$ it is unbounded from above.
If a sequence diverges to $-\infty$ it is unbounded from below.

A **Cauchy sequence**  is a sequence which for every positive real number $\epsilon$ there exists a positive integer $N$ such that for all $m,n \in \mathbb{N}, ~~ m > N, ~~ n > N$ it holds $|a_n-a_m| < \epsilon$
$$(\forall \epsilon > 0) (\exists  N)(\forall m,n \in \mathbb{N}) ~~m>N \land n >N ~\implies~ |a_n - a_m| < \epsilon$$
We can get arbitrarily close to some epsilon.
A real sequence is a Cauchy sequence $\iff$ it converges

// That can be used to define Cauchy completeness. Also fixes the question of whether 
// Complex numbers are complete or not.

If a sequence has a limit, every subsequence must have the same limit.

If two subsequences have different limits, then the supersequence has no limit.

For subsequences, even and odd works 90% of the time. Then $n=3k, 4k,$ etc.

...

For choosing a subsequence, we must assign the index to a strictly increasing sequence. Meaning, we cannot say, let $n=0k$, for example...

We can prove $a_n=sin(\frac{\pi}{4}n)$ does not have a limit by showing that its subsequences have two different limits.
For example, $n=4k$, $a_{4k} = sin(\pi k) = 0$ the limit of which is $0$.
Then, $n=8k+2, a_{8k+2} = sin(2k\pi + \frac{\pi}{2}) = sin(\frac{\pi}{2}) = 1$
The limits are not the same therefore the limit of the supersequence does not exist.

// If we have two subsequences which "complete" the subsequence, 
// and they have the same limit, does it correspond to the supersequence's limit?

...

###### Limit of a function
Let $f$ be a real function and let $a \in \overline{\mathbb{R}}$ be a cluster point of $D(f)$.
We say that $c \in \overline{\mathbb{R}}$ is the limit of the function $f$ at point $a$ if for every $\epsilon > 0$, there exists $\delta > 0$ such that for every $x\in D(f) \cap U_a(\delta) \setminus \{a\}$  the value $f(x)$ belongs to neighborhood $c$ of size epsilon $U_c(\epsilon)$.
Then we denote $lim_{x \rightarrow a} f(x) = c$ 

If $a,c$ are finite, then the limit is equivalent to: $$(\forall \epsilon > 0) (\exists \delta > 0)(\forall x \in D(f))~~~(0 <|x-a| < \delta \implies |f(x) - c|<\epsilon )$$
And the last distance between the function and $c$ means it is in the neighborhood of $c$ of size $\epsilon$.

Limit of identity at a given point is that point. Limit of a constant is always the constant.

Given every positive epsilon, the task is to find the delta, such that the implication is true.

The limit may exist even if the function is not defined at the point.

Even if the function is defined at a point, the limit of that point may not correspond to the image of the function.
If we look at $sgn(x^2)$ , its limit at $x\rightarrow0$ is $1$. That is because we exclude zero itself from the neighborhood. 

...

There exist also left side and right side limits, where we approach the limit only from a predetermined side. What changes in the definition is the neighborhood.
$U_a(\delta) \setminus \{a\}$ becomes  $U_a^-(\delta) \setminus \{a\}$ and $U_a^+(\delta) \setminus \{a\}$ respectively.

If left-side and right-side limits don't match, then the limit itself is undefined.

...

Computation of limits can be done using theorems, as the definition may be a little complicated to prove each time.
Almost all things we know about limits of sequences can be applied to functions.

We may use the sign of the sequence to correspond to the sign of the limit.
A positive limit implies it is eventually positive and vice versa.

Given two sequences, and one sequence's limit is greater than the other's, then the sequence itself is eventually greater then the other sequence.

...

Squeeze theorem.... 

...

Heine's theorem...
Sometimes it is taken as the definition as the limit of a function.
Given a function, and a cluster point of the function, let there be some sequence whose members belong to the function's domain without the cluster point that has a limit equal to the the cluster point.
Then, something something, the limits are equal. Ughh!

...

Theorem about algebraic operations with limits of functions...

