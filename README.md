# EXPERIMENT 03 HALF SUBTRACTOR AND FULL SUBTRACTOR
## IMPLEMENTATION OF HALF SUBTRACTOR AND FULL SUBTRACTOR CIRCUIT
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## EQUIPMENT'S REQUIRED:
1. Hardware – PCs, Cyclone II , USB flasher  
2. Software – Quartus prime
## THEORY:
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## HALF SUBTRACTOR AND FULL SUBTRACTOR:
### HALF SUBTRACTOR
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Difference = A'B+AB' = A ⊕ B  
Borrow=A'B

### FULL SUBTRACTOR
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Difference = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin  
Borrow=A'B+A'C+BC

## PROCEDURE:
1. Connect the supply (+5V) to the circuit
2. Switch ON the main switch
3. If the output is 1, then the led glows.
## PROGRAM:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.  
Developed by: RITHIGA SRI.B  
RegisterNumber:  212221230083

VERILOG PROGRAMMING FOR HALF SUBTRACTOR:

module halfsub(A,B,diff,borrow);  
input A,B;
output diff,borrow;  
wire X;  
xor(diff,A,B);  
not(X,A);  
and(borrow,X,B);  
endmodule

VERILOG PROGRAMMING FOR FULL SUBTRACTOR:

module fullsub(A,B,C,diff,borrow);  
input A,B,C;  
output diff,borrow;   
wire p ;  
assign diff = A ^ B ^ C;   
not(p,A);   
assign borrow = ((p&B)|(p&C)|(B&C));  
endmodule
*/

## OUTPUT:
### HALF SUBTRACTOR:
### TRUTH TABLE
![output](./halftruth.png)
###  RTL REALIZATION
![output](./half.png)
### TIMING DIAGRAM
![output](./halftiming.png)

## FULL SUBTRACTOR:
### TRUTH TABLE
![output](./fulltruth.png)
###  RTL REALIZATION
![output](./full.png)
### TIMING DIAGRAM
![output](./fulltiming.png)

## RESULT:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
