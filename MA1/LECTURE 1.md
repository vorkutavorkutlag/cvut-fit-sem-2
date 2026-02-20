# Real Numbers

First, revision of previous topics.
Side-note, $\exists !$ is shorthand for "there exists just one".
Recall, the order in a set does not matter.
Two sets are equal when $A \subseteq B \land B \subseteq  A$.

The set of all natural numbers is denoted by $N$ $$N = \{1,2,3,...\}$$
The set of all integer numbers is denoted by $Z$ $$N = \{...,-3,-2,-1,01,2,3,...\}$$
The set of all rational numbers is denoted by $Q$ 
$$Q = \{\frac{p}{q} : p \in Z, q \in N\}$$
(p and q are coprime).

The set of all real numbers is denoted by $R$
$$N \subset Z \subset Q \subset R$$
A set A is finite if it has a bijection to a finite set, usually the first n natural numbers. - implying they have the same, finite cardinality. The sets above are infinite.

Natural numbers are closed by addition, but the difference is not closed. 
The set of all possible finite or infinite decimal expansions
gives the set of real numbers, including $\pi, ~e, \sqrt 2$ and so on.
Real numbers are therefore complete. They do not have "gaps". They satisfy the axiom of completeness.

###### Axiom of Completeness
Let $A$ and $B$ be two nonempty subsets of $R$ such that $a \leq b$ for every $a \in A, ~ b \in B$.
Then, there always exists $c \in R$ such that $a \leq c \leq b$ .

$(R, +, \cdot)$ forms an ordered field. Complex numbers on the other are not an ordered field.
There is no ordering relation/property, it is not trivial, and real numbers have it.

Side-note... Complex numbers cannot be defined by lesser/greater, but some completeness property can be stated through the distance $|z_1 - z_2|$, thus to say that they are incomplete would be wrong.

$Q$ is not complete as it does not have solutions for irrationals such as $\sqrt 2$ 
There is no rational number that you can put between $a, b$ in the completeness axiom to fill in the gap.
Editor's note: What about the equation $x^2 = -1$ ? Same problem as $x^2 = 2$ for $Q$ ?
Outcome: Proof for completeness is different.

Properties of real numbers that are absent in rational numbers, is not only completeness... Real numbers are infinite, and there are many more real numbers than rational numbers. There is a bijective mapping from rational numbers to natural numbers, meaning they have the same cardinality.
Editor's note: Is it $N$ or $N^2$ for the bijection?
Outcome: $N$ has a bijection with $N^2$, so by composition $Q$ has bijection with $N$ 
There is no systematic way to count real numbers, they are non-countable. A higher order infinite than that of rational numbers.

Bounded sets are called bounded from above if there exists a real constant such as the inequality $x \leq k$ holds for every element in that set and $k$ is the upper bound.
Bounded sets are called bounded from below if there exists a real constant such as the inequality $k \leq x$ holds for every element in that set and $k$ is the lower bound.
A set is called bounded if the set is bounded from both sides, i.e. from above & below.
All these sets are subsets of real numbers.
The equality in these relations does not matter. As in, $x < k$ and $k < x$ are still upper bounded and lower bounded sets respectively.

$\frac{1}{x}$ for $x \in (0,1)$ is not upper bounded, surprisingly.
$0 < x < 1$ implies $\frac{1}{x} > 1$ , there is a lower bound but not an upper bound.
Editor's note: I guess it's because the limit $x \rightarrow 0$ of $\frac{1}{x} \rightarrow \infty$  so it's $1 < \frac{1}{x} < \infty$ 


A subset of real numbers is as interval if for every two elements, every intermediate value is also in the set.
$\forall x,z \in I, \forall y \in R, ~ x < y < z \implies y \in I$

Bounded intervals
$(a,b) = \{x \in R : a < x < b\}$ open interval
$[a,b]= \{x \in R : a \leq x \leq b\}$ closed interval
$[a,b) = \{x \in R : a \leq x < b\}$ left-closed right-open interval
$(a,b] = \{x \in R : a < x \leq b\}$ left-open right-closed interval

Unbounded intervals 
$(a, +\infty) = \{x \in R : a < x\}$ open interval
$(-\infty, b) = \{x \in R : x < b\}$ open interval
$[a, +\infty) = \{x \in R: x < b\}$ left-closed right-open interval
$(-\infty, b] = \{x \in R : x \leq b\}$ left-open right-closed interval

Real numbers may be expressed as interval $(-\infty, +\infty)$
The maximum of a set is the element in a set that is greater than or equal to than all other elements in the set.
The minimum of a set is the element in a set that is lesser than or equal to than all other elements in the set.

For example, $(-5, 0]$ has a maximum, but not a minimum as it is open below.
Maximum and Minimum are trivially unique. 
Some sets have no maximum nor minimum.

A supermum of a set is denoted by $\sup M$ is its smallest upper bound.
an infimum of a set is denoted by $\inf M$ is its biggest lower bound.
As consequence of the axiom of completeness, every set bounded from above has an infimum, and every set bounded from below has an infimum.

