
# Proofs

Corollary states, given $U,W$ subspaces over $V$, then $V=U \oplus W \iff V = U+W \land U \cap W = \{\vec0\}$

We will be using previous proposition which states, that given subspaces $U_1,...,U_m$ over $V$, $\sum_{i=1}^mU_i$ is a direct sum if and only if the only way to write $0$ as a sum of $u_1+...+u_m$ is when $u_1=...=u_m=0$.

Forward implication:
Assume $V=U \oplus W$.
Prove $V=U+W$ and $U \cap W = \{\vec0\}$.

According to implication hypothesis, $V=U+W$ and $U, W$ create a direct sum.
Therefore, $V=U+W$ always holds by hypothesis.

For sake of contradiction, let there be a non-zero vector $v$ in $U \cap W$.
Then, by properties of vector space, $-v$ will also be in the $U \cap W$.
Then, by definition of additive inverse, $v + (-v) = \vec0$
However, by previous theorem, the direct sum is logically equivalent with the idea of zero can only be represented as the sum of zero vectors. 
Then again, we defined $v$ as non-zero, so we have reached an absurdity.
$\textreferencemark$ by contradiction, if $U+W$ is direct sum, $U \cap W = \{\vec0\}$

Backward implication:
Assume $V=U+W$ and $U \cap W = \{\vec0\}$
Prove $V = U \oplus W$.

According to implication hypothesis, $V=U+W$ holds, so we only need to prove $U,W$ create a direct sum. By our previous theorem, that is logically equivalent with proving that there is only one way to represent $0$ as a sum of vectors from $U, W$.

let $(v_U \in U)(v_W \in W)~v_U + v_W = \vec0$. Then, $v_W$ is the additive inverse of $v_U$. By properties of vector space, $v_U$ must also be in $W$. Then, zero must be written as a sum of a vector and additive inverse that exists both in $U, W$. The only vector that satisfies that, and its additive inverse too, is $\vec0$.
Therefore, by direct proof, if $U \cap W = \{\vec0\}$ then $U,W$ create direct sum. 


With both sides of implication, we show $V=U \oplus W \iff V = U+W \land U \cap W = \{\vec0\}$
