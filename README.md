# Pipelined Processor for Sorting Arrays

## Project Overview
This project involves the creation of a 5-stage pipelined processor using Verilog HDL, designed to execute a sorting algorithm for arrays written in RISC-V assembly language.

### Objective
The primary aim is to enhance processor architecture by:
1. Implementing a sorting algorithm in RISC-V assembly on a single-cycle processor.
2. Transitioning to a 5-stage pipelined processor to achieve faster execution times and efficiency.

### Project Structure
1. **Single-Cycle Implementation:** Develop a foundational single-cycle processor.
2. **Integration of Pipelining:** Modify the single-cycle design to incorporate a 5-stage pipeline for improved execution speed.
3. **Comprehensive Documentation:** Each phase of the project is thoroughly documented.

### Instruction Memory Module
The provided Verilog module, "Instruction_Memory," is responsible for storing instructions for the processor. It includes an array "inst_mem" initialized with specific instructions, and an "always" block that outputs the corresponding instruction based on the input address. This module is crucial for feeding instructions to the processor, facilitating the execution of tasks such as a bubble sort algorithm.

### Pipelining in Processor Design
Transitioning from a single-cycle method to pipelining addresses idle periods during instruction execution. The RISC-V processor framework uses a five-stage pipeline, dividing instruction execution into distinct phases:

1. **IF (Instruction Fetch)**
2. **ID (Instruction Decode)**
3. **EX (Execution or Address Calculation)**
4. **MEM (Data Memory Access)**
5. **WB (Write Back)**

#### Pipeline Registers
To enable pipelining, four new registers are added:
- **IF/ID register:** Holds the fetched instruction for the ID stage.
- **ID/EX register:** Contains the decoded instruction for the EX stage.
- **EX/MEM register:** Stores the execution stage result.
- **MEM/WB register:** Holds the memory access stage result.

These pipeline registers allow simultaneous handling of multiple instructions, enhancing processor performance through parallel processing.

### Handling Hazards
The design includes a control unit to manage data hazards:
- It checks for potential hazards by comparing destination and source registers of consecutive instructions.
- Adjusts control signals to ensure smooth progression of instructions, using forwarding techniques to resolve hazards.

### Performance Comparison
Pipelined processors show a significant performance improvement over non-pipelined versions:
- **Non-pipelined processor:** 153 cycles to complete the task.
- **Pipelined processor:** 43 cycles to complete the task.
This results in a speedup of approximately 3.55 times, highlighting the efficiency gained through pipelining.

This project demonstrates the progressive enhancement of a processor architecture, showcasing the benefits of pipelining in executing sorting algorithms efficiently.
