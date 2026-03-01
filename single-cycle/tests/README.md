# Test Programs

## full_instruction_test

Covers:
- ADD, SUB, ADDI
- AND, OR, XOR
- SLT
- SW, LW
- BEQ
- JAL, JALR

Expected final state is documented in `expected_results.txt`.

To run:
1. Load the corresponding file into instruction memory.
2. Execute until program returns via JALR.