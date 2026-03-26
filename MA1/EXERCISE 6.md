The test question was: $\lim_{n \rightarrow +\infty} \sqrt{n+1} - \sqrt{2n}$ 
The usual trick is to use $(A+B)(A-B)=A^2-B^2$
 $\lim_{n \rightarrow +\infty} \sqrt{n+1} - \sqrt{2n} =$
 $\lim_{n \rightarrow +\infty} \sqrt{n+1} - \sqrt{2n} \cdot \frac{\sqrt{n+1} + \sqrt{2n}}{\sqrt{n+1} - \sqrt{2n}} =$ 
 $\lim_{n \rightarrow +\infty} \frac{1-n}{\sqrt{n+1}+\sqrt{2n}} =$
 We should find out the highest power of $n$ in fractions.
 $\lim_{n \rightarrow +\infty} \frac{n(\frac{1}{n}-1)}{\sqrt n (\sqrt{1+\frac{1}{n}}+\sqrt 2)}=$ 
 $\lim_{n \rightarrow +\infty} \sqrt n \cdot \frac{0-1}{\sqrt{1+0}+\sqrt{2}}$ 
 $\rightarrow -\infty$

Easiest way was, at the beginning, to factor out $\sqrt n$ actually.

...

Zero times bounded is zero. Infinity times bounded (sign changing) is undefined.
$\lim_{x \rightarrow +\infty}\frac{\sin x}{x} = \lim_{x \rightarrow +\infty} \frac{1}{x} \sin x = 0 \cdot ? = 0$ 
Same with $\lim_{x \rightarrow +\infty} \frac{1}{x} \cdot \cos \frac {1}{x} = 0$

If the function is continuous, then the limit of the function at a defined point, is the value of that point.
$\lim_{x \rightarrow a} f(x)=f(a)$ 
Given that $f$ is (locally) continuous.

We may also find a subsequence for the function infinitely approaching the point.
Then, if $\lim_{n \rightarrow \infty} (x_n) = b \implies \lim_{n \rightarrow \infty}~f(x_n) = b$

This is Heine's theorem. Basically meaning, this is the reason we can use all the theorems of sequences in functions, employing real subsequences of real functions.

We can also use another trick we've seen in sequences.
If we can find two disagreeing subsequences, we can prove the limit does not exist.
Also Heine's theorem apparently.
