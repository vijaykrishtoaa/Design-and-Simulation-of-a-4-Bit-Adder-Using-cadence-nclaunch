# Ex No: 07 - Design and Simulation of a 4-Bit Adder Using Verilog and Cadence nclaunch

## Aim
The aim is to design and simulate a **4-bit Adder** using **Verilog HDL** and verify its functionality using **Cadence nclaunch** for simulation.

---

## Tools Required
### Cadence EDA Suite
- **nclaunch** (for functional and timing simulation)

### Hardware Requirements
- Minimum **4GB RAM** and a **multi-core processor**

---

## Procedure

### 1. Writing Verilog Code:
- Create a new Verilog module for the **1-bit Full Adder**.
- Implement a **ripple carry adder** using **four 1-bit full adders** to form a **4-bit Adder**.
- Define input ports (**A[3:0], B[3:0], Cin**) and output ports (**Sum[3:0], Cout**).

### 2. Simulation Using Cadence nclaunch:
- Open **nclaunch** and load the Verilog file.
- Compile the design and check for **syntax errors**.
- Write a **testbench** to apply different input combinations.
- Run the **simulation** and observe the **waveforms**.
- Verify that the output sum and carry are correct for all cases.

---

## Verilog Code for 1-Bit Full Adder
```verilog
module full_adder (
    input A, B, Cin,
    output Sum, Cout
);
    assign Sum = A ^ B ^ Cin;
    assign Cout = (A & B) | (B & Cin) | (A & Cin);
endmodule
```

## Truth Table for 1-Bit Full Adder

![image](https://github.com/user-attachments/assets/0ea58111-49fb-49a4-ad6a-ee36cbf4e479)

## Verilog Code for 1-Bit Full Adder
```verilog
module adder_4bit (
    input [3:0] A, B,
    input Cin,
    output [3:0] Sum,
    output Cout
);
    wire C1, C2, C3;

    full_adder FA0 (A[0], B[0], Cin, Sum[0], C1);
    full_adder FA1 (A[1], B[1], C1, Sum[1], C2);
    full_adder FA2 (A[2], B[2], C2, Sum[2], C3);
    full_adder FA3 (A[3], B[3], C3, Sum[3], Cout);
endmodule
```
## Truth Table for 4-Bit Full Adder

![image](https://github.com/user-attachments/assets/5b5083dc-3c4c-484b-bc07-28f16cda1139)

## Simulation Results
### Simulation Waveforms
(Insert waveform screenshot here)

## Results
Successfully designed the 1-bit Full Adder and 4-bit Adder using Verilog HDL.
Simulated the design using Cadence nclaunch and verified the output.
Observed correct addition functionality for all test cases.


