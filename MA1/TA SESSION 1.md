Mathematical Analysis 1.
The word analysis comes from the Greek word, which means to break up.
This semester, we won't see why that's true, but we will next semester.
Calculus and analysis are somewhat different.
In high-school, we might have seen calculus, the application of analysis.
Analysis focuses on the theory side of things. More theoretical than HS.
Pass rate for LA1 was 61%, pass rate for MA1 is 43%. `>_<`

We will have one test in the last third of the semester, for 30 points.
Above 20 is getting the zapocet.

The purpose of the sessions. The lectures are to explore the theory, exercises are to solidify, TA is to solidify further and summarize - this is not a replacement.

We will review first trigonometric functions.
Three primary trig functions, and their inverses, include:
**sine**
- $sin: R \rightarrow [-1,1]$ 

Going back to theory of functions.
We have two sets, $X, Y$.
We have three words to describe functions.
We want to talk about injectivity, surjectivity, bijectivity.
Injectivity: we have at most one element in $X$ that maps to $Y$. Algebraically, $f(x_1) = f(x_2) \implies x_1 = x_2$ 
Surjectivity: There is a preimage for every element in $Y$. Algebraically, $(\forall y \in Y) (\exists x \in X) f(x) = y$ 
Bijectivity is having both.

For every number interval $[1,1]$ we may find a value such that sin maps to it.
Meaning, it is surjective, onto.
However, sin is NOT injective, as it is periodic, it is not one to one.

**cosine**
- $cos: R \rightarrow [-1, 1]$
This is also surjective and not injective.
If it were $R \rightarrow R$ it would be neither surjective nor injective. These properties depend on the sets of our mapping.

The period of cosine is $2\pi$.
If we have $\sin$ and $\cos$ we have third function called **tangent**.
sine, cosine, tangent.
We define $\tan(x) = \frac{\sin(x)}{\cos(x)}$ 
We are dealing with real numbers, and we cannot divide by zero.
This means, whenever $\cos(x) = 0$, $\tan(x)$ is not defined.
Getting closer to that point, we have $0.99..$ divided by $0.000...1$ so we get a very large number, we have asymptotic behavior.

It is also periodic, and the period is $\pi$.
It is a mapping $\tan: R \rightarrow R$ . It is not injective due to its period. It is injective since in every period we can find values in $[-\infty, +\infty]$ in every period.
The real domain of tangent is real numbers without $\{\frac{\pi}{2} + \pi k\}$ 

We also have the functions:
- $\frac{1}{\sin(x)} = \csc(x)$
- $\frac{1}{\cos(x)} = \sec(x)$
- $\frac{1}{\tan(x)} = \cot(x)$


These were primarily used for navigation tables. Antonella does not expect you to remember these by heart but it is still good to know.
These are obviously not the same as inverse functions!
Anything we can express here can be also expressed without them.

Let's think about the inverse of fundamental trig functions.
If a function from an arbitrary sets has an inverse, then the mapping has to be a bijection. We also must have properties $(\forall x \in X) ~ g(f(x)) = x$ and also $(\forall y in Y ) ~ f(g(y)) = y$
We denote $g = f^{-1}$ and call it $f$-inverse.

We call the maximum height the amplitude.

We want to find the inverse of $\sin$.
Naively, we can take the line $y=x$ and reflecting the functions over the line.
For example, flipping $x^2$ over $y=x$, we get $\sqrt x$ 
The issue with sine is, we get something which is not a function, having many $y$ values for every $x$.

Now, how do we do it? We have to restrict the domain of such inverse. 
How should that be done? We can restrict the function in to half a period.
The interval would be the largest bijective (invertible) interval. $[-\frac{\pi}{2}, \frac{\pi}{2}]$ 

Then, if we flip only that interval over the line $y=x$, our domain will now be $[-1,1]$ and our image will be $[-\frac{\pi}{2}, \frac{\pi}{2}]$ .
This is given a name. We can denote it as **arcsine**.
- $\arcsin(x): [-1,1] \rightarrow [-\frac{\pi}{2}, \frac{\pi}{2}]$ 
The other notation we will see, is $\sin^{-1}(x)$. It is also arcsine, but we also denote powers of sine as such, so it can be confusing... Beware, it does not mean $\frac{1}{sin(x)}$

For cosine, we usually restrict it between $[0, \pi]$ . 
The inverse is **arccosine** 
- $\arccos(x): [-1, 1] \rightarrow [-\pi, 0]$ 

Now, the inverse of tangent has an asymptote at $\frac{\pi}{2}, -\frac{\pi}{2}$. 
We denote the function **arctangent** .
- $\arctan(x): R \rightarrow [-\frac{\pi}{2}, \frac{\pi}{2}]$

The natural domain of a function is the largest set you can consider the function from.
For example, we could also define $\arctan(x): \{0\} \rightarrow [-\frac{\pi}{2}, \frac{\pi}{2}]$ , how silly? 
So, we consider it in the largest set we can define it in.

We are done with the functions and their inverses. Some things before we get into problems...

We often saw things such as $\sin(90 \textdegree)$
Our sine has a different period, $2\pi$. The degree sine has a period of $360 \textdegree$
That sine is really stretched out, so it is different from our sine.
The sine we use from degrees, using real sine is $\sin(\frac{\pi}{180} x)$

$360$ is a very weird number, it exists only because ancient Babylonians liked multiples of $6$. Now, we use radians wherein $\pi$ is the decider. In our case, $2\pi$ is the circumference of the unit circle (radius = $1$)

