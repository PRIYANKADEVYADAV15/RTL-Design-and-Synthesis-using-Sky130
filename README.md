# RTL-Design-and-Synthesis-using-Sky130

## Table Of Contents
- [Day-1-Introduction to Verilog RTL design and Synthesis](#Day-1-Introduction-to-verilog-RTL-design-and-synthesis)
  - [Introduction to open-source simulator iverilog](#Introduction-to-open-source-simulator-iverilog)
    - [Sky130RTL D1SK1 L1 Introduction to verlog design testbench](#sky130RTLD1SK1L1-introduction-to-verilog-design-testbench)
  - [Labs using iverilog and gtkwave](#labs-using-iverilog-and-gtkwave)
    - [Sky130RTL D1SK2 L1 Lab1 Introduction to lab](#Sky130RTL-D1SK2-L1-Lab1-Introduction-to-lab)
    - [Sky130RTL D1SK2 L2 Lab2 Introduction to iverilog gtkwave part1](#Sky130RTL-D1SK2-L2-Lab2-Introduction-to-iverilog-gtkwave-part1)
    - [Sky130RTL D1SK2 L3 Lab3 Introduction to iverilog gtkwave part2](#Sky130RTL-D1SK2-L3-Lab3-Introduction-to-iverilog-gtkwave-part2)

# Day-1- Introduction to Verilog RTL design and Synthesis

## Introduction to open-source simulator iverilog

### Sky130RTLD1SK1L1 Introduction to verlog design testbench
**What is a Simulator?**</br>
A simulator is a software tool that imitates the behavior of a real system, allowing you to test and observe how it works without using the actual hardware.</br>
RTL design is checked for adherence to the spec by simulating the design.</br>
Iverilog is a popular open-source Verilog simulation and synthesis tool. It is widely used in academia and open-source hardware projects for simulating digital circuits written in the Verilog hardware description language (HDL).</br>

**What is a Design?**</br>
Design is the actual verilog code or set of verilog codes which has the intended functionality to meet the required specifications.</br>

**What is a Test-Bench?**</br>
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
Here we will be looking at the environment setup which are needed for the course. First, we will look into the tool setup then the file setup required.</br>
1) Open the terminal
2) Enter into `home/vsduser/`
3) Create a directory `mkdir VLSI`
4) Clone the Workshop Repository `git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git`
5) ```bash
   cd sky130RTLDesignAndSynthesisWorkshop/
   ```
   
6) Install Required Tools:
   
`sudo apt install iverilog`

`sudo apt install gtkwave`

7)Inside the sky130RTLDesignAndSynthesisWorkshop folder, we have `verilog_files` is the folder which contains all the lab experiments which we will perform. Contains all the verilog source files, test bench files for the experiment.

![image](https://github.com/user-attachments/assets/18731d94-02ab-45e1-b1d7-6be8f897be0a)

![image](https://github.com/user-attachments/assets/29e0719c-f51d-4e5c-aaeb-690ff903175b)

![image](https://github.com/user-attachments/assets/ac807b5e-6a7b-4c5a-a154-24cedac25573)

![image](https://github.com/user-attachments/assets/04be565c-7b42-455d-a026-1b380edbbbbe)

### Sky130RTL D1SK2 L2 Lab2 Introduction to iverilog gtkwave part1
In this lab we will see how iverilog and gtkwave works.</br>
We are inside `verilog_files` folder, Here we will see for every file there is corresponding `tb_` file associated with it.</br>

We will now load a design into the test bench.[Simulating the Design]</br>
**Step 1: Compile and Simulate**
```tcl
#load the mux into simulator
iverilog good_mux.v tb_good_mux.v
```
![image](https://github.com/user-attachments/assets/f891ca86-eb5c-48d5-bf98-7226ca6a531a)

**Step 2: Execute the output file**
We will see a file `a.out` being created, we will execute this output file.</br>
```tcl
./a.out
```
It will dump the vcd file at the output.</br>
![image](https://github.com/user-attachments/assets/b9264d6e-15b5-4a2c-b731-0df3d1279e37)

**Step 2: Load the vcd file at the simulator**
```tcl
gtkwave tb_good_mux.vcd
```
A window will pop up projecting the waveform, Follow the following steps:
* Click on the arrow at the test bench shown
* Signals will be shown
* Drag and Drop the signals above empty space for signals.
* We will see the waveform for the required multiplexer.
* Click on zoom fit, to show complete waveform.

![image](https://github.com/user-attachments/assets/d0afd4f1-6641-49f6-98e1-ee694a98c5da)

This is How we will load the design and check the functionality.</br>

### Sky130RTL D1SK2 L3 Lab3 Introduction to iverilog gtkwave part2
Let's look into the output file structure.</br>
```gvim tb_good_mux.v -o good_mux.v```

We will have the test bench and the design.</br>
Below is the Design.The design shows a 2:1 multiplexer.</br>

![image](https://github.com/user-attachments/assets/67732e1e-cdba-4db4-ad05-41e4df656edc)

```tcl
module good_mux (input i0, input i1, input sel, output reg y);
```
* The verilog code indicates the name `good_mux`
* `i0`: first input
* `i1`: second input
* `sel`: select signal
* `y`: output (declared as `reg` because it will be assigned inside an `always` block)

```tcl
always @(*)
```
* This is a combinational `always` block.
* `@(*)` means it runs whenever any signal used in the block changes.

```tcl
begin
```
* Begins the block of statements that will execute when triggered.

```tcl
if(sel)
        y <= i1;
else
        y <= i0;
```
* If the `sel` input is high (1), then `i1` is assigned to `y`.
* Otherwise (when `sel` is `0`), `i0` is assigned to `y`.

```tcl
end
endmodule
```
* These lines close the `always` block and the `module` respectively.





















  












  
