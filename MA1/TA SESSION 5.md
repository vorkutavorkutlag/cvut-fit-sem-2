
$u$-substitution with tangent limit, that being $\lim_{x \rightarrow 0} \frac{\tan x}{x} = 1$
We can split limits in multiplication and other operations as long as the limits exist and make sense on their own.

(Strictly) Monotonic sequences are sequences which are always (strictly) increasing or decreasing.
$(2,2,2,2,2,...)$ is neither strictly increasing nor strictly decreasing, but it is both increasing and decreasing, therefore it is monotonic. 
There can be sequences which are eventually monotonic.

$\log n$ is strictly increasing (monotonic), we aren't expected to prove it for now.

Supremum/Infinimum are the least/greatest upper/lower bounds.
If $k$ bounds the sequence from above, then $k+1$ does also, but then $k$ can be supremum and then $k+1$ is not the supremum.
Do not mix up limit at (positive/negative) infinity with supremum/infinimum.

Remember asymptotic hierarchy for limits. i.e., cosine or even exponential doesn't grow as fast as factorial.

Remember logarithm properties.

Can say nominator is bounded instead of doing the long squeeze theorem.

Remember Big O Little O definitions.

The definition is: $f \in O(g) x \rightarrow a$ 
If **exists** positive constant $C$ and exists neighborhood of point $a$, such that 
$|f(x)| \leq C \cdot |g(x)|$ 
Formally, $$(\exists C > 0) (\exists U_a) ~~ |f(x)| \leq C \cdot|g(x)|$$
Then, Little O is smaller. We find for **every** C a neighborhood $a$, and the different is strictly less than.
Formally, $$(\forall C > 0) (\exists U_a)~~ |f(x)| < C \cdot |g(x)|$$

Note that in sequences, there exists only a single neighborhood, being infinity.
Also, we are talking about very big numbers of $N$.
The implication being, if $n > N$, then, statement holds.
Inequality juggling.

Little O implies Big O but the converse is not true.

The definition for sequences is as follows.
$$(\exists C > 0) (\exists N) ~~ n>N \implies|f(x)| \leq C \cdot|g(x)|$$
$$(\forall C > 0) (\exists N) ~~ n>N \implies|f(x)| < C \cdot|g(x)|$$

