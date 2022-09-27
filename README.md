# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'
## Combimation 1

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'
##combination 1
## Program:
~~~
module exp4(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(~c & b & a);
assign q=(~d & c & c & a);
assign r=(c & ~b & a);
assign f=(~(~p & ~q & ~r));
endmodule
~~~
## RTL realization
![exp4](https://user-images.githubusercontent.com/94506182/192531151-b3d75458-2483-47ff-b6b0-aa2283e150b9.png)
## waveform
![wave (2)](https://user-images.githubusercontent.com/94506182/192534402-f61c08fa-bcd4-4d46-917e-0e64bf139d0f.jpeg)

## Truthtable
![truth](https://user-images.githubusercontent.com/94506182/192531964-24bb47fc-563f-4aaf-a92a-68a50bd6d4c4.jpeg)


## Combination 2
## Program
~~~
module exp4(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(c & ~b & a);
assign q=(d & ~c & a);
assign r=(c & ~b & a);
assign f=((p | q & |r));
endmodule
~~~
## RTL
![com 2 RTL](https://user-images.githubusercontent.com/94506182/192535255-7a388b5b-99df-409c-b289-72eb269d7d9e.png)

## Timing Diagram
![w](https://user-images.githubusercontent.com/94506182/192535483-fb5a899d-17ce-4f78-8b80-e62dc5b58aa4.jpeg)
## Truth table
![true](https://user-images.githubusercontent.com/94506182/192536648-29c09fdc-c528-44eb-bd73-cedb438abc68.jpeg)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
