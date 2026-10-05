# 32-bit-ALU--Verilog-vivado
32-bit-ALU-Verilog-Vivado
design and Verification of a 32bit ALU using Verilog HDL and AMd Vivado

32-bit ALU Design and Verification using Verilog HDL
📌 Project Overview
This project presents the design and verification of a 32-bit Arithmetic Logic Unit (ALU) using Verilog HDL and AMD Vivado 2026.1.

The ALU is a combinational digital circuit that performs arithmetic, logical, shifting, and comparison operations on 32-bit binary operands.

The design was developed and verified using a Verilog testbench and Vivado Behavioral Simulation. The project also includes RTL analysis, synthesis, FPGA implementation, resource utilization analysis, timing analysis, power estimation, and DRC verification.

🎯 Objectives
Design a 32-bit combinational ALU using Verilog HDL.
Implement arithmetic, logical, shift, and comparison operations.
Develop a Verilog testbench for functional verification.
Perform behavioral simulation using AMD Vivado.
Analyze the RTL schematic and synthesized design.
Perform FPGA implementation.
Analyze resource utilization, timing, and power reports.
Document the complete RTL design and verification flow.
🛠️ Tools and Technologies
Verilog HDL
AMD Vivado 2026.1
Vivado Simulator
Behavioral Simulation
RTL Analysis
FPGA Synthesis and Implementation
GitHub
🧩 ALU Interface
Inputs
Signal	Width	Description
A	32 bits	First operand
B	32 bits	Second operand / shift amount source
ALU_Sel	4 bits	Selects the required ALU operation
Output
Signal	Width	Description
Result	32 bits	Result of the selected operation
⚙️ Supported ALU Operations
The operation is selected using the 4-bit ALU_Sel input.

ALU_Sel	Operation	Function
0000	Addition	A + B
0001	Subtraction	A - B
0010	AND	A & B
0011	OR	A | B
0100	XOR	A ^ B
0101	NOT	~A
0110	Shift Left	A << B[4:0]
0111	Shift Right	A >> B[4:0]
1000	Comparison	1 when A < B, otherwise 0
🏗️ ALU Architecture
The ALU is implemented as combinational RTL using Verilog HDL.

Conceptually, the design consists of multiple arithmetic and logical operation blocks whose outputs are selected according to the ALU_Sel control signal.

The supported functions include:

Addition
Subtraction
AND
OR
XOR
NOT
Logical left shift
Logical right shift
Comparison
The operation selection is implemented using combinational logic.

🧪 Functional Verification
A dedicated Verilog testbench was developed to verify the ALU functionality.

The testbench applies different combinations of:

A
B
ALU_Sel
and observes the resulting Result.

The behavioral simulation tests all nine supported operations.

Representative Test Cases
Operation	Inputs	Expected Result
Addition	10 + 5	15 (0x0000000F)
Subtraction	10 - 5	5 (0x00000005)
AND	0x0F & 0x03	0x00000003
OR	0x0F | 0x03	0x0000000F
XOR	0x0F ^ 0x03	0x0000000C
NOT	~0x0000000F	0xFFFFFFF0
Shift Left	1 << 2	4
Shift Right	16 >> 2	4
Comparison	5 < 10	1
📊 Simulation
Behavioral simulation was performed using Vivado Simulator.

The supplied simulation waveform covers ALU_Sel values from 0 through 8 over a 90 ns simulation period.

The main signals observed in the waveform are:

A[31:0]
B[31:0]
ALU_Sel[3:0]
Result[31:0]