For example, $(-\infty, 2)$ has no supermum, and its infimum is 2.

Characteristics properties:
A finite number $c$ is a supremum of $M$ $\iff$
1. $\forall x \in M, x \leq c$
2. $\forall \epsilon > 0, M \cap (c - \epsilon, c] \neq \emptyset$
The latter part meaning we may find an element in that cut of the interval.

A finite number $c$ is a infimum of $M$ $\iff$
1. $\forall x \in M, x \geq c$
2. $\forall \epsilon > 0, M \cap [c, c + \epsilon) \neq \emptyset$

A proposition for a well-order property of a finite set.
A finite subset of rel numbers has maximum and minimum. It is a consequence of the axiom of ordering.

Corollary of well-order property of integer numbers.
If a set is bounded above is a subset of integer numbers, then it has maximum. If a set is bounded from below is a subset of integer numbers, it has a minimum.

Now let's look at "Machine Numbers".
It has to do with what we work with in the real world. Since we cannot implement infinity and such...
First let's recall that the sets mentioned are infinite and countable, then $R$ is uncountable infinite and complete.
Since computer memory is limited, it is clear that none of these sets can be exactly represented in the computer.
You cannot represent all real numbers either, as they are complete, i.e. between every two real numbers there is another real number.

Integers can be easily represented in a binary system.
Thus, rational numbers can be stored as two integers (nominator, denominator).
However, there is the problem of not being able to represent overly large values.

Finite memory.
Even if we do not limit $n$ for arbitrary precision, then for most values we exhaust the memory of our machines. So in reality we are covering a "large" subset of $Z$ with 64-bit signed integers.

Real numbers are represented via floating point representation.
A floating point is specified by:
1. a base, also called radix $b$, which is either binary or decimal in IEEE 754.
2. A precision $p$
3. An exponent range from `emin` to `emax`

$x = (-1)^s \times m \times b^c$ 
Where $m$ is the mantissa and $c$ is the exponent.
Through some specific and nonsensical values, we have sentinels for positive, negative infinities and NaN. Check lecture slides for exact values (Page 27).

Thus with a computer we use instead of the precise value of a real number some approximation by a rational number. This yields some issues.

For example, the sum $\sum_{k=1}^n \frac{1}{k}$ is non convergent, yet it converges when calculating in a computer, since the fraction's value will be equivalent to zero in the computer.
Which is wrong.
...As opposed to other sums which converge, in which the computer will be correct.


##### Second Part
The Cartesian product $A \times B$ of two sets is the set of all ordered pairs $(x,y)$ where $x \in A, y \in B$. And for all x, y: $(x,y) \in A \times B$
Cartesian products are generally not commutative. 
The cartesian plane is just $R \times R = R^2$.

A mapping $f$ from $A \rightarrow B$ is defined as a subset of the Cartesian product between two sets such that for every $a \in A$ there is at most one $b \in B$ such that $(a,b) \in f$ 
If we call $a, b$ input and output respectively, then we can say that for every input the mapping produces at most one output.
We may also write $f(a) = b$ and we simply refer to $f$ as to a function.

Sets A, B are called domain and codomain of $f$ respectively. Denoted $D(f)$.
The set of all values of $f$ is called the image set, or shortly, the image of $f$ and 
denoted by $H(f)$ also called range. Additionally, $H(f) \subseteq B$ .

Two mappings are equal if they are equal as sets. Equivalent $$f =g \iff f(x) = g(x) \forall x \in A$$
When we want to restrict a mapping $f$, say we have mapping from $A \rightarrow B$ we want to restrict it to $M \subset A$. Then consider mapping g: $M \rightarrow B$. It is called the restriction of $f$ on $M$ if $\forall x \in M : g(x) = f(x)$ 
$f(M) = \{f(x) : x \in M \cap D(f)\}$ is called the image of the set $M$ under the mapping $f$.
We are not actually applying the mapping on the set, simply a notation.
Given $N \subseteq B$, $f^{-1}(N) = \{x \in A : \exists y \in N : f(x) = y\}$ is called the preimage of the set $N$ under the mapping $f$.

For a mapping, we define the inverse mapping, if it exists, $f^{-1} : H(f) \rightarrow A$ s.t. $$f^{-1} = \{(b,a) \in B \times A : (a,b) \in f\}$$
A real function is often described explicitly, i.e. by a formula which expresses in arithmetic terms how the output depends on the input.
Real functions include $B \subseteq R$, but $A$ is not restricted, e.g. can be natural too.
Whenever $A \subseteq R$, the function is a real variable real function.

The plot of the function is the set of all ordered pairs $\{(x,y) : x \in D(f), y = f(x) \}$ 
The plot of the sequence is the set of all ordered pairs. Graphically, a bunch of dots.

The (natural) domain and codomain of a function of real variables... Since the function is given usually as a formula, well-defined everywhere or not. $\frac{\sqrt x}{x-1}$ is not well defined for every variable. Thus natural domain $D(f) = [0,1) \cup (1, +\infty)$ $\subset R$ ######