
# The Function of CPU Instruction Set Architectures (ISA)

We will learn how a processor works, and how to construct our own computer.
We know how to build basic building blocks, adders, multipliers, sequential circuits, etc. Today it will be about controllers, sequential circuits.

The ISA sits above the CPU architecture and I/O system, but below compiler and operating system.
Von Neumann architecture. Data memory and Instruction memory are stored in the same place. Will be in the exam.

A high level language is compiled into machine code, translated into binary instructions, translated into CPU signals.

Instruction Fetch (IF) reads instruction from memory.
Instruction Decode (ID) decodes the instruction opcode.
Operands Fetch (OF) reads the operands data from memory.
Instruction Execution (IE) executes the instruction
Write Back (WB) writes the result to memory.
That is what the control unit does.
Sometimes it is only divided into two parts, Fetch and Execute.

Will speak about bus (data-bussy) in a future lecture.
The ALU does calculations.
The control does unit data flow control.
Registers does data storage.

The simple CPU architecture...

Accumulator contains data in a single register.
Calculations are being done by the ALU. We already know what it looks like, we have an example.
Memory is connected by buses.
![[Pasted image 20260330191249.png]]

In the instruction fetch phase, we take the instruction code and save it in memory.
In the instruction decode phase, we look up our instruction, and typically the program counter is incremented by one.
In the operands fetch phase, typically the instruction has some data to work with. We have the instruction, we know what to do, so we want to have the data to work with; Then typically the instruction contains where to get the data. The operand is withdrawn from the memory and sent to the data bus to the ALU.
In the instruction execution phase, we send everything to the ALU, and then accumulate, storing the result in ACC.
In the last phase, in case there is no returning, we skip.
Interrupt phase?

That's it, that's how the CPU works.
No magic, going through an execution cycle.

# CPU Instructions -- Assembler

What is an instruction? It is some command, encoded as a number, binary. It determines what should be done, with what it should be done (operands), where to store the result, how and where to continue (can be specified explicitly, rarely, or implicitly, via Von Neumann model. The following instruction is executed.)
Operation code comes first, and then operands come afterwards.

There are many aspects that should be figured out.
Instruction format and encoding, operands size, location of operands and results, ISA operations, selection of the next instruction to be executed, memory organization, widths of the busses, registers, their organization.

In general, it is visualized as the opcode and operand(s).
For example, `c=a+b` could be written as Opcode, Operand 1, Operand 2, Result C.
We can also do a 2-address instruction, Opcode, Operand 1, Operand 2, being `a=a+b`.
We can also accumulate the working register, accumulator, by value.
By Opcode, Operand (a), resulting in `ACC=ACC+a` with a single operand.

The AVR is the CPU we will be working with in the labs. These examples will be coming from AVR architecture.
The MOV instruction copies the value of one register to another.
It does not move actually, it just copies.
For example, `mov Rd, Rr` - Instruction, Destination, Source.
The full instruction: `001011rdddddrrrr`
// the letters here are placeholders.
The beginning we have the opcode of the move instruction. Whenever the CPU sees this code, it knows the move instruction is being called. 
The `r` is the `Rr` and `d` is the `Rd`, total five bits for each. Note that they are... 'torn apart', split. The first value after the opcode is of `Rr`, then the all of `Rd`, then the rest of `Rr`.

The mapping is one-to-one. Though, it is easier to remember the names.

The assembler.
The machine code binary is translated back and forth into characters.
The level of abstraction is an advantage, the standardization, and the interface between low level SW and HW are advantages.
If you lean the assembler of one CPU, you will easily understand the others.
Most of the instruction sets are standardized.
Most likely, the move instruction will be implemented in different ways, so the hexadecimal will be different for example. Though, in assembler, it will be the same.

###### The Stack

Used in virtually every CPU.
Typically used as auxiliary data storage. Data passing, storing return address for subroutine calls, very temporary data storage.
It is Last In First Out (LIFO) memory.
Implementation in HW is a specialized register, or in main memory.
Operations include PUSH - store data to the top of the stack; and POP - withdraw the data.
Uses a specialized register stack pointer (SP).
The stack pointer points somewhere. In the beginning it points typically to the top of the stack. When the stack pointer is being filled, the stack pointer is decremented.
![[Pasted image 20260330193459.png]]

It is full when the SP is all the way down, causing Stack Overflow.
There are some CPU's where it is implemented in hardware, but in most places, even AVR, it is in the main memory.

