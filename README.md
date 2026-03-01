\# RV32I 32-Bit RISC-V CPU – Single-Cycle (Logisim 2.7.1)



A 32-bit single-cycle RISC-V (RV32I subset) processor implemented structurally in Logisim.



This project was developed as part of a computer architecture course and implements a complete single-cycle core with verified control flow, memory operations, branching, and jump/return behavior (JAL/JALR).



---



\## Overview



The processor executes one instruction per clock cycle using a fully structural datapath design. All major components (ALU, Control Unit, Register File, Immediate Generator, Data Memory) are modularized and implemented as separate subcircuits.



The implementation follows the RV32I base integer instruction format and supports arithmetic, logical, control-flow, and memory instructions.



---



\## Supported Instruction Subset



\### Arithmetic \& Logical

\- ADD

\- SUB

\- ADDI

\- AND

\- OR

\- XOR

\- SLT



\### Memory

\- LW

\- SW



\### Control Flow

\- BEQ

\- JAL

\- JALR



---



\## Architectural Features



\### Single-Cycle Datapath

\- One instruction completed per clock cycle

\- Dedicated adders for:

&nbsp; - PC + 4

&nbsp; - PC + immediate (branch / JAL)

&nbsp; - rs1 + immediate (JALR)

\- Priority-based PC selection logic



\### ALU

\- Supports arithmetic, logical, and comparison operations

\- Controlled via ALUOp and funct3/funct7 decoding



\### Immediate Generator

Supports proper reconstruction and sign-extension for:

\- I-Type

\- S-Type

\- B-Type

\- U-Type

\- J-Type



\### Register File

\- 32 general-purpose registers

\- Dual read ports

\- Single write port

\- x0 permanently hardwired to zero



\### Data Memory

\- Byte-addressable memory

\- Word-aligned load/store operations



\### Jump Handling

\- JAL: PC = PC + immediate

\- JALR: PC = (rs1 + immediate) \& ~1

\- Correct return address storage (rd = PC + 4)



---



\## Project Structure



single-cycle/

│

├── cpu\_single\_cycle.circ # Top-level processor entry file

├── components/

│ ├── alu.circ

│ ├── alu\_control.circ

│ ├── main\_control.circ

│ ├── register\_file.circ

│ ├── immediate\_generator.circ

│ ├── branch\_unit.circ

│ └── data\_memory.circ

│

├── screenshots/

└── tests/



---



\## Verification



The single-cycle core was tested using a comprehensive instruction sequence that validates:



\- Arithmetic correctness

\- Logical operations

\- Load/store behavior

\- Branch taken path

\- JAL and JALR return behavior



Key observed results:



\- Correct arithmetic outputs

\- Branch correctly skips instructions when taken

\- JAL stores PC+4 into rd

\- JALR returns to the correct instruction address

\- Register x13 correctly updated after return



Full expected register and memory state is available in: single-cycle/tests/expected\_results.txt





---



\## How to Run



1\. Open Logisim 2.7.1

2\. Open:



&nbsp;  single-cycle/cpu\_single\_cycle.circ



3\. Load the provided memory image from the `tests` folder into instruction memory

4\. Run the clock



Ensure the folder structure is preserved so that all subcircuits load correctly.



---



\## Author



Kareem Elkenany  

Computer Engineering Student  

Egypt University of Informatics

