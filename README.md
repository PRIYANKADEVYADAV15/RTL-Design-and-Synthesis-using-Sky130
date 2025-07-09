# RTL-Design-and-Synthesis-using-Sky130

## Table Of Contents
- [Day-1-Introduction to Verilog RTL design and Synthesis](#Day-1-Introduction-to-verilog-RTL-design-and-synthesis)
  - [Introduction to open-source simulator iverilog](#Introduction-to-open-source-simulator-iverilog)
    - [Sky130RTL D1SK1 L1 Introduction to verlog design testbench](#sky130RTLD1SK1L1-introduction-to-verilog-design-testbench)
  - [Labs using iverilog and gtkwave](#labs-using-iverilog-and-gtkwave)
    - [Sky130RTL D1SK2 L1 Lab1 Introduction to lab](#Sky130RTL-D1SK2-L1-Lab1-Introduction-to-lab)

# Day-1- Introduction to Verilog RTL design and Synthesis

## Introduction to open-source simulator iverilog

### Sky130RTLD1SK1L1 Introduction to verlog design testbench
**What is a Simulator?**
A simulator is a software tool that imitates the behavior of a real system, allowing you to test and observe how it works without using the actual hardware.</br>
RTL design is checked for adherence to the spec by simulating the design.</br>
Iverilog is a popular open-source Verilog simulation and synthesis tool. It is widely used in academia and open-source hardware projects for simulating digital circuits written in the Verilog hardware description language (HDL).</br>

**What is a Design?**
Design is the actual verilog code or set of verilog codes which has the intended functionality to meet the required specifications.</br>

**What is a Test-Bench?**
Now, I have my design and I need to check if the design obeys the required spec(specifications) or not. For this I need to apply the stimulus to the design and check it's functionality. So, Testbench is a setup to apply the stimulus (test-vectors) to the design and check it's functionality.</br>

**How Simulator Works?**

![image](https://github.com/user-attachments/assets/4b800914-bd07-4b2a-9782-29dae44892f2)

We have a Design with primary Inputs(one or many) and primary outputs(one or many). So for the primary Inputs we have to generate the stimulus and for primary outputs we need to observe the stimulus. For this we have 'Stimulus Generator' and 'Stimulus Observer'. This is how a test bench looks like.</br>
![image](https://github.com/user-attachments/assets/aa3438bf-b08f-45dc-9a4d-c01364d09938)

*NOTE:*
* *Designs may have one or more Primary inputs and Primary Outputs.*
* *Test Bench does not have a Primary input and Primary output. Only Design has primary input and primary output.*

**Iverilog Simulation Flow**
* We will write verilog code and testbench
* Compile the verilog code and testbench to iverilog simulator, which will give the changes at the output for the changes in the input.
* At the output of iverilog we will get a vcd(value change dump) file format.
* For observing the waveform, we will give vcd format file to GTkwave and observe the required changes.

![image](https://github.com/user-attachments/assets/9f2bae9e-4489-4040-9f70-4d9a65d24124)


## Labs using iverilog and gtkwave

### Sky130RTL D1SK2 L1 Lab1 Introduction to lab










  
