Consider we have a vector space $V$, and we have subspaces $U_1, ..., U_n$.
How do we create a subspace that includes all those subspaces?
We use a direct sum $U_1 \oplus ... \oplus U_n$ 
It consists of the sum of them $U_1+...+U_n$ .. and... another thing?
This is unique apparently.

Uniqueness of representation. If $u$ can be represented in two different ways (sums), then every addant in the sum has to be equal to the other addant.

If $A$ is injective:
$Av_1 = Av_2 \implies v_1 = v_2$
Due to the linearity of the vector space, proving uniqueness for all vectors means also proving uniqueness for zero.

A vector space is called finite dimensional if it is spanned by a list.
By a list we always mean a finite list.
If we write in the test/exam that a vector space is fin. dim. if it admits a fin. basis, it will be flagged as wrong. We'd need to define a basis here, so it is not a definition..
$F^n$ is fin. dim., $M_{m,n}(F)$ is also fin. dim, and so are all its fundamental subspaces. 
We called a vector space inf. dim. if it is not fin. dim.

For the claim, $P(R)$ is inf. dim. we can write, for every list $\beta$ of $P(R)$, $P(R) \neq span(\beta)$ 
Note also $deg(p+q) \leq max\{degp, degq\}$ and $deg(\alpha p) \leq deg p$ 
Then it follows $deg(\alpha p + \beta q) \leq max\{degp, degq\}$ 
Then if $p \in span(p_1, p_2) \implies degp \leq max\{degp_1, degp_2\} \implies p \in span$ 
$p \in span \implies degp = max\{degp_1, degp_2\}$ 
We can however find a polynomial $x^{m+1}$ which a different degree, and so it does not belong to the span.
We inductively prove then that it is an inf. dim. vector space, since we can always find another polynomial which does not belong to it.
Editor's note: Is $P$ the power set..? I doubt.

Any list containing additive identity $\vec0$ is linearly dependent.
Reminder, a list is called LI if the only choice of $a_1,...,a_n \in F$ that makes $a_1v_1+...+a_nv_n = \vec0$ is $a_1=...=a_n=0$.
By the definition, we should find a linear combination which is equal to zero but not all of the scalars are zero. If we have the $\vec0$, then there are some scalars that don't satisfy this. For example, for $\{\vec0, v_2,...,v_m\}$ we have LC $1\cdot\vec0+0v_2+...+0v_m$  and $1\neq0$.

A list $v$ of one vector $\iff v\neq \vec0$.
If $v = \vec0$ then by the previous proof it is LD.
But if it is not equal to zero, then $\alpha v = \vec0 \implies \alpha = 0$ and $\alpha = \alpha = 0$.

...Also we can assume $\alpha v = \vec0$ for some scalar.
Assume the scalar is nonzero, then its inverse exists.
$\alpha^{-1} \alpha v = \alpha^{-1} \vec0 \implies v = \vec0$ which is contradiction.

A list of two vectors is LI if neither vector is a scalar multiple of another.

Can a list $(v_1, v_2,v_3)$ be LI when $(v_1, v_2)$ is LD?
$(v_1, v_2)$ LD $\implies \exists a_1, a_2 \neq 0$ s.t. $a_1v_1 + a_2v_2 = 0$ 
Then, $a_1v_1 + a_2v_2 + 0v_3 = 0$, but $a_1 \neq 0$ nor $a_2 \neq 0$ so it is not possible.

Two mappings/functions/matrices/polynomials are the same when their values at every input are the same. 
Equivalently, degree and coefficients of polynomials are the same.

If we have a LD list such as the first vector is not zero, then exists $j \in \{2,..,m\}$ s.t.:
- $v_j \in span(v_1,..,v_{j-1})$
- If $v_j$ is removed from the list, the span will remain the same.

$\vec0 = a_1v_1 + a_2v_2$ 
For the first case, assume $a_1 \neq 0$, then multiply by its inverse.
$\vec0 = v_1 + a_1^{-1}a_2v_2 + a_1^{-1}a_3v_3$ 
Then, $v_1 = -a_1^{-1} a_2v_2 -a_1^{-1} a_3v_3$
Finally, $v_1 \in span(v_2, v_3)$ 
This applies for every single one of these.

List of polynomials, is it LI or LD...

We went through the results, theorems, rules of LA1 and proved them.
