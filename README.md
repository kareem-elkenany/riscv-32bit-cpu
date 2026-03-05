# RV32I 32-Bit RISC-V CPU (Logisim)

A modular **32-bit RISC-V processor built in Logisim**, progressing from a **single-cycle architecture** to a **5-stage pipelined CPU**.

This project demonstrates the evolution of processor architecture, including reusable datapath components, control logic, and instruction verification tests.

---

## Project Overview

This repository implements a subset of the **RV32I instruction set architecture** and explores how processor design evolves from simple to more advanced implementations.

Two processor architectures are included:

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

This architecture serves as the baseline implementation before introducing pipelining.

#### Features

- RV32I instruction subset
- Modular datapath
- Immediate Generator
- Branch Unit
- Register File
- ALU and ALU Control
- Instruction Memory
- Data Memory
- Verified instruction test programs

Directory:

```
single-cycle/
```

---

### 5-Stage Pipelined CPU

The pipelined CPU improves performance by allowing multiple instructions to be processed simultaneously.

#### Pipeline Stages

1. **IF** — Instruction Fetch  
2. **ID** — Instruction Decode  
3. **EX** — Execute  
4. **MEM** — Memory Access  
5. **WB** — Write Back  

Pipeline registers propagate control signals and data between stages.

#### Features

- Pipeline registers between stages
- Modular datapath design
- Correct sequential instruction execution
- Clean separation of control and datapath

#### Current Limitations

- Hazard detection not implemented yet
- Data forwarding not implemented yet
- Cache system not implemented yet

Directory:

```
pipelined/
```

---

## Components

Reusable processor modules are located in each architecture’s `components` directory.

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

Instruction test programs are provided to verify processor correctness.

Tests validate:

- Register writes
- Arithmetic instructions
- Memory operations
- Branch behavior

Test programs are located inside:

```
tests/
```

Each test includes documentation explaining how to run it and what results to expect.

---

## Tools Used

- **Logisim Evolution**
- **RISC-V ISA Specification**
- Custom instruction test programs

---

## Future Improvements

Planned architectural improvements include:

- Hazard detection unit
- Data forwarding
- Pipeline stall logic
- Branch flushing
- Instruction cache
- Data cache

---

## Author

**Kareem Elkenany**  
Computer Engineering Student  
Egypt University of Informatics

---

## License

MIT License
