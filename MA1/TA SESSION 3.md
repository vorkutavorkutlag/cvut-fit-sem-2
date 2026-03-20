
## Limits of Functions

Epsilon-Delta definitions.

We looked at limits of special functions $\mathbb{N} \rightarrow \mathbb{R}$ (sequence).
Now we want to generalize it for all functions.

We defined limit last time for sequences.
The number $L$ is the limit of the sequence $f:\mathbb{N} \rightarrow \mathbb{R}$ if:
$$(\forall \epsilon >0)(\exists N) n > N \implies |f(n)-L| < \epsilon$$

We'd like to extend this definition for functions $\mathbb{R} \rightarrow \mathbb{R}$ and look at different behaviors.
There are cases where a function is not defined at a point but we are still interested in the behavior. For example, $\frac{x^2-4}{x-2}$ is not defined at $x=2$ .
Simplifying, we get $f(x)=x+2$
Our function is not defined there, but we can say when we get really close to 2, we get really close to 4 as the output.

We formalize this via limit.
Continuing the example, we'll give a bit of intuition for why it works the way it does.
Around the point of non-definition, we have an interval of size $\delta$, we should be arbitrary $\epsilon$ close to value 4.

The Game: I want to be within $\epsilon$ of 4. We choose a corresponding $\delta$ s.t. it is satisfied.
The delta should depend on the epsilon, we cannot choose the epsilon.
Being within delta of x guarantees being within epsilon of y.

Note that $D(f) = \mathbb{R} \setminus \{2\}$
The point $2$ is not in the domain of $f$, but it is a cluster point.
Given every point, we can find any other point within that interval.
This is a punctured neighborhood.
Our point of interest should be a cluster point of the domain of the function.

We want to talk about the behavior of a function getting arbitrarily close to a value, so we require in general that it be a cluster point.

The cluster point is a cluster point for a set if for every open interval around that point there is some other point of the set in that open interval. Formally,
The point $a$ in $\mathbb{R}$ is a cluster point of the set $\mathbb{X} \subset \mathbb{R}$ $\iff$  for all $(a,b)$ to which $a$ belongs, there exists $x \in \mathbb{X}$ such that $x \in (a,b)$ and $x \neq a$ 

We have a set, and we are missing a point. It is a subset of $R$.
If for any open interval around this point, I can find some other point , such that that point is in the open interval and it is not equal to the (cluster) point, then it is a cluster point.

In general, every point is a cluster point of its own set.
Though a set may contain more points that do not belong it.

Infinities are cluster points.

For a limit to make sense, the point of interest must be either in my domain or a cluster point of my domain.

Being a cluster point is a requirement but it is not the only requirement for having a limit defined at that point.

Formally,
Let $f: \mathbb{R} \rightarrow \mathbb{R}$ and let $a \in D(f)$ or $a$ is a cluster point of $D(f)$ 
Let $L \in \mathbb{R}$. The value $L$ is the limit of $f$ at $a$ if $$(\forall \epsilon > 0) (\exists \delta > 0) ~ |x-a| < \delta ~\implies~|f(x) - L| < \epsilon$$
One step at a time.
You claim that $L$ is the limit of $f$ at $a$.
Someone gives you an arbitrary epsilon.
You can respond to them with another small positive number, delta, usually depending on epsilon;
Such that, whenever $x$ is within $\delta$ of $a$, you can show that $f$ is within $\epsilon$ of $L$.

In shorthand, we write $\lim~_{x \rightarrow a} f(x) = L$

The limit does not care what's happening at the actual cluster point.
For example, $f(x) = 1$ if $x \neq 0$ and $f(x) = 0$ if $x=0$ 
The limit of the function going to zero, is one!

Limits and function values don't need to agree.

If a point is within our domain it is trivially a cluster point.

...

Examples.
$\lim~_{x \rightarrow 2}~ 5x -4 = 6$
Let's work from the end to the back, scratch-work.
$|5x-4-6| < \epsilon \iff |5x-10| < \epsilon \iff 5|x-2| < \epsilon \iff |x-2| < \frac{\epsilon}{5}$
Then, we may choose $\delta = \frac{\epsilon}{5}$ and reverse the steps.
$|x-2| < \delta \implies |x-2| < \frac{\epsilon}{5} \implies ... \implies |5x-4-6| < \epsilon$ 
Now we have proven the implication, so we have proven the limit.


Theorems:
1. For all constants $C, a$, $\lim_{x \rightarrow a} C=C$ 
2. $\lim_{x \rightarrow a} Cf(x) = C \lim_{x \rightarrow a} f(x)$      // only works most of the time. $f(x)=\frac{1}{x}, C=0$ bad
3. $\lim~_{x \rightarrow a} f(x) = f(a)$ for all polynomials $f$
4. $\lim~_{x \rightarrow a} f(x) + g(x) = \lim~_{x \rightarrow a} f(x) + \lim~_{x \rightarrow a} g(x)$ // careful with definition, again!
5. $\lim~_{x \rightarrow a} f(x) \cdot g(x) = \lim~_{x \rightarrow a} f(x) \cdot \lim~_{x \rightarrow a} g(x)$
6. $\lim~_{x\rightarrow a} \frac{f(x)}{g(x)} = \frac{\lim~_{x\rightarrow a} f(x)}{\lim~_{x\rightarrow a} g(x)}$ // when denominator is not zero...

So now, for example, $\lim~_{x \rightarrow 2}x^3 + 4=12$ can be proven easily now.

Property 3. is called continuity. 
A function is called continuous if for all points in its domain correspond with the limits.
If the function is defined at a point, and the limit agrees with that value, that point is continuous.

The trigonometric functions are continuous in their domains.
$\sin, \cos, \tan$ are continuous on their domains.
Logarithms, exponential functions are continuous.

Another theorem, $\lim~_{x\rightarrow a} f(x) = L \iff \lim~_{x\rightarrow a^-} f(x) = L \land \lim~_{x\rightarrow a^+} f(x) = L$
