Design and Verification of 32-bit ALU

📌 Project Overview

This project presents the design and verification of a 32-bit Arithmetic Logic Unit (ALU) using Verilog HDL and AMD Vivado.

The ALU is a combinational digital circuit that performs arithmetic, logical, shifting, and comparison operations on two 32-bit input operands.

The project was developed as part of an internship at Vaidsys Technologies and demonstrates the complete basic RTL design flow, including:

- RTL design
- Verilog HDL coding
- Functional verification
- Behavioral simulation
- RTL elaboration
- Synthesis
- FPGA implementation
- Resource utilization analysis
- Timing analysis
- Power estimation
- Design Rule Check (DRC)

🎯 Objectives

- Design a 32-bit combinational ALU.
- Implement arithmetic and logical operations using Verilog HDL.
- Develop a testbench for functional verification.
- Verify all supported operations using simulation waveforms.
- Perform RTL elaboration and synthesis using Vivado.
- Implement the design on the selected FPGA device.
- Analyze FPGA resource utilization, timing and power reports.
- Understand the complete RTL-to-FPGA design workflow.

⚙️ ALU Operations

The ALU supports 9 operations controlled by a 4-bit "ALU_Sel" input.

ALU_Sel| Operation| Function
"0000"| Addition| "A + B"
"0001"| Subtraction| "A - B"
"0010"| AND| "A & B"
"0011"| OR| "A | B"
"0100"| XOR| "A ^ B"
"0101"| NOT| "~A"
"0110"| Shift Left| "A << B[4:0]"
"0111"| Shift Right| "A >> B[4:0]"
"1000"| Comparison| "1" when "A < B"

🔌 Input and Output

Signal| Width| Direction| Description
"A"| 32-bit| Input| First operand
"B"| 32-bit| Input| Second operand / shift amount
"ALU_Sel"| 4-bit| Input| Selects ALU operation
"Result"| 32-bit| Output| Result of selected operation

🏗️ Architecture

The ALU uses a combinational RTL architecture.

Conceptually, the design consists of multiple operation blocks working in parallel. The "ALU_Sel" signal selects the required operation and drives the corresponding result to the output through selection logic.

Basic Flow

        A[31:0] ─────────────┐
                             │
        B[31:0] ─────────────┤
                             ▼
                  ┌──────────────────┐
                  │   ALU Operations │
                  │                  │
                  │ ADD              │
                  │ SUB              │
                  │ AND              │
                  │ OR               │
                  │ XOR              │
                  │ NOT              │
                  │ SHIFT LEFT       │
                  │ SHIFT RIGHT      │
                  │ COMPARISON       │
                  └────────┬─────────┘
                           │
                     ALU_Sel[3:0]
                           │
                           ▼
                    ┌─────────────┐
                    │   Selector  │
                    └──────┬──────┘
                           │
                           ▼
                     Result[31:0]

🛠️ Tools and Technologies

- Verilog HDL
- AMD Vivado 2026.1
- Vivado Simulator
- FPGA RTL Design
- Functional Verification
- Synthesis and Implementation

🔄 Design Methodology

1. Define the ALU operations and input/output interface.
2. Develop the 32-bit ALU using Verilog HDL.
3. Implement operation selection using combinational logic.
4. Develop a Verilog testbench.
5. Apply different operands and operation-select values.
6. Perform behavioral simulation.
7. Verify the output waveform.
8. Perform RTL elaboration.
9. Run synthesis.
10. Perform FPGA implementation.
11. Analyze utilization, timing, power and DRC reports.

🧪 Functional Verification

The testbench verifies all nine supported operations by applying different values of "A", "B", and "ALU_Sel".

Example verification cases:

Operation| Inputs| Expected Result
ADD| "10 + 5"| "15"
SUB| "10 - 5"| "5"
AND| "0x0F & 0x03"| "0x03"
OR| "0x0F | 0x03"| "0x0F"
XOR| "0x0F ^ 0x03"| "0x0C"
NOT| "~0x0F"| "0xFFFFFFF0"
Shift Left| "1 << 2"| "4"
Shift Right| "16 >> 2"| "4"
Comparison| "5 < 10"| "1"

The supplied Vivado behavioral waveform covers "ALU_Sel" values from "0" to "8" over a 90 ns simulation period.

📊 FPGA Resource Utilization

The implementation report showed:

Resource| Used| Available| Utilization
Slice LUTs| 315| 20,800| 1.51%
Slices| 87| 8,150| 1.07%
LUT as Logic| 315| 20,800| 1.51%
Bonded IOB| 100| 106| 94.34%

The logic resource utilization is relatively low, while I/O utilization is high because the design exposes two 32-bit inputs, one 4-bit select input and one 32-bit output.

⏱️ Timing Analysis

The timing report showed no failing endpoints. However, the project does not contain user-specified timing constraints.

Therefore, this project does not claim a verified maximum operating frequency.

For a future pipelined or registered version, appropriate clock and input/output timing constraints can be added.

⚡ Power Analysis

Vivado reported an estimated total power of approximately 18.019 W with a low confidence level.

This value should be considered a tool estimate under incomplete switching-activity assumptions, rather than measured hardware power consumption.

✅ DRC Result

The final Design Rule Check was completed successfully with:

No Violations Found

Earlier FPGA constraint warnings were addressed during the project workflow.

📁 Suggested Repository Structure

32-bit-ALU-Verilog/
│
├── README.md
├── rtl/
│   └── alu_32bit.v
│
├── testbench/
│   └── alu_32bit_tb.v
│
├── simulation/
│   └── waveform/
│
├── vivado/
│   └── project_files/
│
├── results/
│   ├── rtl_schematic.png
│   ├── simulation_waveform.png
│   ├── synthesis.png
│   ├── implementation.png
│   └── utilization_report.png
│
└── docs/
    └── Internship_Report.pdf

📚 Learning Outcomes

Through this project, the following skills were developed:

- Verilog HDL RTL coding
- Combinational digital design
- Testbench development
- Functional verification
- Vivado simulation
- RTL schematic analysis
- FPGA synthesis
- FPGA implementation
- Resource utilization analysis
- Timing report interpretation
- Power report interpretation
- DRC analysis

These outcomes are consistent with the internship report's documented learning outcomes.

🚀 Future Enhancements

Possible improvements include:

- Add "Carry", "Zero", "Overflow", "Borrow" and "Negative" flags.
- Add multiplication and division operations.
- Add arithmetic right shift.
- Introduce pipelining.
- Develop a self-checking testbench.
- Add assertion-based verification.
- Use constrained-random test vectors.
- Improve power estimation using realistic switching activity.
- Implement and test the ALU on an FPGA development board.
- Compare different architectures based on area, delay and power.

👨‍💻 Author

BHANUPRAKASH K A

Electronics and Communication Engineering
JSS Academy of Technical Education, Bengaluru

Internship Organization

Vaidsys Technologies

Internship Project

Design and Verification of 32-bit ALU

📄 Project Report

The detailed internship report is included in the repository under the "docs/" directory.

---

⭐ If you found this project useful, consider giving the repository a star!
