# Palindrome-Detectror-Verilog
PROJJECT TITLE : 
Palindrome Detector using Verilog HDL

OBJECTIVE : 

The aim of this project is to design a digital circuit that detects whether a sequence of 4 consecutive input bits forms a palindrome.

PROBLEM STATEMENT : 

A palindrome is a sequence that reads the same forward and backward. In this project, the system continuously receives a serial input bit (x) and checks whether the last four bits form a palindrome.

EXAMPLES OF VALID PALINDROMES :

1001
0110
1111
0000

APPROACH : 
The design uses a combination of a finite state machine (FSM) and a shift register:

A 4-bit shift register is used to store the most recent inputs.
The FSM structure is maintained mainly for synchronization and control, similar to standard sequence detector designs.
Once four bits are received, the circuit checks:
First bit equals last bit
Second bit equals third bit

If both conditions are satisfied, the output y becomes 1.

INPUTS AND OUTPUTS : 

clk : Clock signal
reset : Asynchronous reset
x : Serial input bit
y : Output signal (1 when palindrome detected)
