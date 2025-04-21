# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**
![Screenshot 2025-04-21 191044](https://github.com/user-attachments/assets/202f354a-4866-426b-a11a-6b7515214c1e)


**Procedure**
 Full Adder: Inputs: Three inputs: A, B (the two bits to be added), and Cin (the carry-in bit from a previous addition). Outputs: Two outputs: Sum (the resulting sum) and Cout (the carry-out bit). Logic: Sum = A ^ B ^ Cin (XOR operation). Cout = (A & B) | (A & Cin) | (B & Cin) (carry occurs if at least two inputs are 1). Full Subtractor: Inputs: Three inputs: A, B (the two bits, where A - B is calculated), and Bin (the borrow-in from a previous subtraction). Outputs: Two outputs: Diff (the resulting difference) and Bout (the borrow out bit). Logic: Diff = A ^ B ^ Bin (XOR operation). Bout = (~A & B) | ((~A | B) & Bin) (borrow occurs if A is less than B or needs a borrow). Both circuits follow simple XOR logic for the primary result and AND-OR logic to determine carry or borrow conditions

**Program:**

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 
Developed by:MOPURI SARADEEPIKA

RegisterNumber:212224040201

```
module Fulladder(sum, cout, a, b, cin);
    output sum;
    output cout;
    input a;
    input b;
    input cin;

	 wire w1,w2,w3;
	 assign w1=a^b;
	 assign w2=a&b;
	 assign w3=w1&cin;
	 assign sum=w1^cin;
	 assign cout=w2|w3;
endmodule
```

```
module fullsubtractor (df,bo,a,b,bin);
output df;
output bo;
input a;
input b;
input bin;
wire w1,w2,w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(~w1&bin);
assign df=w1^bin;
assign bo=w2|w3;
endmodule
```


**RTL Schematic**
![Screenshot 2025-04-21 191422](https://github.com/user-attachments/assets/02141417-5990-4b0c-bb1c-cb9052427908)
![Screenshot 2025-04-21 191528](https://github.com/user-attachments/assets/36c8607f-b4b8-495e-b801-4ba3e1a4e3be)



**Output Timing Waveform**
![Screenshot 2025-04-21 191619](https://github.com/user-attachments/assets/d0d2dfe4-049f-4a5b-a933-fbd8b558f9af)
![Screenshot 2025-04-21 191710](https://github.com/user-attachments/assets/e97dff7c-5324-4746-8ebc-a6f454e5ef45)



**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



