# Pipelined CPU core based on RISC-V Instruction Set Architecture

## Introduction 
A RISC-V ISA is defined as a base integer ISA, which must be present in any implementation, plus optional extensions to the base ISA. Each base integer instruction set is characterized by
1. Width of the integer registers (XLEN)
2. Corresponding size of the address space
3. Number of integer registers (32 in RISC-V)
The following CPU core 3-stage pipelined and is written in Transaction Level Verilog, popularly known as TL-Verilog.

## Basic microarchitecture of the implemented CPU
Components of the implemented CPU :
1. Program Counter
2. Instruction Memory
3. Decoder
4. Control Unit/ Arithmetic Logic Unit
5. Data Memory
The microarchitecture consist of three stages:
1.Fetch
2.Decode
3.Execute
### Fetch
In this stage, the processor fetches the instruction from the Instruction Memory pointed by the address given by Program Counter. 
The program counter is updated by a logic which is governed by the type of instruction that needs to be executed.
### Decode
In this stage, the type of the instruction fetched must be determined and be sorted out into roughly six types.
1. R-type - Register
2. I-type - Immediate
3. S-type - Store
4. B-type - Branch (Conditional Jump)
5. U-type - Upper Immediate
6. J-type - Jump (Unconditional Jump)
After determining the instruction type, the immediate field, source registers, funct3, funct7 and opcode are retrieved from the instructions accordingly.
The register which needs to be are read when the enable signals are valid.
### Execute
This stage contains the Arithmetic Logical Unit to perform the instruction to get the result. The result further is written to the destintion register and is stored in a Data Memory.

## About TL-Verilog and Makerchip
Transaction-Level Verilog (TL-Verilog) is an emerging extension to SystemVerilog that supports transaction-level design methodology. In transaction-level design, a ​transaction is an entity that moves through a microarchitecture. The language is simple,powerful and flexible to use
Makerchip is a free online environment for developing high-quality integrated circuits. You can code, compile, simulate, and debug Verilog designs, all from your browser. Your code, block diagrams, and waveforms are tightly integrated. The online environment has been used to compile the codes.

## Acknowledgement
I am highly grateful for the workshop conducted by Mr. Steve Hoover, Founder, Redwood EDA and Mr. Kunal Ghosh, CEO, VSD Corp. for conducting the workshop and introducing TL-Verilog and helping in completing a pipelined RISC-V CPU core.

    
