
The definition of a total mapping is the same as a mapping, except for every $a \in A$ there exists exactly on $b \in B$. 

For mappings $f: A \rightarrow B$ and $g: C \rightarrow E$ we can consider the composition of the two mappings to be $g \circ f: A \rightarrow E$ defined on the set $$D(g \circ f) = A \cap f^{-1}(C) = \{a \in A : f(a) \in C\}$$
The intersection between the original domain, A, with the preimage of set C.

![[Pasted image 20260225101101.png]]

For a mapping $f: A \rightarrow B$ we define the **inverse mapping**, if it exists, as the mapping $f^{-1}: H(f) \rightarrow A$ such that $$f^{-1} = \{(b,a) \in B \times A : (a,b) \in F\}$$ If the inverse mapping exists, we say that $f$ is invertible.

If $g$ is the inverse mapping of $f$ then $\forall x \in D(f), y \in H(f)$  $$y = f(x) \iff x = g(y)$$
Additionally, if we compose a mapping with the inverse mapping, we get the identity mapping, that maps each element to itself.

A mapping is invertible in practice when it is injective and surjective $\rightarrow$ bijective.

Let's define these.
Let $A,B \subset R$ and $f: A \rightarrow B$ 

**Injective** (one to one); for every pair $x, y \in D(f)$ when $x \neq y$ then also $f(x) \neq f(y)$
$$(\forall x,y \in D(f)) f(x) = f(y) \implies (x =y)$$
**Surjective** (important to denote, on B) if for every $y \in B$ there exists $x \in D(f)$ such that $f(x) = y$. Equivalently, $H(f) = B$
$$(\forall b \in B, \exists a \in A) f(a) = b$$
**Bijective** (from $A$ to $B$ ) if it is both injective and surjective.

Let us also define now the identity.
The function $id_A: A \rightarrow A$ is defined by formula $f(x) = x$ and is bijective.
Any invertible $g \circ g^{-1}$ will evaluate to the identity. The domain will be the entire domain,, since the existence of the inverse implies bijection (covers entire set).

We say a function is:
- increasing on $A$ if $(\forall x,y \in A) f(x) \leq f(y) \implies x \leq y$
- decreasing on $A$ if $(\forall x, y \in A) f(x) \geq f(y) \implies y \geq y$
- strictly increasing, if there is no equality, only $<$ 
- strictly decreasing,if there is no equality, only $>$ 

A function is said to be (strictly/) **monotonic** if it is (strictly/) increasing or decreasing. 

If a function is strictly monotonic, then $f$ is bijective.

An injective function does not need to be strictly monotonic. For example, $f(x) = \frac{1}{x}$ whose natural domain $D(f) = R \setminus \{0\}$   

Functions can be bounded or not bounded.
We say that the function is bounded, bounded above, or bounded below, if $H(f)$ is a bounded, bounded above or bounded below set, respectively.
$$\exists k > 0 : \forall x \in D(f) : |f(x)| \leq k$$


A function is:
- **even**, if for every $x \in D(f)$, $-x \in D(f)$ and $f(-x) = f(x)$. symmetric on y-axis.
- **odd**, if for every $x \in D(f)$, $-x \in D(f)$ and $f(-x) = -f(x)$

Note, a function can be neither even nor odd.

The definition of an odd an even function is as follows.
Let $f: R \rightarrow R$ be a function and $T \in R$ be positive such that:
- $\forall x \in D(f), x + T, x - T \in D(f)$
- $\forall x \in D(f), f(x+ T) = f(x)$
We say a function is **periodic** and that $T$ is the period of the function.

### Part II

#### Asymptotic Behavior of Functions

We will reintroduce the Big O and small o notations. They are useful to get asymptotic estimates and compute limits, they give a formal meaning to expressions like "at infinity the function goes to..." "the function goes to zero faster than..."

We will use the notion of neighborhoods. 
Let $a \in R \cup \{-\infty, +\infty\}$ the notation $x \rightarrow a$ means "x approaches a" in the sense that it is getting closer and closer toward $a$.
What is the definition of "getting closer"?

We define it by **neighborhood**.
Let $a \in R$ and $\epsilon > 0$. The open interval $(a - \epsilon, a + \epsilon)$ is called $\epsilon$-neighborhood of point $a$ in $R$ and we denote it by $U_a(\epsilon)$. also, $x \in U_a(\epsilon) \iff |x-a| < \epsilon$ 
The intervals $(a - \epsilon, a)$, $(a, a + \epsilon)$ are called the right and left sides of the neighborhood, denoted by $U_a^-(\epsilon)$ and $U_a^+(\epsilon)$ respectively.

The notation $x \rightarrow +\infty$ can be defined by introducing the extended real line $\overline R$, which would be the set constructed by $R \cup \{+\infty, -\infty\}$.
Thus, open interval $(a, +\infty), (a, -\infty)$  are called the $a$- neighborhoods of $+\infty$ and $-\infty$ in $R$, respectively. We denote them by $U_{+\infty}(a), U_{-\infty}(a)$ 

We take values in the neighborhood of infinity, in an interval smaller and smaller. A point belongs to its neighborhood only if it is a real number, so the infinities do not belong to it.

We say that $a \in \overline R$ is a cluster point of a set $M \subseteq R$ if every neighborhood of $a$ also contains a point of $M$ other than itself.
As in, $M \cap U_a \ \{a\} \neq \emptyset$ for every $U_a$. We also say that $M$ is near $a$.

Since $R$ is complete, unlike $N$, $3$ can be a cluster point in the former but not the latter. 
However, $+\infty$ is a cluster point for both.

Definition of Big O.
Let $f, g$ be two functions and $a \in \overline R$  be a cluster point of $D(f) \cap D(g)$ we say $$f=O(g) ~ x \rightarrow a$$
$x$ is not equal to $a$, it is merely close to it.
If there **exists** a positive constant $C$ and neighborhood $U_a$ of the point, such that $U_a \setminus \{a\} \subset D(f) \cap D(g)$ and $\forall x \in U_a \setminus \{a\}$ it holds $$|f(x)| \leq C |g(x)|$$
Additionally, if $g(x)$ is nonzero, $$|\frac{f(x)}{g(x)}| \leq C$$

Example. For $f(x) = 3x^4 + x$
For every $x \in (1, +\infty)$ i.e. $U_{+\infty}$
$|f(x)| = |3x^4+x| \leq 3|x^4| + |x|^4 \leq 4|x|^4$
This means that $f(x) = O(x^4)$ for $x \rightarrow +\infty$ 
The correct way to write this would be $f(x) \in (x^4)$

Now, what is little o?
Let $f, g$ be two functions and $a \in \overline R$ be a cluster point of $D(f) \cap D(g)$. We say that $f \in o(g)$ for $x \rightarrow a$ if **for every** positive constant $C$ there exists a neighborhood that holds $$|f(x) < C|g(x)|$$ Essentially, it is a more strict, strong Big O.
"little o of g" $\implies$ "Big O of g", but the contrary isn't true!
If $g$ is not equal to zero in a sufficiently small neighborhood of $a$, $f \in o(g)$ is equivalent to the fact that limit of $\frac{f}{g} = 0$ as $x \rightarrow 0$.

