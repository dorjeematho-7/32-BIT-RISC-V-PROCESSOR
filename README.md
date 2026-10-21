# 32-BIT-RISC-V-PROCESSOR (Course Project, Code not allowed to be published)
## Overview
 A multi-cycle processor instead splits each instruction into a sequence of shorter steps (fetch, decode, execute, memory access, write-back) and only spends cycles on the steps an instruction actually needs. A finite-state-machine control unit sequences those steps, which also lets hardware like the ALU and memory interface be reused across cycles instead of duplicated. I am currently taking ECE552 (Comptuer Architecture) which is a graduate course, that investigates pipelined processor architecture and optimizations.

ISA: RISC-V RV32I
Data width: 32 bits
Microarchitecture: Multi-cycle, FSM-controlled
HDL: SystemVerilog
Verification: ModelSim simulation

# Supported instructions
R-type (4 cycles): [add, sub]
I-type ALU (4 cycles): [addi,subi]
Load (6 cycles): [lw]
Store (5 cycles): [sw]
Branch (5 or 7 cycles): [beq]

# Verification
The design was verified in ModelSim with SystemVerilog testbenches:

Module-level tests: [ALU, register file, immediate generator, control FSM] tested on their own before integration

Program-level tests: [RISC-V test programs loaded into memory and run to completion, with register file and memory contents checked against expected results]

Waveform debugging: stepping through the FSM state, PC, and control signals cycle by cycle to track down bugs

# Datapath and Control
<img width="1000" height="512" alt="image" src="https://github.com/user-attachments/assets/142aa3cc-c2de-4345-88a3-3a66c51acd84" />

# FSM state diagram
<img width="738" height="627" alt="image" src="https://github.com/user-attachments/assets/bbaf43ea-c3fd-4427-8d65-46e298885074" />

# RTL VIEWER on Quercus
<img width="1250" height="422" alt="image" src="https://github.com/user-attachments/assets/ac28af5d-a88d-47f2-a2e1-039794be8f69" />




