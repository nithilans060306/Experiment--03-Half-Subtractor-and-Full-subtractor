## Name:Ashwath M
## Reference number:23000309
# Experiment 04 Half Subtractor and Full subtractor
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
1.	Create a New Project:

  	  o	Open Quartus and create a new project by selecting "File" > "New Project Wizard."

  	  o	Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).
3.	Create a New Design File:

  	  o	Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."

  	  o	Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.
5.	Write the Combinational Logic Code:

  	  o	Open the newly created Verilog or VHDL file and write the code for your combinational logic.
7.	Compile the Project:

  	  o	To compile the project, click on "Processing" > "Start Compilation" in the menu.

  	  o	Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.
9.	Analyze and Fix Errors:

  	  o	If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.

  	  o	Review and fix any issues in your code if necessary.

  	  o	View the RTL diagram.
11.	Verification:

   	  o	Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".

   	  o	Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.

   	  o	Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.


## Program:
#### Half Subtractor:
```
module fulladder(diff,a,b,carry);
input a,b;
output diff,carry;
xor(diff,a,b);
and(carry,a,b);
endmodule
```
#### Full Subtractor:
```
module fullsub(diff,carry,a,b,c);
input a,b,c;
output diff,carry;
xor(diff,a,b,c);
assign carry= (~a)&c | (~a)&b | (b&c);
endmodule
```
##  RTL realization
#### Half Subtractor:
![experiment4 halfsubtractor rtl](https://github.com/Ashwathm12/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849225/87e774ac-6a86-4a51-b94a-a4901ea7bbc5)

#### Full Subtractor:
![experiment4 fullsubtractor rtl](https://github.com/Ashwathm12/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849225/4ce52309-b0be-490a-aa07-ebd037b7c5de)

## Truth table
#### Half Subtractor:
![experiment4 halfsubtractor truth table](https://github.com/Ashwathm12/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849225/aa1e0013-b2c4-4695-8665-744365bb23be)

#### Full Subtractor:
![experiment4 fullsubtractor truthtable](https://github.com/Ashwathm12/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849225/ea34a41b-3f66-4c83-bf32-e4f550f2fa50)

## Timing Diagram
#### Half Subractor:
![half diagram](https://github.com/Ashwathm12/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849225/436e2025-c944-4084-92be-2e283861c52a)

#### Full Subtractor:
![DE Experiment 4(fs) Waveform output](https://github.com/Ashwathm12/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/147473026/f2c6f479-c3d5-4610-855e-8ffd41098946)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
