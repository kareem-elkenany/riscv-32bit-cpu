# RV32I 32-Bit RISC-V CPU (Logisim)

A modular **32-bit RISC-V processor implemented in Logisim**, progressing from a **Single-Cycle architecture** to a **5-Stage Pipelined CPU**.

This repository demonstrates the architectural evolution of a processor, including reusable datapath components, control logic, and instruction tests.

---

## Project Overview

This project implements a subset of the **RV32I instruction set architecture** and explores how processor designs evolve from simple to more advanced implementations.

Two CPU architectures are included:

| Architecture | Status |
|--------------|--------|
| Single-Cycle CPU | Fully working |
| 5-Stage Pipelined CPU | Working datapath (hazard detection and cache pending) |

---

## Repository Structure

```
riscv-32bit-cpu
│
├── single-cycle
│   ├── cpu_single_cycle.circ
│   ├── components
│   ├── tests
│   └── screenshots
│
├── pipelined
│   ├── cpu_pipelined.circ
│   ├── components
│   ├── tests
│   └── screenshots
│
└── README.md
```

---

## Implemented Architectures

### Single-Cycle CPU

The single-cycle processor executes **one instruction per clock cycle**.

This architecture serves as the foundational design before introducing pipelining.

Features:

- RV32I instruction subset
- Modular datapath
- Immediate generator
- Branch unit
- Register file
- ALU and ALU control
- Instruction memory
- Data memory
- Verified instruction tests

Directory:

```
single-cycle/
```

---

### 5-Stage Pipelined CPU

The pipelined processor improves performance by overlapping instruction execution.

Pipeline stages:

1. **IF** — Instruction Fetch  
2. **ID** — Instruction Decode  
3. **EX** — Execute  
4. **MEM** — Memory Access  
5. **WB** — Write Back  

Features:

- Pipeline registers between each stage
- Modular datapath design
- Control signals propagated through pipeline registers
- Working sequential pipeline execution

Current limitations:

- Hazard detection not implemented yet
- Data forwarding not implemented yet
- Cache system not implemented yet

Directory:

```
pipelined/
```

---

## Components

Reusable processor modules exist inside each architecture’s `components` directory.

Examples include:

- ALU
- ALU Control
- Branch Unit
- Immediate Generator
- Main Control
- Register File

These modules are designed to be reusable between architectures.

---

## Testing

Instruction programs are provided to verify processor correctness.

Tests validate:

- Register writes
- Arithmetic operations
- Memory access instructions
- Branch instructions

Test files are located inside:

```
tests/
```

Each test includes documentation explaining how to run it and what results to expect.

---

## Tools Used

- Logisim Evolution
- RISC-V ISA Specification
- Custom instruction test programs

---

## Future Improvements

Planned architectural upgrades include:

- Hazard detection unit
- Data forwarding
- Pipeline stall logic
- Branch flushing
- Data cache

---

## Author

**Kareem Elkenany**  
Computer Engineering Student  
Egypt University of Informatics

---

## License

MIT License