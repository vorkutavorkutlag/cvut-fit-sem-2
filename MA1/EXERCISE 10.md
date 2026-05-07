Investigating function: $$f(x)=2arctan(x)-x$$
Let us look at the intersection with the vertical axis. $f(0)=2arctan(0)-0 = 0$
Let us look at the intersection with the horizontal axis. 
Let us find intersections between $arctan(x)$ and $\frac{x}{2}$
We cannot find them precisely, we would have to estimate it with iterative methods such as Newton methods.
We cannot calculate them, we can only argue that there are two more.
We see that there are two more by drawing $arctan(x)$ and $0.5x$

Let us find the limits and asymptotes at the end points of the domain.
Since the function is defined everywhere the only asymptotes will be at the infinities.
The limit at negative infinity is positive infinity.
The limit at positive infinity is negative infinity.

Note that it is an odd function. The difference of two odd functions is odd.

Let us now check for slant asymptotes.
$$\lim_{x \to \pm\infty} \frac{2arctan(x)-x}{x}=\frac{2arctan(x)}{x}-1=-1$$

Perfect, we have the slant, being $-x$. Now let's find the offset.
$$\lim_{x \to \pm\infty} 2arctan(x)-x+x=lim_{x\to\pm\infty}2arctan(x)=\pm\pi$$

Right-side slant asymptote: $y=-x+\pi$
Left-side slant asymptote: $y=-x-\pi$

Let us look at possible monotonicity. Compute the derivative.
$$\frac{d}{dx}=\frac{2}{1+x^2}-1$$
We can simplify by making the fraction $f'(x)=\frac{1-x^2}{1+x^2}$
The domain is all real numbers. We want to find where it is equal to zero.
$f'(x) = 0 \iff 1+x^2 = 0 \iff x=\pm1$
Those extremes are minima and maxima respectively. Check by table.
We say then that $f$ is strictly decreasing on $(-\infty, -1] \cup [1, +\infty)$

Note that we check strictly decreasing by $(\forall x,y \in (-\infty, 1]) (x < y \implies f(x) > f(y))$
We do not use the derivative definition, then we can say the interval is closed, even though the value of the derivative at that point is zero.

We find the second derivative to find convex (UP) and concave (DOWN) and we call $0$ the reflection point.