Now, we can look at the cosine value as the horizontal length and sine value as the vertical length.
- degree $\theta = 0$ we get the values $(1, 0)$ for cosine, sine respectively.
- degree $\theta = \frac{\pi}{6}$ we get the values $(\frac{\sqrt2}{2}, \frac{\sqrt 2}{2})$ for cosine, sine respectively.
- etc.

![[Pasted image 20260227175912.png]]

Please consult the unit circle. You should have these values memorized.
The last thing you want to do on a test is to find out what is the $\sin$ of stuff.
Just one quadrant is enough, since we can just mirror it everywhere.

The exposition for the class is over with, time for some problems.

What is the domain of $\arcsin(4x)$ ?
We may substitute $u=4x$ and consider $\arcsin(u)$. That is trivial, by definition,
$u \in [-1, 1]$. And this simply means: $-1 \leq u \leq 1$, and equivalently, $-1 \leq 4x \leq 1$
Then, $-\frac{1}{4} \leq x \leq \frac{1}{4}$ and finally $x \in [-\frac{1}{4}, \frac{1}{4}]$

A positive multiple greater than 1 is kind of like speeding the effect, squishing it.
Does the horizontal squishing have any effect on the height has no effect on the height. So, the image will be the same.
Compressing it horizontally have no effect on the height.

What WOULD change it is if we wrote $3 \arcsin(4x)$. This stretches it vertically, so we can now "reach" $-3, 3$ 
If we applied the square root, or square, or anything, non-linear things, it would vary even more, not linearly. 

$f(x-1)$ just shifts the graph over to the right. Since, if we apply $1$, then we get $f(0)$.

Side-note, in LA1 we had quite a few notes on Christian's website. However, Antonella makes practice tests and has plenty of exercise on the course page, so no need.



Let us consider $f(x) = \arcsin(e^{x^2+x} + e)$
The domain of arcsine is $[-1, 1]$ .
So, $e^{x^2+x}+e \in [-1, 1]$  is bounded. Now we need to solve:
$-1 \leq e^{x^2+x}+e \leq 1 \implies -1-e \leq e^{x^2+x} \leq 1 \implies$
Now, we could have applied $\ln$ on the negative numbers, which is bad...
The expression $e^{x^2+x}+e$ is always bigger than $e$, so the bound does not fit.
Therefore, the domain of $f(x)$ will be $\emptyset$ (empty set).

Side-note: Technically there is some imaginary number magic to be done.

Big O is defined as such: $(\exists C > 0)(\exists U_a) |f(x)| \leq C \cdot |g(x)|$ 
Then we denote $f \in O(g) ~~~ x \rightarrow a$
Let us have two functions $f,g$. We have a point $a$ which is a cluster point.
A cluster point of a function is a point where exists a neighborhood in which $x$ is never equal to that point.

For example.
$f(x) = 2x^3, g(x) = 3x^2$ 
We need to show $f \in O(g) ~~~ x \rightarrow 0$
Note that if $x \rightarrow +\infty$ then it would be the opposite.
Anyway, let us try to prove:
$(\exists C > 0)(\exists U_0) ~~~ |2x^3| \leq C|3x^2|$
The correct term is a punctured neighborhood. We poke the little hole in it, so we don't actually care about zero, even though we are approaching it. So we may divide by $x^2$  So we get $(\exists C > 0) ~~~ |x| \leq \frac{3}{2}C$
Finally, we may choose $C=1$ and then $U_0 = [-\frac{3}{2}, \frac{3}{2}]$

We could also write $|2x^3| = 2|x||x^2| \leq 2|x^2|$ since we have chosen $U_0 = [-1; 1]$ 
In which case we could choose $C=\frac{2}{3}$ (since $\frac{2}{3}|3x^2| = 2|x^2|$) 
We don't have a single answer.

Let us try proving Little O now.
Little O is stricter.
$f \in o(g) ~~ x \rightarrow 0$
The definition is $(\forall C > 0)(\exists U_a) ~~~ |f(x)| < C |g(x)|$
The answer will depend as $C$ will be our variable.
$|2x^3| < C|3x^2| \implies 2|x| < 3C \implies |x| < \frac{3}{2}C \implies U_0 = (-\frac{3}{2}C; \frac{3}{2}C)$ 

Side-note: The logic is not circular, even though limits and neighborhoods share similar core ideas. Though, this is a more general idea, and does not care whether the function is continuous or not etc.

$f(x) = 3sin(x), ~ g(x) = 2xsin(x)$ 
Prove $g \in o(f) ~~~ x \rightarrow 0$

$(\forall C > 0)(\exists U_0)$
$|2xsin(x)| < C |3sin(x)| \implies \frac{|2xsin(x)|}{|sin(x)|} < 3C \implies \frac{2}{3}|x| < C \implies |x| < \frac{3}{2}C$     
Note that we can divide by sine. It can be zero, but it never reaches zero. It is a punctured neighborhood, it will never be zero.
Then, $U_0 = (-\frac{3}{2}C, \frac{3}{2}C)$ for every $C > 0$ 
Also denoted $U_0=(\frac{3}{2}C)$ to save redundancy.

We can try something more complicated now.
$f(x) = sin(2x), ~ g(x) = 2xsin(x) ~$ prove $g \in o(f) ~~~ x \rightarrow 0$
Using $sin2x = 2sinxcosx$ we end up with the equation $|x| < C |cosx|$ 
I don't entirely get this but the answer is $U_0 = min(\frac{C}{2} ; \frac{\pi}{3})$
This isn't a unique answer. 
If we chose $\frac{\pi}{4}$ instead, $U_0 = min(\frac{2C}{\sqrt2}; \frac{\pi}{4})$
We probably won't get something of this difficulty.
Even at the final test it will be more like the previous question.

