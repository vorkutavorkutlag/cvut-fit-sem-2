
Big O says we have a "similar speed".
Little O has a more dramatic difference in speed.

Just to make something clear:
- $x^2 \in O(3x^2)$
- $3x^2 \in O(x^2)$

However, $x^2 \not \in o(x^2) ~~~ x \rightarrow +\infty$ 
Since, $(\forall C > 0)(\exists U_{+\infty}) |x^2| < C|x^2|$ does not hold for every $C$!

`1.41.c)` $2x\sin(x) \in o(\sin(2x)) ~~~ x \rightarrow 0$ 
$(\forall C > 0)(\exists U_0)$
$|2x\sin(x)| < C|\sin(2x)| \implies 2 |x| |\sin(x)| < 2C|\sin x| |\cos x|$
We can divide by $\sin(x)$  since it will never be zero in this punctured neighborhood.
$\implies |x| < C|\cos x|$ 
It is impossible to get just one $x$ from this. We jut want to find $|x| < ... < ... < ... < ... < C |\cos(x)|$ 
We will be using approximations by looking at the graph.
For example, we can choose the point where cosine is equal to half.
![[Pasted image 20260305122441.png]]
$\implies |x| < C \frac{1}{2} < C |cos(x)|$
Then we have conditions $|x| < \frac{\pi}{3}$ and $|x| < \frac{1}{2} C$

Thus, $U_0 = (MIN\{\frac{\pi}{3}, \frac{C}{2}\})$ 
Alternative notation: $U_0 = (-MIN\{\frac{\pi}{3}, \frac{C}{2}\}, MIN\{\frac{\pi}{3}, \frac{C}{2}\})$ 


Now, to sequences,
Sequences only have cluster points at positive infinity.

`2.1.e)` $3(\cos(\sqrt n)) \in O(1) ~~~ n \rightarrow +\infty$
$(\exists C > 0) (\exists K > 0) ~~~ |3 \cos(\sqrt n)| \leq C |1|$
Where $k$ is the neighborhood of infinity. $(\forall n > K)$ basically
$\implies 3|\cos(\sqrt n)| \leq 3 \leq C$
So then we can choose (since this is Big O), $C := 3, K := 1$

`2.1.g)` $-3n^3 \cos(2n^2+3) \in o(n^4) ~~~ n \rightarrow +\infty$
($\forall C > 0)(\exists K > 0) (\forall n > K)$
$|-3n^3 \cos(2n^2+3)| < C|n^4|$
The obvious trick with cosine...
$\implies 3|n^3 \cos(2n^2+3)| \leq 3|n^3| < C n^4$    Since $n \in N$
We need to know condition for $n$
$\implies \frac{3}{C} < n$ So then we choose $K := \frac{3}{C} + 1$ for example, and we have proved it.

