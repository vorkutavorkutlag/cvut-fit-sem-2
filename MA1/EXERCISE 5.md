
We have indeterminate limit.
$\lim~_{n \rightarrow +\infty} \sqrt{n+1} - \sqrt n$
We are going to learn about one trick.

Keep in mind the formula $(A-B)(A+B)=A^2-B^2$
we can rewrite it as $\lim_{n \rightarrow +\infty} \sqrt{n+1} - \sqrt n \cdot \frac{\sqrt{n+1} + \sqrt n}{\sqrt{n+1} + \sqrt n}$ 
Which is then equal to $\lim~_{n \rightarrow +\infty} \frac{n+1-n}{\sqrt{n+1} + \sqrt n} = \frac{1}{+\infty} = 0$  

`3.10)` $\lim_{n \rightarrow +\infty} n \cdot (\sqrt{n^2+1}-n)$
This is also indefinite since we have $+\infty - \infty$ 
We will be using the same trick as earlier.
$\lim_{n \rightarrow +\infty} n \cdot (\sqrt{n^2+1}-n) \cdot \frac{\sqrt{n^2+1}+n}{\sqrt{n^2+1}+n}$ 
We are hoping for simplification.
This is equal to $\lim_{n \rightarrow +\infty} n \cdot \frac{n^2+1-n^2}{\sqrt{n^2+1}+n} = \lim_{n\rightarrow +\infty} \frac{n}{\sqrt{n^2+1}+n}$ 
We have another indeterminate expression. We factor out $n$ in the denominator.
$\lim_{n \rightarrow +\infty} \frac{n}{n \cdot (\sqrt{1 + \frac{1}{n^2}}+1)}$ 
Any real number over infinity is zero. Then, we simplify the $n$, and we get $\frac{1}{2}$

`3.11)` $\lim_{n \rightarrow +\infty} \frac{2^n-2^{-n}}{2^n+2^{-n}}$ 
Consider that $\frac{2^{-n}}{2^n} = 2^{-n-n} = 2^{-2n}$ 
Positive exponent is always increasing, negative exponent is always decreasing.
We will factor out $2^n$ from both nominator and denominator.
$\lim_{n \rightarrow +\infty} \frac{2^n(1-2^{-2n})}{2^n(1+2^{-2n})} = \lim_{n \rightarrow +\infty} \frac{1-2^{-2n}}{1+2^{-2n}} = \frac{1-0}{1+0} = 1$

When the limit goes to $1$, we say the sequences have similar speed.
In a test we do not need to prove that the negative exponent goes to zero. Just maybe a comment saying that it does, so that you show you understand, but no need proving.

`3.12)` $\lim_{n \rightarrow +\infty} \frac{(\frac{1}{2})^{n^2} - (\frac{1}{3})^{n^2}}{(\frac{1}{2})^{n^2+1}-(\frac{1}{3})^{n^2+1}}$
Recall $a^n < b^n \implies a^{-n} > b^{-n}$
We can factor out both nominator and denominator.
$\lim_{n \rightarrow +\infty} \frac{(\frac{1}{2})^{n^2} \cdot (1- (\frac{2}{3})^{n^2})}{(\frac{1}{2})^{n^2+1} \cdot (1 - (\frac{2}{3})^{n^2+1})}$ 
The terms within the braces on the right go to zero, since a positive exponent of a fraction in infinity is equal to zero (theorem).
Then, we can use the fact that division of the same base is subtraction of the exponent. Then we have left $(\frac{1}{2})^{n^2-n^2-1} = 2$

Recall:
- $\lim_{n \rightarrow +\infty} a^n = 0 ~~~ |a| < 1$

Let's consider the limit $\lim_{x \rightarrow 0} \frac{-3x^2+x+1}{x^3}$
It does not exist since since the exponent is odd.
It is positive/negative infinity, depending on the side we approach from.
The limit itself is undefined, but we can define $\lim_{x \rightarrow 0^+}$ and $\lim_{x \rightarrow 0^-}$
There is a theorem stating if the one-sided limits aren't equal, the limit is undefined.

 $\lim_{x \rightarrow 0^+} \frac{-3x^2+x+1}{x^3} = \frac{0+0+1}{0^+} = +\infty$
 $\lim_{x \rightarrow 0^-} \frac{-3x^2+x+1}{x^3} = \frac{0+0+1}{0^-} = -\infty$

...

We have the limit that eventually will be a formula. 
$\lim_{x \rightarrow 0} \frac{\sin x}{x} = 1$
We use the squeeze theorem to prove it, using the upper bound of sine.

Likewise, $\lim_{n \rightarrow +\infty}\frac{\sin \frac{1}{n}}{\frac{1}{n}}$
It doesn't matter in what form it comes in, the element inside the sine and in the fraction must be approaching zero.

HEINE'S THEOREM.