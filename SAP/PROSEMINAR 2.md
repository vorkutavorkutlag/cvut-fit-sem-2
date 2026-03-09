We will be doing modulo 5. Previous one was modulo 4.
We have five states, 0 1 2 3 4, and that's all, back to 0.
Also, we will include the enable signal, enabling the counting.

We will have a single primary input, being the enable signal.
We will need three primary outputs, since four in binary is `1 0 0`.
We will need three DFF. For 5 states, the minimum DFF is 3 $= ceil(log_2 5)$ 
That is because one DFF remembers one bit. Then, same case with PO.

We have one combinational part, with enable as the input.
Of sequential, we have three flip flops, the (three) outputs of which are going into the combinational part, and the inputs which are coming out of the combinational part.
The output, if we go with Moore, will come out of the sequential part, out of the outputs of the DFFs.
Side-note, DFF inputs/outputs usually denoted as $d_i~/~q_i$  respectively.

Constructing the STT, let's encode each state as the binary representation of the number it corresponds to `(0..4)`. 
It will depend on enable. If EN is off, then the state goes back to itself (waits) (LIKE SEQUENTIAL, SYNCHRONOUS, GET IT?? BECAUSE IT HAS TO WAIT??? WOW I CAN'T BELIEVE I ONLY NOW REALIZE WHY IT'S CALLED THAT!!!!). 
Otherwise, if EN is on, it proceeds to the next state.
The output at each entry will be the binary representation of the number the current state corresponds to. It will be equal to the encoding of states in this case.

We don't actually need the STT. We can import the counter behavior directly into the truth table.

We translate the STT to a truth table and create a K-map for each PO bit.
