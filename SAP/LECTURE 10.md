# Floating Point Numbers Representation

Two basic types of number format include fixed point and floating point arithmetic.
Strictly defined size of integer and fractional part, as opposed to flexible size of integer and fractional part.

#### The principle.
The representation has two parts:
- Mantissa $m$
- Exponent $e$
The number value $N = m \cdot r^e$ .
For binary, $N = m 2^e$

For negative numbers,
Mantissa is in some code for signed numbers. Sign magnitude and 2's complement.

For fractional numbers, exponent is in some code for signed numbers. biased, 2's complement.

For IEEE, First bit is sign, then two bits are exponent, then the rest of the bits are mantissa again.

The strict rules are given by the specification and standard.


#### Normalized form.
When the mantissa cannot be shifted to the left anymore.
No pending zeros at the left hand side of the mantissa.
Whenever we multiply the mantissa by the radix, it is easier to increment the exponent by one.

If it's in 2's complement, when we shift it to the left, it could become negative.
So this number is normalized once shifting to the left will flip the sign.

A normalized representation of a number is unique.

Arithmetic operations using normalized forms do not guarantee having the result in normalized form. Normalization required after every operation.

...

The concept of "Hidden One" or "Leading Bit Convention".
Assumptions include binary encoding ($r=2$) and normalized form.
When we have a normalized number Mantissa always starts with $1$.
That's how we save one bit. We can display more numbers.

Basically, the hidden one is not represented, but we know it is there. The first non-sign bit of the mantissa is always one.

...

In general, that's all.

How do we represent a zero? It's a special case.
We've been trying to talk very generally about it all.
Now about the standard in particular.

### IEEE-754 (1985)

Binary.
Mantissa represented in sign magnitude code.
Range of the mantissa: $0 \leq |m| < 2$ - the modulus $M$ = 2
Exponent in biased code.
Different precisions.
`float` is for single precision, `double` is for double precision.

The single precision 32 bit mantissa has 24 bits, but the one is hidden, 23 without it..
1 sign, 8 exponent, 23 mantissa.
The double precision 64 bit mantissa has 52 bits, but the one is hidden, 51 without it.

As of 2008, we also have half precision (the one we will be working with in AVR), single precision, double precision, quadruple precision, octuple precision.

Special cases include:
- Zero (0) is represented as all zeros. `e:0, m:0`
- $\pm$Infinity `e: 255, m:0`
- NaN `e:255, m:-`
- $(-1)^2 \cdot (m+1) \cdot 2^{e-127}$ : `e: <1...254>, m:m`


### Operations in Floating Point
A little bit more complicated than fixed point.

##### Addition/Subtraction
Align the radix point. Mantissa of the operand with the smaller exponent is shifted right.
The operands will have the same exponents as a result.
Add/Subtract the mantissas.
Normalize the result.

##### Addition/Subtraction
Multiply/Divide the mantissas.
Add/Subtract the exponents.
Normalize the result.

...

### Storing Numbers in memory

A little bit to do with floating point numbers.
Storing big numbers in memory.
The problem is, some data types are longer than one byte.
Byte is always 8 bits.
A word size depends on the CPU architecture.

The question, how to order the bytes in memory to form a word? Little endian, big endian...
