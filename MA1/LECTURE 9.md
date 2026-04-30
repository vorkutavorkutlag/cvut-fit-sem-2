# DERIVATIVES

The tangent, the infintisimal rate of change.
The definition.
Let $f$ be a function defined on a neighborhood of a point $a$. The value of the following limit, if it exists, is called **the derivative of the function f at point a**. We denote it by $f'(a)$, or $\frac{d}{dx}f(a)$. If the derivative is finite, we say the function is differentiable at $a$.

$$f'(a) = \lim_{x \to a} \frac{f(x)-f(a)}{x-a}$$

The limit in the definition of the derivative can also be written:
$$f'(a) =\lim_{h \to 0} \frac{f(a+h)-f(a)}{h} $$

...

The line given by the equality $y=f(a) + f'(a)(x-a)$ is the tangent of the function $f$ at point $a$.
If $f$ is continuous at point $a$ and its derivative is  positive or negative infinity, the vertical line is given by equality $x=a$

...

Derivative of a **constant** function is equal to $0$ at every point $a \in R$.
$$\lim_{x \to a} \frac{f(x) - f(a)}{x-a} = \lim_{x \to a} \frac{c-c}{x-a}= 0$$

Derivative of a **power** $x^n$ is $nx^{n-1}$.
$$f'(a) = \lim_{x \to a} \frac{x^n - a^n}{x-a}=\lim_{x \to a} \frac{(x-a)(x^{n-1} + x^{n-2}a + x^{n-3} a^2)}{x-a}$$ $$= \lim_{x \to a} (x^n-1 + x^n-2 a + x^{n-3}a^2 + ... + a^{n-1}) = na^{n-1}$$
Derivative of the **Euler exponent** is $e^x$.
$$\lim_{h \to 0} \frac{e^{a+h}-e^a}{h} = e^a \lim_{h \to 0} \frac{e^h-1}{h} = e^a$$

Using the definition of the limit, as well as trigonometric addition identities,
Derivative of **sine** is $\cos x$, Derivative of **cos** is $-\sin x$
$$\lim_{h \to 0} \frac{\sin(a+h)-\sin(a)}{h} = \lim_{h \to 0} \frac{\sin(h)\cos(h)+\cos(h)\sin(a)-\sin(a)}{h}$$
$$= \lim_{h \to 0} (cos(a) \frac{sin(h)}{h}+\sin(a) \frac{\cos(h)-1}{h}) = \cos(a)$$
Something very similar holds for cosine's derivative.

...

### Properties of Differentiable Functions
Theorem states about the  relation between differentiability and continuity.
If $f$ is a function differentiable at point $a$, then $f$ is continuous at point $a$.
$$\exists f'(a) \in R \implies \lim_{x \to a}f(x) = f(a)$$

$$\lim_{x \to a} f(x) - f(a) = \lim_{x \to a} \frac{f(x)-f(a)}{x-a} (x-a) = \lim_{x \to a} \frac{f(x) - f(a)}{x-a} \lim_{x \to a} (x-a) = f'(a) \cdot 0 = 0$$
Thus, $\lim_{x \to a}f(x) = f(a)$

...

By algebraic properties of the definition, we have the following rules:
**Addition**: $(f+g)'(a) = f'(a) + g'(a)$
**Product**: $(f\cdot g)'(a) = f'(a)g(a) + f(a) g'(a)$ Leibniz's Rule
**Quotient**: $(\frac{f}{g})'(a) = \frac{f'(a)g(a) - f(a)g'(a)}{g(a)^2} \iff g(a) \neq 0$

By quotient property and trigonometric identities, $tan'(x) = \frac{1}{\cos ^2(x)}$ 

Theorem about the derivative of a composite function.
$(f \circ g)'(a) = (f' \circ g)(a) \cdot g'(a)$

Derivative of the inverse function by theorem, $$(f^{-1})'(x) = \frac{1}{f'(f^{-1}(x))}$$
That is also the way we find: $$\frac{d}{dx} \ln(x) = \frac{1}{x}$$
Derivative of $\arcsin(x)$ is $\frac{1}{\sqrt{1-x^2}}$ where $x \in (-1, 1)$ 

