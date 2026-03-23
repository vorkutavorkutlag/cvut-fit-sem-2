
# Fixed Point Arithmetic Operations in Hardware

Number frame manipulation.
Shifts.
Addition, Subtraction.
etc.

Number format specifies the range of numbers that can be represented, defines the highest order $n$ and smallest order $-m$.
The length $l$ is the total number of digits.
The number format unit $\varepsilon$ is the smallest non-zero number that can be represented.
Number format modulus... check last lecture.

We have two basic types of number format.
Fixed point - radix is fixed.
Floating point - the radix point is defined relatively.

##### Frame Manipulations

The size of the frame can be manipulated.
Precision increase/decrease.
Extension of range, reduction of range.

There will be tasks where we will have to extend the radix from 8 bits to 16 bits, so that's what we are going to speak about.

To the left, 
Positive: we just add pad with zeros.
Negative: with the sign magnitude code, we replace the sign with zero and pad with zeros to the left, and then change the left-most bit with one.
For 2's complement, we copy everything, and we copy the MSB to all the padded positions from the left.

Minus one in 2's complement is all ones. Can I get a point for that?

To the right:
In all the codes we know, we just append the zeros.
The value does not change because we have the radix point.
i.e. $4 = 4.000 = 00004.0000$ and 

###### Shifts

In logical left shift, we will move all the numbers to the left, and we fill the missing positions with zeros. The number that 'fell off' is our carry.
This is not arithmetic, considering code, this is just the theory
In logical right shift, we will move all the numbers to the right, and we fill the missing positions with zeros. The number that 'fell off' is our carry.

A number shifted to the left is multiplied by 2.
In a general radix, a number shifted to the left is multiplied by the radix.
A number shifted to the right is divided by 2. In case of odd numbers, it rounds down.

Multiplication takes a lot more cycles than shifting.
Efficiently multiplying a number by a power of two, do left shift.
Same holds for division, as division is very complicated.
For example, in AVR, there is no division instruction.
// is there not a square root or a power instruction?

Then, arithmetic shifts are slightly different, in order to retain the arithmetic properties (for example, sign).
Everything works well for unsigned, but for signed numbers, it's a little more difficult (will be using frame extension).

In unsigned, carry = 1 means we experienced an overflow, meaning the result is not accurate. We would need to extend the radix by some bits in order to fit it.

In general, indication of incorrect result of an arithmetic operation. Overflow means the result is too big and cannot be fitted from the left. Completely wrong result indication. For unsigned numbers, equal to carry.
Precision loss is when the result is too small, cannot be fitted to the radix from the right. Imprecise result indication.
Check correctness of LShift by ensuring carry $\neq$ 1.
If we shift by two bits, check correctness by ensuring none of the carries are 1.

The arithmetic left shift:
for sign-magnitude code: shifts all the numbers to the left, except the leftmost bit, and the last bit before the sign bit is the overflow/carry.
For radix-complement: To check correctness, XOR of the two MSBs. Quite important trick.
For shifting n bytes, all n MSB must have the same value. Otherwise the sign would change, implying overflow.

The arithmetic right shift:
There is no overflow possible, but precision loss instead.
Some CPU's give the carry to some flag, put it somewhere...
You will always have precision loss for n right shifts if any of the n LSBs are one.
For 2's complement, the sign is copied twice, to the two MSBs in the result.
For n shift, to the n+1 MSBs on the result.

![[Pasted image 20260323194024.png]]

...

##### Cyclic Shifts (Rotations)

The bits are rotated. Performs no particular arithmetic operation, but can be used in arithmetic... Won't speak of this right now.
Rotation left shifts all the bits to the left, and MSB becomes LSB.
Rotation right shifts all bits to the right, and MSB becomes LSB.

It's possible to create the universal right shifter by one bit. Check lecture slides. :/

The barrel shifter (remember please) is used in CPU's for shifting, is a universal shifter. You can say by how many bits it can be shifted, which direction (right, left), and which type of shift (logic, cyclic (rotation), arithmetic)
It is a combinational circuit. Could be a question in the test.

#### Addition, Subtraction
Addition in radix complement... 
- RC(A+B) = RC(A) + RC(B)
- RC(A+B) = RC(A) + RC(B) - M
// which, when, what??

To indicate whether we have had overflow/underflow, match the polarities.
Positive + Negative cannot ever overflow/underflow.
Positive + Positive = Negative overflow
Negative + Negative = Positive underflow.
Reminder, there is no subtraction, there is just addition with negatives.

The overflow can occur in the two last additions in the ripple carry. Check slides.
$overflow = c_{out} \bigoplus c_{n-2}$ 
where $c_{out}=a_{n-1} b_{n-1}$ 

This is not inherent to the ripple carry adder.
Overflow and carry is different. Carry being 1 does not mean overflow necessarily...
Overflow means the result is wrong.
// but, if we have nowhere to put the carry, is it not overflow?

Subtraction, even for unsigned numbers, is nothing special.
Subtraction converted to addition of additive inverse.
$A>B$ assumed.
$A-B = A+(-B)$
$RC(-B)=M-RC(B)$
$RC(A)+RC(B)=RC(A)-RC(B)+M$

Negating all bits and adding one is very easy in hardware. 
Remember using this!...

Overflow is when we don't have a carry for computing $A-B$ when $A > B$
In subtraction, we call carry a borrow. The implementation is the same but we have different names.

XOR is a controlled inverter.

In sign magnitude code it is much more complicated.
The 2's complement code is much better used.

Multiplication.
It is a sequence of shifts and additions. That's how we did it in highschool.
That's the way it can be done and used in ALUs.
It is converted to addition + shifting.
Check slides, please...

Simplest, but slowest way.

// does unsigned subtraction not lose frame/range/size as we reserve one bit to sign?

Division is done as the same way as we are used in school. There really is no more efficient way. Check slides, please...

ALU is the Arithmetical Logical Unit. That is what performs all those operations we have talked about. It is being talked about in the ALU. We have seen it in the Von Neumann and Harvard architectures (REMEMBER THE DIFFERENCE).

Typically it has two operands, opcode, status, and output is result and status.
For floating point, we have FPU, not ALU.
Just know the ALU briefly for now.