###### Status Register Flags

The status flag stores information from the ALU, control unit, etc. It is essential for a lot of arithmetic operations. Flags include:
- Carry Flag `C`
- Zero Flag `Z`
- Negative Flag `N`
- Two's Complement Overflow `V`
- N $\bigoplus$ V for signed tests `S`
- Half Carry flag `H`
- Transfer bit used by BLD and BST instructions `T`
- Global Interrupt Enable/Disable flag `I`

`I T H S V N Z C`
###### Types of Instructions

Arithmetic and logic instructions where the ALU is involved, addition, subtraction, shifts, increments, etc.
Code execution order changing instructions including jumps, branch, subroutine, interrupts.
Data transfer instructions including moving data from/to registers/memory.
Bit set influencing the status register.
Stack manipulation instructions.

Today we will focus rather on:

#### Addressing Modes

How to access data in the CPU's.
Implicit addressing happens when, for example, there is just the opcode in the instruction. For example, the Clear Carry Flag `CLC` operation.
**Immediate** addressing (explicit) is when the operand is in the instruction and is constant.
For example, `LDI r16, 0x17` - set the register `r16` to `0x17`.
Here, for example, the value `0x17` is a constant.
`LDI` is "Loads Immediate".

The LSB in the flags register is the carry. It is useful to set it to zero or one. 
To set carry to zero, clear carry via `CLC`.

Whenever we hear **immediate**, it means there is a constant involved.

It is not necessary for the register number to appear, for example, in the situation of the accumulator.

**Direct** addressing there (explicit) is a register number in the instruction.
`INC r16` - increments `r16`
`MOV 10,r1` - loads the contents of `r1` and stores to `r0`.
Likewise, another type of direct addressing involves using the memory address.
`LD r16, my_data` or `LD r16,0x0100`
`LD` loads direct.
The content of the label `my_data` is nothing more nothing less than just the address.
Pretty much a macro?

**Indirect** addressing.
The instruction contains a register number, where there is memory address of the operand.
`LD` takes raw data from the memory to register. The data is pointed by another register.
For example, `LD r0, X`
`X` register is an actual thing that we will learn later.

There are some variations, including post/pre increment/decrement.
For example, `LD r0,X+` or `LD r0, -X`.

The post increment is useful when iterating over bytes for example.
For example, to display text, we need to read the first character, display it, then next, then next, then next, etc. We immediately increase `X` and then it is pointing at the next one, ready for our next call.

It could also happen, also in indirect addressing, where after the opcode there is an address, which points to an address, which finally points to an operand.

**Relative** addressing.
The operand address is obtained as a sum of some register value and offset.
The register is implicit, say, a program counter.
For example, `rjmp 10` will jump the code 10 bytes further.
It takes the value of the `PC`, pointer at the current instruction, and adds `10`. 
It is relative by the offset.
It needs not be just the case of relative jump.

**Index** addressing.
The operand address is obtained as a sum of two register values, base and index.
It is good for addressing different portions of memory in a simple way.
If we address the big portion of memory by the base, and then offset via the index, we get the operand. Via `Opcode R1, R2`.
That's similar to C arrays. i.e. `arr[i]` is equivalent to `i[arr]`


That was everything about how the machine code (opcode, operands) can be looking like.

### Instruction Set Architecture Types

Accumulator-oriented ISA: One main register used for computations.
Stack-oriented ISA: The operands are stored in stack.
General-Purpose Registers (GPR)-Oriented ISA: multi use.

The accumulator is the oldest, based on same principles for calculator.
Has simple context-switching.

Stack oriented ISA has a hardware stack, operands are stored in stack.
In the beginning, there were no floating point operations, and if we wanted those, we'd need to buy a specialized CPU.

The GPR orientated ISA is the prevalent architecture today.
It has multiple tenths multi purpose registers. In AVR we have 32.
Can be used interchangeably, no specialized registers like accumulator.

Registers flip flops are much faster than the main memory (DRAM).
It is good for storing local variables, many thousand times faster. Random access to registers, in contrast to stack.
Drawbacks include more complicated compilers, CPU state has a lot of information (values of registers), slow context switching.
The registers cannot contain more complex data structures, and cannot be access indirectly by pointers.

...

We should know from now on the basic blocks, CPU instruction cycle, instructions, addressing mods and ISA. This is basis for next week.