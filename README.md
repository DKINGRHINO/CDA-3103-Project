```markdown
# MySPIM - MIPS Processor Simulator

A single-cycle MIPS processor simulator written in C for **CDA 3103: Computer Logic and Organization** at the University of Central Florida (Fall 2024).

This project simulates the execution of a subset of MIPS instructions on a simplified single-cycle datapath. It demonstrates core computer architecture concepts including instruction fetch, decode, execution, memory access, and program counter updates.

## Project Overview

- Implements a functional MIPS-like processor simulator capable of running basic assembly programs provided in hexadecimal `.asc` files.
- Supports 14 MIPS instructions (add, sub, lw, sw, beq, bne, slti, etc.).
- Memory: 64 KB word-addressable, big-endian, word-aligned.
- Programs start at address `0x4000`.
- No exception or interrupt handling required.

The simulator is built around three main files:
- `spimcore.c` – Main driver and simulation loop (provided skeleton).
- `spimcore.h` – Function prototypes and control signal structure (provided).
- `project.c` – Student-implemented datapath functions (core of the project).

## My Contributions

As part of a team project, I was responsible for:
- Implementing the **ALU** function (low-level arithmetic and logic operations).
- Implementing **read_register** (register file read logic).
- Implementing **sign_extend** (16-bit to 32-bit sign extension for immediate values).
- Implementing **rw_memory** (load/store with word-alignment checks and halt-on-misalignment).
- Adding extensive **comments** throughout the code for clarity and maintainability.
- **Testing** the full simulator with various `.asc` test files.
- **Debugging and fixing bugs** across multiple functions (including those written by teammates).
- Performing **code formatting** and cleanup for consistency.

These components are critical to correct datapath operation and contributed significantly to the successful execution of MIPS programs.

## How to Build and Run

### Requirements
- GCC compiler
- Linux, macOS, or Windows

### Compilation
```bash
gcc -o spimcore spimcore.c project.c
```

### Execution
```bash
./spimcore <input_file.asc>
```

The program provides an interactive command-line interface:
- `s` – Step one instruction
- `c` – Continue until halt
- `r` – Display registers
- `m <start> <end>` – Display memory contents
- `h` – Check halt status
- `x` – Quit

Sample `.asc` files can be created manually with hexadecimal MIPS machine code (one instruction per line).

## Credits & Attribution

- Skeleton code (`spimcore.c`, `spimcore.h`) and project guidelines provided by the UCF CDA 3103 teaching staff.
- Original project concept and structure credit to course instructors (Sarah Angell, Jerrett Longworth, and others).
- This repository is a fork of our team project repository.
- Implemented as a team academic project – shared here for portfolio and demonstration purposes only.

## License / Usage Note

This code was developed as part of coursework at the University of Central Florida. It is shared publicly for portfolio purposes and to demonstrate understanding of computer architecture concepts. Feel free to view and learn from it, but please do not use it to complete active assignments in CDA 3103 or similar courses.

---

**Christopher Otto**  
Computer Science B.S. Candidate, Class of 2027  
University of Central Florida
