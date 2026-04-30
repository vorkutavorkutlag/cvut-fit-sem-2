
# INTERRUPTS

Occur at the end of the cycle, check slides for visualization.
They come from the idea that I/O devices are independent of the CPU/processor, and if we want to communicate, we need it to have some way of protocol.

The CPU does not know about the connection I/O.
Need for syncing of the devices and CPU.
The I/O invokes an interrupt when some action should be taken.
Then an interrupt handler (**Interrupt Service Routine** - **ISR**) is called a subroutine servicing the interrupt.
The normal code execution is interrupted and the interrupt handler is ran.

###### Interrupt Types
**External** (asynchronous) interrupts.
Called by I/O devices, maskable.
Can be disabled by the interrupt controlled. keyboard stroke, interrupt from timer, buttons (in AVR).

Non-maskable (NMI).
Cannot be disabled, must be serviced. 
For example, system errors, memory corruption - parity errors.

When these happen, the "normal" code execution is typically terminated.

**Internal** (software, synchronous) interrupts.
Planned by the programmer. (INT instruction) 
Called by the user (program).
Error indication (exception calls), debugging.

Called by CPU.
For example, division by zero, page fault.

Interrupts can technically by be interrupted by another interrupt but shouldn't be.

Interrupt controller generates INT, interrupt request, and gets answered by INTA, interrupt acknowledgement. Interruption specification moves through the Data Bus.

Look at the interrupt controller in x86 architecture on the slides...

Masking interrupts, in AVR, the FLAG I.
`SEI`, `CLI` instructions.
The global interrupt enable/disable flag, `I`

Interrupt vector table, typically in the beginning of program memory, dedicated address for each interrupt source. Only small space left for your code, jut for `jmp`.

For subroutine call, place and reason for call is known.
Interrupt call is unknown.
Pushed to stack PC, in interrupt call, PC + possibly `SREG`.
Return: `RET` as opposed to `RETI`

###### Recommendations

Forbid interrupt during interrupts.
- Place `CLI` at the beginning of the handler.

Do not modify registers.
- At the beginning, store `SREG` and all registers used by handler to the stack, restore them to the end (LOOK AT THE SLIDES FOR EXAMPLE)

Data passing
- Do not use registers to pass data from/to the main code.
- use variables in data memory for this purpose (huh?)

Be fast. The interrupt handler should be as fast, short as possible.

# I/O Devices
Closely related to the interrupts.
We have seen the Von Neumann model before, where memory is not separated.

It is typically connected by some bus or buses.
Three types include data bus, address bus, control bus.

There are registers `r0`-`r31`.
64 I/O registers, accessible by `in`, `out`.
160 external I/O registers.
The rest is free memory.

We will be using buttons in our labs. If we want to read what button has been pressed, we have to look into some value in the memory and read the button.
// is it debounced?

The communication with I/O is through **ports**.
In AVR, in, out instructions.

To summarize,
They have reserved memory space.
Possibly special I/O instructions.

It can take more time for the I/O device to react.
The instruction waits until the operation is completed, or, the program execution continues even though the operation is not finished. Sometimes there is a possibility to read the status of the I/O or the end of the operation is indicated by an interrupt.

# Buses
Check the lecture slides for the diagram.
Everything is connected by buses, so much stuff...
Memory, ALU, registers, I/O lines.
We are skipping over important topics but dragging boring trivia.

In current PC architectures, multiple busses, hierarchical. Northbridge-Southbridge.
Note in modern CPUs, the northbridge is integrated in CPU package.


Standard CMOS states cannot be used to feed the bus. The output is either log.
There would be 0-1 conflicts.
The solution is three state logic, being `0`, `1`, `Z` values.
Implementation is with a 3 state buffer, with Enable input, or, open collector (TTL tech)

Terminology includes:
- Bus master. The device initiating the bus transaction and driving the control bus, CPU.
- Bus slave. The device performing the bus transaction, specified by the control bus, memory and I/O interface circuit, etc.
- Talker, source, the device sending the data to the bus. Only one talker at a time.
- Listener (destination), the device receiving data from the data bus.

Bus arbitration.
Who says which device has access to the bus.
Centralized busses... The **bus arbiter** (controller) says who accesses the bus.
Can be a part of the CPU.
Daisy chain, polling, fixed priority...

A bus is not a bunch of wires, it is a protocol.
A set of signals and rules to connect devices.
Typical buses include address, data, control. The first two can be shared, multiplexed.
Typical operations include read, write, read-modify-write, etc., not too relevant.

Bus types include serial and parallel.
Only one data lines, or as many data signals as there are data bits.
Data transmitted serially, or in parallel.
Serial: USB, PCI.
Parallel: ISA, PCI.

Synchronous buses are driven by a clock. USB, PCI...
Expecting to have data every cycle.

Pseudo-Synchronous.
same as Synchronous, special waiting signals. SCSI...

Asynchronous are driven by a sync signal - handshake.  RS 232..
A fully fledged protocol.

...

Basic parameters of buses.
- Bandwidth (bits). With serial, only 1.
- Frequency (HZ). For asynchronous.
- Throughput (he skipped this.)

