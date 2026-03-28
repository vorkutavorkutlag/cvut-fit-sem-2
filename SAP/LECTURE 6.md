
## Data, Codes, Fixed-Point Arithmetic

Numeral systems and their conversions...

Radix number system.
It is positional. The number is determined by the basis, the radix of the system.
The radix is the number of symbols we can use (basis)

Fixed-Base - the basis is the same for all digits.
Weighted system - the position determines the power of the base
Finite - the number of digits is finite

Displaying numbers in radix systems.
$A_r = (a_n, a_{n-1},..., a_1, a_0 . a_{-1}... a_{-m})$
Integer part, and fractional part. The decimal point is the radix point.
The resulting number can be calculated as the sum of the radix to the power of the position times the value at that position.

That's also how we can convert any number from any radix to decimal.

From decimal to binary...
The integer and fractional parts are converted separately. 

We gradually divide the number by 2, recording the remainders.
For example, if the number is even, the right-most digit in binary will be $1$.

For fractional part, we gradually multiply by 2, and record the integer part.

One issue is the precision. We have numbers in decimal, like one third, $0.33333....$
We cannot precisely represent it unless we choose some other means.
Maybe storing nominator and denominator separately? 

...

Hexadecimal is nothing more nothing less as compressed binary.
The idea is, one digit, can represent 4 binary digits. Sixteen different possibilities.
From binary, to hexadecimal...
One digit in HXD = 4 digits in binary.
We have to go from the decimal point, go to the left extracting 4-tuples.
Then, to the right, extracting 4-tuples.
In case of missing digits (not in groups of 4), we pad with zeros at the end.

`0.1` in binary will be `0.8` in HXD. because it is actually `0.1000`

People usually make mistakes in the fractional part, not the integer part.

...

Basic operations in binary, briefly.

Addition can be done using the carry to the highest order. We remember the adder...
Multiplication in binary is being done manually by multiplying it bit by bit and summing it up, always going one order higher by bitshifting it.

...

Number format.
Specifies the range of numbers that can be represented. Defined highest order and smallest order.
Basic properties include:
- length - total number of digits
-  number format unit (epsilon) - the smallest non-zero number that can be represented. 
- Number format modulus (M) - the smallest integer number that cannot be represented by the format. It is equal to the biggest number + epsilon.

For example, `3210.0` 
$l = 4, ~ n = 3, ~-m = 0, ~ \epsilon = 1, M = 10000_2$ 

It holds that:
$l = n + m + 1$
$M = r^{n+1}$
$\epsilon = r^{-m}$
Where $r$ is our radix.

....

Signed and unsigned numbers.
If we have unsigned numbers we can only represent non-negative numbers. The standard radix system represents unsigned numbers only.

Signed numbers, include being able to represent negative numbers.
Some negative numbers are mapped to some positive numbers, so the range of positive numbers is reduced.
Codes for signed numbers are used.
$2$'s complement code ("radix complement" in general)
Sign-magnitude code.
Biased code.

We have to sacrifice some positive numbers for the representation, we have to limit the positive numbers, and we use that range to represent negative numbers.

All computers are using the radix complement code.
The definition is...
$RC(X) =X$ if $X \geq 0$
$RC(X) = M-X$ if $X < 0$
Where $M$ is the number with the MSB flipped on.
![[Pasted image 20260316193703.png]]
This also demystifies overflow/underflow.

For example, 8 bits ranges from $-128$ to $127$.
![[Pasted image 20260316193920.png]]

The leftmost bit corresponds to the sign.

The algorithm from the definition is... If $X$ is non-negative, the image is $X$
Otherwise, compute image $M+X$

Another algorithm to compute it, for negative numbers, is writing the absolute value of the number, negating all the bits, and then adding +1.

This encoding also works in hexadecimal, seeing as it is just another transcription of binary.

It works everywhere, even in decimal.

In binary, if the left-most bit is 1, it's negative, otherwise, it's positive.
In hexadecimal, if the first character is $8..F$ is negative, otherwise ($0...7$), positive.
In 8 bit decimal (M = 256), if the image is in ${128..255}$
In binary, all ones, is $-1$

The reason we use this code is because it is very efficient and convenient for addition.

The adder doesn't care what is positive and what is negative, it just adds, and the result is correct (not counting overflow/underflow).

When we are not able to represented the result in radix compliment, that's overflow/underflow.

Check the polarity (MSB).
Adding two positives will result in a negative only in OF.
Adding two negatives will result in a positive only in UF.

There are no subtractors, just adders.
We do not care about positive or negative numbers. 
Instead of $A + B$, we write $A +$ the additive inverse of $B$, calculated as $M-RC(B)$

...

We also have the sign magnitude code, that we also know already.
We have the sign, and the magnitude. The sign is indicated by the MSB, the rest is the absolute value of the number.

We have a redundancy, we have both positive and negative zero. 

We also have the biased code, it is good for some specific purposes.
Zero is not represented as $0000$
It is shifted by a bias.
The image of the number is $X+K$ 
![[Pasted image 20260316200552.png]]

Radix Complement is the standard signed numbers, mantissa in some floating point representations.
Sign magnitude code is Mantissa in some floating point representations.
Biased code is exponent in some floating point representations.

In IEEE-754 they use sign magnitude and biased code, not radix complement.

