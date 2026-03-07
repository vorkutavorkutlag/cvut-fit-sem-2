Direct sum mentioned. What's the point of this anyway

For every positive integer $m$, if a list has a linearly independent list of that length, then the vector space is infinite dimensional.

For two subspaces of a finite dimensional vector space,
$dim(U+W) = dim(U)+dim(W) - dim(U \cap W)$
Inclusion-Exclusion (?)

Optional homework. Only one.
1. Write a summary of lecture. Notations, important results and their relations.
2. Which proof did you like the most and why?
3. Which proofs do you find most challenging and why? Any suggestions to improve?
4. Write down, sketch some proofs in your writing.

#### Part II

Are necessarily all subspaces of inf. dim. vector spaces, inf. dim.?
Let $W = \{a_1, a_2, 0 ....\ ~:~ a_1,a_2 \in R\} \subset R^{\Omega}$    
It is spanned by a list $(a_1, a_2)$.
Therefore, not necessarily, but we should provide an example.

We can do the same thing with polynomials.
$V = P(R), W=P_3(R), W=span(1,x,x^2,x^3)$

Recall, how do we show if $R^\Omega$ is inf. dim.?
For every integer $m$, there is an LI list of that length.

For next week, prove that if list $(v_1,v_2,v_3)$ is LI in $V$ then $(v_1-v_2,v_2 - v_3, v_3)$ is LI.
Also, if list $(v_1,v_2,v_3)$ spans $V$, then $(v_1-v_2,v_2-v_3,v_3)$ is spanning.

$\begin{bmatrix}x \\ |y| \end{bmatrix}$ is not a subspace of $R^2$ since $- \begin{bmatrix}x \\ |y| \end{bmatrix}$ , the additive inverse, does not exist in the subspace, it is not closed. Same with $\begin{bmatrix}x \\ y \\ x^2 \end{bmatrix} \not \subset R^3$  since it is not closed under neither vector addition nor scalar multiplication.

The set of invertible matrices is not a subspace, since it lacks the zero, which is not invertible. Also not closed under vector addition.

The set of polynomials satisfying $p(3) = 0 \in P_3(R)$ is a subspace due to the properties of polynomials as functions such as $(p+q)(3)=p(3)+q(3)=0+0=0$ and $(cp)(3)=c(p(3)) = c(0) = 0$

Is the set of polynomials with odd degree a subspace in $P(C)$? No.
Counterexample: $(1+x+x^2+x^3) + (1 - x^3) = 2+x+x^2$  even degree!
