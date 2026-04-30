The derivative tells us the instantaneous rate of change.
A function is differentiable at a point if it is continuous and the derivative is a real number.

Calling a function differential is a notion for open interval.s Doesn't make sense to take the derivative of the edge.

Good way: $$\frac{d}{dx}f(x)= \lim_{h \to 0} \frac{f(x+h)-f(x)}{h}$$

May also see: $$\frac{d}{dx} f(x) = \lim_{a \to x} \frac{f(x)-f(a)}{x-a}$$


All polynomials are differentiable. 
Note these rules:
$$\frac{d}{dx} ax^n = anx^{n-1}$$
$$\frac{d}{dx}[f(x)+g(x)]=\frac{d}{dx}f(x) + \frac{d}{dx}g(x)$$
$$\frac{d}{dx}[cf(x)] = c\frac{d}{dx}f(x)$$
$$\frac{d}{dx}[f(x)g(x)]= g(x)\frac{d}{dx}f(x) + f(x) \frac{d}{dx}g(x)$$
$$\frac{d}{dx}[\frac{f(x)}{g(x)}] = \frac{g(x) \frac{d}{dx} f(x) - f(x) \frac{d}{dx} g(x)}{g^2(x)}$$

These are general. Now limits of elementary functions:
$$\frac{d}{dx} sin(x) = cos(x)$$
$$\frac{d}{dx} cos(x) = -sin(x)$$
$$\frac{d}{dx} a^x = \ln(a) a^x$$
$$\frac{d}{dx}\log_ax = \frac{1}{x \ln a}$$
$$\frac{d}{dx} \tan(x) = \sec^2(x) = \frac{1}{\cos^2(x)}$$
$$\frac{d}{dx}\cot(x) = -\csc^2(x) =- \frac{1}{\sin^2(x)}$$
$$\frac{d}{dx}\arcsin(x) = \frac{1}{\sqrt{1-x^2}}$$
$$\frac{d}{dx}\arccos = -\frac{1}{\sqrt{1-x^2}}$$
$$\frac{d}{dx}\arctan(x) = \frac{1}{\sqrt{x^2+1}}$$

It is important to mention there is a derivative for the composition of functions.
$$\frac{d}{dx}(f \circ g)(x)=((\frac{d}{dx}f \circ g)\cdot g)(x)$$
It's called chain rule because: $f(g(h(x)))'=f'(g(h(x)) \cdot g'(h(x)) \cdot h'(x)$

Derivative of a function is not unique.

Differentiability implies Continuity.