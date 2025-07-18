# RTL-Design-and-Synthesis-using-Sky130

## Table Of Contents
- [Day-1-Introduction to Verilog RTL design and Synthesis](#Day-1-Introduction-to-verilog-RTL-design-and-synthesis)
  - [Introduction to open-source simulator iverilog](#Introduction-to-open-source-simulator-iverilog)
    - [Sky130RTL D1SK1 L1 Introduction to verlog design testbench](#sky130RTLD1SK1L1-introduction-to-verilog-design-testbench)
  - [Labs using iverilog and gtkwave](#labs-using-iverilog-and-gtkwave)
    - [Sky130RTL D1SK2 L1 Lab1 Introduction to lab](#Sky130RTL-D1SK2-L1-Lab1-Introduction-to-lab)
    - [Sky130RTL D1SK2 L2 Lab2 Introduction to iverilog gtkwave part1](#Sky130RTL-D1SK2-L2-Lab2-Introduction-to-iverilog-gtkwave-part1)
    - [Sky130RTL D1SK2 L3 Lab3 Introduction to iverilog gtkwave part2](#Sky130RTL-D1SK2-L3-Lab3-Introduction-to-iverilog-gtkwave-part2)
  - [Introduction to Yosys and Logic Synthesis](#Introduction-to-Yosys-and-Logic-Synthesis)
    - [Sky130RTL D1SK3 L1 Introduction to Yosys](#Sky130RTL-D1SK3-L1-Introduction-to-Yosys)
    - [Sky130RTL D1SK3 L2 Introduction to Logic Synthesis part1](#Sky130RTL-D1SK3-L2-Introduction-to-Logic-Synthesis-part1)
    - [Sky130RTL D1SK3 L3 Introduction to Logic Synthesis part2](#Sky130RTL-D1SK3-L3-Introduction-to-Logic-Synthesis-part2)
  - [Labs using Yosys and Sky130 PDKs](#Labs-using-Yosys-and-Sky130-PDKs)
    - [Sky130RTL D1SK4 L1 Lab3 Yosys 1 good mux Part1](#Sky130RTL-D1SK4-L1-Lab3-Yosys-1-good-mux-Part1)
    - [Sky130RTL D1SK4 L2 Lab3 Yosys 1 good mux Part2](#Sky130RTL-D1SK4-L2-Lab3-Yosys-1-good-mux-Part2)
    - [Sky130RTL D1SK4 L3 Lab3 Yosys 1 good mux Part3](#Sky130RTL-D1SK4-L3-Lab3-Yosys-1-good-mux-Part3)

- [Day-2-Timing Libs, hierarchical vs flat synthesis and efficient flop coding styles](#Day-2-Timing-Libs-hierarchical-vs-flat-synthesis-and-efficient-flop-coding-styles)
  - [Introduction to timing .libs](#Introduction-to-timing-.libs)
    - [Sky130RTL D2SK1 L1 Lab4 Introduction to dot lib part1](#Sky130RTL-D2SK1-L1-Lab4-Introduction-to-dot-lib-part1)
    - [Sky130RTL D2SK1 L2 Lab4 Introduction to dot lib part2](#Sky130RTL-D2SK1-L2-Lab4-Introduction-to-dot-lib-part2)
    - [Sky130RTL D2SK1 L3 Lab4 Introduction to dot lib part3](#Sky130RTL-D2SK1-L3-Lab4-Introduction-to-dot-lib-part3)
  - [Hierarchical vs Flat Synthesis](#Hierarchical-vs-Flat-Synthesis)
    - [Sky130RTL D2SK2 L1 Lab5 Hier Synthesis vs Flat Synthesis part1](#Sky130RTL-D2SK2-L1-Lab5-Hier-Synthesis-vs-Flat-Synthesis-part1)
    - [Sky130RTL D2SK2 L2 Lab5 Hier Synthesis vs Flat Synthesis part2](#Sky130RTL-D2SK2-L2-Lab5-Hier-Synthesis-vs-Flat-Synthesis-part2)
  - [Various Flop calling Styles and Optimization](#Various-Flop-calling-Styles-and-Optimization)
    - [Sky130RTL D2SK3 L1 Why flops and flop coding styles part1](#Sky130RTL-D2SK3-L1-Why-flops-and-flop-coding-styles-part1)
    - [Sky130RTL D2SK3 L2 Why flops and flop coding styles part2](#Sky130RTL-D2SK3-L1-Why-flops-and-flop-coding-styles-part2)
    - [Sky130RTL D2SK3 L3 Lab Flop synthesis simulations part1](#Sky130RTL-D2SK3-L3-Lab-flop-synthesis-simulations-part1)
    - [Sky130RTL D2SK3 L4 Lab Flop synthesis simulations part2](#Sky130RTL-D2SK3-L4-Lab-flop-synthesis-simulations-part2)
    - [Sky130RTL D2SK3 L5 Interesting Optimizations part1](#Sky130RTL-D2SK3-L5-Interesting-Optimizations-part1)
    - [Sky130RTL D2SK3 L6 Interesting Optimizations part2](#Sky130RTL-D2SK3-L6-Interesting-Optimizations-part2)

- [Day-3-Combinatinal and Sequential Optimizations](#Day-3-Combinatinal-and-Sequential-Optimizations)
  - [Introduction to Optimization](#Introduction-to-Optimization)
    - [Sky130RTL D3SK1 L1 Introduction to Optimization part1](#Sky130RTL-D2SK1-L1-Introduction-to-Optimization-part1)
    - [Sky130RTL D3SK1 L2 Introduction to Optimization part2](#Sky130RTL-D2SK1-L2-Introduction-to-Optimization-part2)
    - [Sky130RTL D3SK1 L3 Introduction to Optimization part3](#Sky130RTL-D2SK1-L3-Introduction-to-Optimization-part3)
  - [Combinational Logic Optimizations](#Combinational-Logic-Optimizations)
    - [Sky130RTL D3SK2 L1 Lab06 Combinatioanl Logic Optimization part1](#Sky130RTL-D2SK2-L1-Lab06-Combinatioanl-Logic-Optimization-part1)
    - [Sky130RTL D3SK2 L2 Lab06 Combinatioanl Logic Optimization part2](#Sky130RTL-D2SK2-L2-Lab07-Combinatioanl-Logic-Optimization-part2)
  - [Sequential Logic optimizations](#Sequential-Logic-optimizations)
    - [Sky130RTL D3SK3 L1 Lab07 Sequential Logic Optimization part1](#Sky130RTL-D3SK3-L1-Lab07-Sequential-Logic-Optimization-part1)
    - [Sky130RTL D3SK3 L2 Lab07 Sequential Logic Optimization part2](#Sky130RTL-D3SK3-L2-Lab07-Sequential-Logic-Optimization-part2)
    - [Sky130RTL D3SK3 L3 Lab07 Sequential Logic Optimization part3](#Sky130RTL-D3SK3-L3-Lab07-Sequential-Logic-Optimization-part3)
  - [Sequential Optimiazations for unused outputs](#Sequential-Optimiazations-for-unused-outputs)
    - [Sky130RTL D3SK4 L1 Seq Optimization unused output part1](#Sky130RTL-D3SK4-L1-Seq-Optimization-unused-output-part1)
    - [Sky130RTL D3SK4 L2 Seq Optimization unused output part2](#Sky130RTL-D3SK4-L2-Seq-Optimization-unused-output-part2)

- [Day-5-Optimization in Synthesis](#Day-5-Optimization-in-Synthesis)
  - [If Case constructs](#If-Case-constructs)
    - [Sky130RTL D5SK1 L1 IF CASE Constructs part1](#Sky130RTL-D5SK1-L1-IF-CASE-Constructs-part1)
    - [Sky130RTL D5SK1 L2 IF CASE Constructs part2](#Sky130RTL-D5SK1-L2-IF-CASE-Constructs-part2)
    - [Sky130RTL D5SK1 L3 IF CASE Constructs part3](#Sky130RTL-D5SK1-L3-IF-CASE-Constructs-part3)
  - [Labs on "Incomplete If Case"](#Labs-on-"Incomplete-If-Case")
    - [Sky130RTL D5SK2 L1 Lab Incomplete IF part1](#Sky130RTL-D5SK2-L1-Lab-Incomplete-IF-part1)
    - [Sky130RTL D5SK2 L2 Lab Incomplete IF part2](#Sky130RTL-D5SK2-L2-Lab-Incomplete-IF-part2)
  - [Lab on "Incomplete overlapping case"](#Lab-on-"Incomplete-overlapping-case")
    - [Sky130RTL D5SK3 L1 Lab Incomplete overlapping Case part1](#Sky130RTL-D5SK3-L1-Lab-Incomplete-overlapping-Case-part1)
    - [Sky130RTL D5SK3 L2 Lab Incomplete overlapping Case part2](#Sky130RTL-D5SK3-L2-Lab-Incomplete-overlapping-Case-part2)
    - [Sky130RTL D5SK3 L3 Lab Incomplete overlapping Case part3](#Sky130RTL-D5SK3-L3-Lab-Incomplete-overlapping-Case-part3)
    - [Sky130RTL D5SK3 L4 Lab Incomplete overlapping Case part4](#Sky130RTL-D5SK3-L4-Lab-Incomplete-overlapping-Case-part4)
  - [for loop and for generate](#for-loop-and-for-generate)
    - [Sky130RTL D5SK4 L1 For Loop and For Generate part1](#Sky130RTL-D5SK4-L1-For-Loop-and-For-Generate-part1)
    - [Sky130RTL D5SK4 L2 For Loop and For Generate part2](#Sky130RTL-D5SK4-L2-For-Loop-and-For-Generate-part2)
    - [Sky130RTL D5SK4 L3 For Loop and For Generate part3](#Sky130RTL-D5SK4-L3-For-Loop-and-For-Generate-part3)
  - [Labs on "for loop" and "for generate"](#Labs-on-"for-loop"-and-"for-generate")
    - [Sky130RTL D5SK5 L1 Lab For and For Generate part1](#Sky130RTL-D5SK5-L1-Lab-For-and-For-Generate-part1)
    - [Sky130RTL D5SK5 L2 Lab For and For Generate part2](#Sky130RTL-D5SK5-L2-Lab-For-and-For-Generate-part2)
    - [Sky130RTL D5SK5 L3 Lab For and For Generate part3](#Sky130RTL-D5SK5-L3-Lab-For-and-For-Generate-part3)
    - [Sky130RTL D5SK5 L4 Lab For and For Generate part4](#Sky130RTL-D5SK5-L4-Lab-For-and-For-Generate-part4)
      

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

7) Inside the sky130RTLDesignAndSynthesisWorkshop folder, we have `verilog_files` is the folder which contains all the lab experiments which we will perform. Contains all the verilog source files, test bench files for the experiment.

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

Below is the Test bench(`tb_good_mux`) for simulating `good_mux` module.</br>

![image](https://github.com/user-attachments/assets/7847b1b9-17bc-4d4c-8843-6c38f257dcd4)

```tcl
`timescale 1ns / 1ps
```
* Sets the simulation time unit and time precision.
* `1ns` = 1 nanosecond time step.
* `1ps` = precision of 1 picosecond (used for delay rounding).

`module tb_good_mux;`
* This starts the testbench module.
* No Input and Output ports here because testbenches are self-contained.

```tcl
// Inputs
reg i0, i1, sel;

// Outputs
wire y;
```
* Declares three reg variables to drive input signals (`i0`, `i1`, `sel`)
* `y` is declared as wire since it will be connected to the output of the DUT (Design Under Test)

```tcl
good_mux uut (
    .sel(sel),
    .i0(i0),
    .i1(i1),
    .y(y)
);
```
* Instantiates the good_mux module.
* uut stands for Unit Under Test.
* Connects the testbench signals to the DUT ports using named port mapping.

```tcl
initial begin
    $dumpfile("tb_good_mux.vcd");
    $dumpvars(0, tb_good_mux);
```
* Generates a VCD (Value Change Dump) file for waveform viewing.
* Dumps all variables inside the module for GTKWave or any VCD viewer.

```tcl
// Initialize Inputs
    sel = 0;
    i0 = 0;
    i1 = 0;
```
* Sets initial values for inputs at time 0.

```tcl
#300 $finish;
```
* Ends the simulation after 300 ns.

```tcl
end
```
* Ends the `initial` block.

```tcl
always #75 sel = ~sel;
always #10 i0 = ~i0;
always #55 i1 = ~i1;
```
* Every 75 ns, toggles the value of sel (0 → 1 → 0 → ...)
* Toggles i0 every 10 ns.
* Toggles i1 every 55 ns.

```tcl
endmodule
```
* Closes the `tb_good_mux` module.

## Introduction to Yosys and Logic Synthesis
### Sky130RTL D1SK3 L1 Introduction to Yosys
**Synthesizer:**Synthesizer is tool that coverts RTL(Register Transfer Level) into a gate-level netlist. Which further can be implemented on an FPGA or fabricated as an ASIC. </br>

**Yosys:** Yosys is an Open-source tool used for synthesizing. </br>

**The typical flow using Yosys is as follows:**
We have the design, and we have the `.lib` verilog file. It is given to yosys and we get the output as netlist.</br>

![image](https://github.com/user-attachments/assets/ef8437a6-9035-4d84-a0ea-fcf05320cf5f)

**Yosys Setup:**
1) We have a `read_verilog` command to read the Design, and `read_liberty` command to read the `.lib`.
2) At the output we have the `write_verilog` for netlist, netlist is the presentation of design in form of cells present in `.lib`.

![image](https://github.com/user-attachments/assets/407b7ba4-63bd-4d24-addf-141e2eb93b14)

**Verify the Synthesis:**
1) We have the netlist and the TestBench.
2) We have the Simulator iverilog.
3) We get the output as vcd file.
4) Run gtkwave to get the waveform.

![image](https://github.com/user-attachments/assets/77dec60f-82a3-4cad-bf37-fc065d3221ad)


*Note:
* *The stimulus should be same as output observed during RTL design.*
* *TestBench is also going to be same as RTL TestBench.*

### Sky130RTL D1SK3 L2 Introduction to Logic Synthesis part1
We will discuss about the complete flow of Logic Synthesis.</br>
**First is RTL Design:** RTL Design is the behavioural representation of required specification. It is written in the form of HDL code as shown below.</br>
![image](https://github.com/user-attachments/assets/d53c8ed7-7785-451f-9ada-857f3aa17071)

Now to convert the RTL design into a digital logic circuit we need a Synthesizer.</br>
![image](https://github.com/user-attachments/assets/529b0a9d-82f4-4b51-a8a1-25bcc64468fe)

* We need to convert RTL to gate level translation.
* The design is converted into gate and the connections are amde between the gates.
* This is given out as a file called netlist.
![image](https://github.com/user-attachments/assets/663ff9cc-9dba-4525-8f31-db22002c3f02)

**What is `.lib`?** </br>
a) It is a collection of all logical modules and standard cells.
b) It includes all basic logic gates like AND, OR, NOR, NAND, etc.
c) It also includes different flavours of same logic gates like-slow, medium and fast gates.
![image](https://github.com/user-attachments/assets/53abe0cf-a235-42b1-a7fb-ca3971326fd9)

**Why do we need different flavours of gates?**</br>
We know combinational delay in logic path determines the max speed of operation of digital logic circuit. </br>
Tclk > Tcq_a + Tcomb + Tsetup_b
We need cells that work fast to make Tcomb small.</br>

![image](https://github.com/user-attachments/assets/4623831a-247e-43de-b231-c8d3b67855ec)

But we also need slow cells.</br>

### Sky130RTL D1SK3 L3 Introduction to Logic Synthesis part2
**Why do we need slow cells?**</br>
Just like setup time we also have hold time. The FF_B should start after FF_A starts and not before. TO ensure that there are no "HOLD" issues at DFF_B, we need cells that work slowly.Hence we need cells that work fast to meet the setup requirement and cells that work slow to meed the hold requirements. The collection forms the `.lib`.</br>
![image](https://github.com/user-attachments/assets/9191c60f-6c66-41ee-9684-c35960508a7c)

**Faster vs Slower cells:**
![image](https://github.com/user-attachments/assets/1578a20f-e034-4827-8864-f45c01df0d75)

**Selection of cells:**
![image](https://github.com/user-attachments/assets/aa1dd173-3b6e-4205-a298-16b32c0a328f)

**Synthesis Illustration:**</br>
First step a synthesiszer is going to do is a syntactical check and then it will start mapping the design. The module maps with the top level ports of the design.</br>

```assign int = sel ? A : B;``` a Verilog continuous assignment using the ternary operator (? :), which is a shorthand way to write an if-else statement. If `sel` is 1, assign `A` to `int`; otherwise, assign `B` to `int`. It is basically describing a 2:1 multiplexer.
Then there is a flop, where the output of mux is input of flip flop. The next code is for flip flop.</br>
This is the coversion of RTL into netlist using gates available in the `.lib`. </br>

![image](https://github.com/user-attachments/assets/7b4ce9ce-2872-47c6-9e60-a2f89624870a)

## Labs using Yosys and Sky130 PDKs
### Sky130RTL D1SK4 L1 Lab3 Yosys 1 good mux Part1
Here we will see how to invoke Yosys and how to synthesize our designs.</br>
We will be reading the verilog files and .lib files, then at the output we will write the verilog files.</br>

To invoke yosys; type `yosys`

![image](https://github.com/user-attachments/assets/7b298397-fb4c-40d8-9890-5ba926c1b7bd)

Inside the `sky130RTLDesignAndSynthesisWorkshop` folder we have `my_lib` file which includes all the library.</br>

* Now inside Yosys we are going to read the library, the command for the same is:</br>
```tcl
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
![image](https://github.com/user-attachments/assets/340032fa-4072-4f77-83de-f3f8e28c4172)

* Next step is to read the design file, here we will read `good_mux.v` design file</br>
```tcl
read_verilog good_mux.v
```
![image](https://github.com/user-attachments/assets/fcf9bdcd-bf04-4277-a6b5-a4db399c046d)

* command to write the module to synthesize
```tcl
synth -top good_mux
```
![image](https://github.com/user-attachments/assets/e6b57307-ac04-4b27-a198-72abccf8dc4b)
![image](https://github.com/user-attachments/assets/cd98468c-fa73-470c-8eb7-8deec46c83fc)

Now we have read the library and design, we will now generate the netlist.</br>
* Generate the Netlist
```tcl
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
# abc is the command which will convert our RTL into the gate level and what all logic circuits are required.
```
![image](https://github.com/user-attachments/assets/b0bc529a-675e-4d3a-b22d-c3a9048f8a5c)
![image](https://github.com/user-attachments/assets/d956524a-4bac-42b3-b219-f8653ea6457b)

We can see what all logic gates is has used, also the internal signals, input and output signals.

To show the graphical version of logic it has realised, the command used is : `show`

![image](https://github.com/user-attachments/assets/8cc2af11-0f29-4b32-9d1b-aec02f65344a)

### Sky130RTL D1SK4 L2 Lab3 Yosys 1 good mux Part3
We will now see how netlist looks like.</br>
* Command to write the synthesized gate-level netlist
  ```tcl
  #It writes the synthesized gate-level netlist to a Verilog file named good_mux_netlist.v.
  write_verilog good_mux_netlist.v
  ```
  ![image](https://github.com/user-attachments/assets/27b6b3c8-0447-4254-8ed1-fb55ca7ec538)

* Open the file `good_mux_netlist.v` in the GVim text editor.
  ```tcl
  !gvim good_mux_netlist.v
  ```
  ![image](https://github.com/user-attachments/assets/09cf1b10-f0bf-4757-8782-fc06c4a3acb9)

*Note: Here there are unnecessary attributes, so we will remove these by using the switch ```write_verilog -noattr good_mux_netlist.v```*.</br>

* Simplified Netlist
  ```tcl
  !gvim good_mux_netlist.v
  ```
  ![image](https://github.com/user-attachments/assets/5aa03659-fdf2-47b6-80af-bf1d02851f23)


# Day-2-Timing Libs, hierarchical vs flat synthesis and efficient flop coding styles
## Introduction to timing .libs
### Sky130RTL D2SK1 L1 Lab4 Introduction to dot lib part1
Here we will see what our libraries actually contain.
 1. To see what's inside the library
   ```tcl
   gvim ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```
   ![image](https://github.com/user-attachments/assets/23b5b186-b752-4e8d-89c2-48e950a83095)

   Let us breakdown `sky130_fd_sc_hd__tt_025C_1v80.lib` library:
   * `sky130` → Refers to the SkyWater 130nm open-source process node.

   * `fd_sc_hd` → Stands for:
      `fd`: Foundry Design
      `sc`: Standard Cells
      `hd`: High Density (a variant optimized for smaller area)

   * `tt` → Process corner:
      `tt` = Typical-Typical (average manufacturing, average performance)
     
   * `025C` → Temperature:
      25°C — standard room temperature

   * `1v80` → Voltage:
      1.80 Volts — the supply voltage during characterization

   * `.lib` → File extension for Liberty format, used by synthesis and timing analysis tools.

 2. When we look into a library, There are three crucial parameters to look into; P:Process, V:Voltage, T:Temperature.</br>
    The variations in these parameters will decide how the 'Silicon' is going to work.

### Sky130RTL D2SK1 L2 Lab4 Introduction to dot lib part2
We will now see what are the different cells contained in the library.</br>

![image](https://github.com/user-attachments/assets/58e544a4-d846-42ad-8610-7f94ef410d04)

If we type `:/cell`, we will see what all cells are present. The different flavours of same cell, features of cells, leakage power and so on.</br>
![image](https://github.com/user-attachments/assets/853878c7-7e69-4570-bcb0-f021f7a60613)

To see the behavioral model of a specific cell, type the command:
```tcl
:sp ../verilog_model/sky130_fd_sc_hd__a211o.behavioral.v
```
### Sky130RTL D2SK1 L3 Lab4 Introduction to dot lib part3
Let's check some other cells as well.</br>
![image](https://github.com/user-attachments/assets/3355c47d-fe24-421d-8cf8-2cae87ba3ccb)

We will look into the difference between `and2_0`, `and2_2` and `and2_4`:</br>
It is actually the difference in 'area', 'power', 'delay'</br>
**Area:** `and2_0` < `and2_2` < `and2_4` </br>
**Delay:** `and2_0` > `and2_2` > `and2_4` </br>
**Power:** `and2_0` < `and2_2` < `and2_4` </br>
This shows that wider the area --> faster is the transistor --> and power consumed will also be more.</br>
<img width="1918" height="971" alt="image" src="https://github.com/user-attachments/assets/d34b44a9-b6cd-438a-bddb-09e2a652d0ef" />

## Hierarchical vs Flat Synthesis
### Sky130RTL D2SK2 L1 Lab5 Hier Synthesis vs Flat Synthesis part1
We will see in this lab what is Hierarchical and Flat synthesis</br>
The files which we will be discussing here `multiple_modules.v`, inside `/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files/`
* ```tcl
  gvim multiple_modules.v
  ```
  <img width="1918" height="1030" alt="image" src="https://github.com/user-attachments/assets/abdf7f7a-b43a-48f7-b5fe-e73e5ad833c9" />
  
  Here we have sub_module 1 which is an AND gate and sub_module 2 which is an Or gate. U1 has inputs 'a' and 'b' and output as 'net1', which is input to U2 OR c and    output of OR gate is output of multiple_modules as shown below.</br>
  
  <img width="556" height="322" alt="image" src="https://github.com/user-attachments/assets/f96f86b6-0f14-4883-8bd3-5ec109b5c265" />

* Let's do the synthesis. Type commands as shown below;
  1) ```yosys```
  2) ```read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
  3) ```read_verilog multiple_modules.v```
  4) ```synth -top multiple_modules```
     <img width="1918" height="1028" alt="image" src="https://github.com/user-attachments/assets/719ca34c-95fc-4074-9fa4-146f8cc46232" />
     
     We can see the report here which shows sub_module 1 has 1 AND gate, sub_module 2 has 1 OR gate and overall there 2 gates.</br>

     <img width="1918" height="1023" alt="image" src="https://github.com/user-attachments/assets/e109e1df-82a5-4f3b-bc38-e0eb40274014" />

     <img width="1916" height="1023" alt="image" src="https://github.com/user-attachments/assets/96b05aa3-1d8f-4b0c-8e58-a17ea9382039" />

  5) ```tcl
     # we will link design to library
     abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
     ```
  6) ```tcl
     # we will see the design as shown in the above figure
     show multiple_modules
     ```
     
     <img width="1918" height="1016" alt="image" src="https://github.com/user-attachments/assets/445e5a41-3b04-46cc-8c30-b98f1c5132d7" />

     *Note: We will not see the AND / OR gates, we will just see sub_module 1 and sub_module 2*</br>
     This is what we called **Hierarchical Synthesis**.</br>

  7) ```tcl
     # we will write the netlist with -noattr
     write_verilog -noattr multiple_modules_hier.v
     ```
  8) ```tcl
     # we will see how the netlist looks like
     !gvim multiple_modules_hier.v
     ```

     <img width="1918" height="1032" alt="image" src="https://github.com/user-attachments/assets/f0a0fb1a-10f5-41e4-9ef3-a75689bb5630" />

     <img width="1918" height="1027" alt="image" src="https://github.com/user-attachments/assets/bc5d4c6d-b9f5-46f1-adb5-4b609c9d82c6" />

     We can see here the Hierarchies are preserved.</br>

### Sky130RTL D2SK2 L2 Lab5 Hier Synthesis vs Flat Synthesis part2
Till now we have discussed what actually hierarchy is, now we will do `flatten`. This command Merge all instantiated submodules into the top module, so the design becomes a single-level netlist with no hierarchy.</br>
If your top-level module instantiates other modules inside it (like reusable components), `flatten` will:</br>
* Pull all submodule logic directly into the top-level
* Remove all module boundaries
* Make it one flat, big module with just gates and wires

We will use the following commands;
* ```tcl
  # to flat the netlist
  flatten
  ```
* ```tcl
  write_verilog -noattr multiple_modules_flat.v
  ```
* ```tcl
  !gvim multiple_modules_flat.v
  ```

  <img width="1917" height="1027" alt="image" src="https://github.com/user-attachments/assets/ea97042b-f5ee-4b7d-8223-83da594eea9c" />

  <img width="1918" height="1028" alt="image" src="https://github.com/user-attachments/assets/d794b8dc-f964-4341-be76-db459c61c5f1" />

  Let's do the comparison with Hierarchical synthesis.</br>
  Here we can see that there is no hierarchy, it is flattened out. There is no sub_modules and  direct instantiation of AND, OR gate.</br>

  <img width="1912" height="1018" alt="image" src="https://github.com/user-attachments/assets/2053fa5d-23b5-4cb2-80fa-095ade79e2a9" />
* ```tcl
  # to see how the layout looks like after flattening
  show
  ```
  After flattening we will not see u1 and u2 and sub_modules.</br>
  
  <img width="1915" height="1047" alt="image" src="https://github.com/user-attachments/assets/7ff448b9-dbb3-4f49-85a0-7c6e3811adbb" />


Now if I have multiple modules and I want to synthesize sub modules, then how to do it?

**Sub_modules level synthesis**

* ```yosys```
* ```read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
* ```read_verilog multiple_modules.v```
* ```tcl
  # Since we are synthesising onlu sub modules and not multiple modules
  synth -top sub_module1
  ```
  <img width="1920" height="1035" alt="image" src="https://github.com/user-attachments/assets/f125cb7b-5b62-4263-b040-244c0c7dab76" />

* ```tcl
  # link the design
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  show
  ```
  We will see only the AND gate, which is present in sub_module1.</br>
  
  <img width="1917" height="1026" alt="image" src="https://github.com/user-attachments/assets/0cd0fccc-a231-49c0-90b0-e2c8315275da" />

  Why do we prefer module level synthesis?
  1) When we have multiple instantiation of same module module level synthesis becomes easy as we don't need to instantiate the same module many a times.</br>
  
  2) Divide and Conquer- This technique is used in Massive design. When we give the entire design to a tool, but tool is not doing a good job, So instead of giving       the entire massive design to tool we will give one by one portion. By doing this the entire design is optimized and we get the best netlist.

  So, to control which module we want, the command we use is: ```synth -top $module_name```.


## Various Flop Calling Styles and Optimization
### Sky130RTL D2SK3 L1 Why flops and flop coding styles part1

We will study here how to code a flop and what are the different possible flops available.</br>
Why do we need Flops, We know when there is a combinational circuit and there is input signal given there will be "Glitch" at the output. For many combinational circuits there will be further more glitches.And for continuous combinational circuits the output will never settle down, it will be always glitchy. To avoid this we need an element to store the value, it is called "FLOP".</br>

We will use the flops in between the combinational circuit to stabilize the output even after the glitches, the output of the flop will remain constant. This is the main purpose of using flops in digital circuit.</br>
Also we need to initialize the flops for that we have 'Set' and 'Reset' which can be Synchronous and Asynchronous.</br>

<img width="1228" height="653" alt="image" src="https://github.com/user-attachments/assets/a1fda91f-189f-41b5-b9b2-eadfac8600d0" />

### Sky130RTL D2SK3 L2 Why flops and flop coding styles part2

<img width="1918" height="998" alt="image" src="https://github.com/user-attachments/assets/826ba4c1-2917-4a57-94ee-ec67c41770eb" />

Above code is D-flop code for both asynchronous and synchronous reset. `always` at posedge clk signifies a posedge flipflop; posedge of asynchronous.</br>
`if` has ore priority than `else` part, First looking for asynchrnous clock. Let's breakdown one by one each line</br>

* `module dff_asyncres_syncres (...)`
   * Declares a module named dff_asyncres_syncres.
   * Inputs:
      `clk`: Clock signal.
      `async_reset`: Asynchronous reset signal.
      `sync_reset`: Synchronous reset signal.
      `d`: Input data to the D flip-flop.
   * Output:
      `q`: Output of the flip-flop (declared as `reg` because it's assigned inside an `always` block).

* `always @ (posedge clk , posedge async_reset)`
   This block is triggered on:
  * A rising edge of the clock (`posedge clk`) — used for synchronous behavior.
  * A rising edge of `async_reset` — used for immediate (asynchronous) reset.

This is a standard pattern for flip-flops that require both asynchronous and synchronous control.

* `if (async_reset)`
  If the asynchronous reset is triggered, `q` is set to `0` immediately, ignoring the clock.

* `else if (sync_reset)`
  If `async_reset` is not active, but `sync_reset` is high on the rising edge of the clock, then `q` is also set to `0`.

* `else q <= d;`
  If neither reset is active, the D flip-flop captures the input `d` on the rising edge of the clock.

  This is an asynchronous reset, we entered into this loop because of posedge of edge. Only in case of posedge we can enter into `always` block. Circuit is getting sensitive to positive edge of clock. upon positive edge `q` is getting `d`. It is an asynchronous reset because it does not awaits for clock. If I apply `reset` at any point. the output will go low irrespective of `q` value. </br>

  <img width="1238" height="631" alt="image" src="https://github.com/user-attachments/assets/e741dac9-4d79-45ff-a3d3-0254218162f6" />

If we talk about `asynch_set`; "Set" means setting the output `q` to logic `1`.Asynchronous" means this happens immediately when `async_set` goes high, regardless of the clock. The presence of async_set in the sensitivity list `(always @(posedge clk, posedge async_set`)) makes it asynchronous.</br>

<img width="1918" height="1030" alt="image" src="https://github.com/user-attachments/assets/949e6cf2-19cc-4a55-ae6f-8867ff6c781a" />

Now talking about `synch_reset`, A synchronous reset is a reset signal that only affects the output during the active clock edge (typically rising edge). This means the reset signal is checked along with the clock.When posedge clock is given and `synch_reset` is 1, then output `q` will set to `0`.

Below is the image of all 4 together.</br>
<img width="1918" height="1023" alt="image" src="https://github.com/user-attachments/assets/aff2dc7d-0f82-416c-9cbb-fecbdf4aaa5c" />

<img width="1213" height="517" alt="image" src="https://github.com/user-attachments/assets/cf34d2b2-6841-4a69-8bb4-1d1295c85d32" />

Above shows the asynch and synch_reset, only asynch_reset and only synch_reset.</br>

### Sky130RTL D2SK3 L3 Lab Flop synthesis simulations part1

Here we will simulate all the flops discussed above and see how they behave.</br>
We will be dealing with `dff` files here</br>

<img width="1918" height="1032" alt="image" src="https://github.com/user-attachments/assets/81ed093c-0d49-4442-bde8-4654e977a64b" />

Write the following steps to get the waveform of `asynch_reset`:
* ```tcl
  iverilog dff_asyncres.v tb_dff_asyncres.v
  ```
* ```tcl
  ./a.out
  ```
* ```tcl
  gtkwave tb_asyncres.vcd
  ```
  <img width="1918" height="1047" alt="image" src="https://github.com/user-attachments/assets/78045733-b898-445c-89a2-fe6a8f36bf69" />

  We can clearly see in the waveform, the moment `async_reset = 1`, irrespective of `clk`, `q = 0`. </br>

* ```tcl
     #Now we will into the file below and follow the similar steps
     dff_async_set.v
  ```
  Here we can see that output `q` becomes `1` only when `async_set = 1`.</br>
  
  At `async_set = 0` , the changes in `d` are looked upon by output `q` only on positive clock edge. When `d = 0` on clock edge `q = 0` and similarly for `d = 1`, `q   = 1`</br>

  <img width="1916" height="1020" alt="image" src="https://github.com/user-attachments/assets/8220ffde-8b04-4f13-a5d7-f78cea891ff5" />

  At `async_set = 1`, the changes in output are not virtue of changes in `clk` or `d` it only depends on `async_set`.
  <img width="1918" height="1028" alt="image" src="https://github.com/user-attachments/assets/fee69ebe-7e05-4fe1-8327-b1077477f505" />

Now look at the `sync_reset` behaviour </br>
* ```tcl
  iverilog dff_syncres.v tb_dff_syncres.v
  ```
* ```tcl
  ./a.out
  ```
* ```tcl
  gtkwave tb_syncres.vcd
  ```
  Here we can see that even though the `sync_reset = 1`, the output `q` goes to `0` only when the clock edge is positive.This shows that synchronous flop depends on clock edge.</br>
  <img width="1913" height="1020" alt="image" src="https://github.com/user-attachments/assets/76dae253-7c39-47e6-9dbb-5f2126eb6ee0" />


### Sky130RTL D2SK3 L4 Lab Flop synthesis simulations part2
**Now we will synthesize these three circuits**.</br>
* ```tcl
  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  read_verilog dff_asyncres.v
  ```
* ```tcl
  synth -top dff_asyncres
  ```
<img width="1920" height="993" alt="image" src="https://github.com/user-attachments/assets/bd71de70-145e-43ac-a75b-94aeb986f1f4" />

Since, we are using D-flip flops we are supposed to use keyword `dfflibmap`. As in the flow they will keep a separate flop library and standard cell library so we need to tell the tool where to pick D-FF design from. This will only look for `dff` flops. br>
* ```tcl
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```

<img width="1912" height="992" alt="image" src="https://github.com/user-attachments/assets/1b4674d7-9b45-43f2-b938-2f422941284b" />

* ```tcl
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  show
  ```
  <img width="1916" height="1022" alt="image" src="https://github.com/user-attachments/assets/8d7a754a-c1d0-4127-a9d9-d612b2a7ff64" />

**Next, we will synthesize `async_set` and following the same steps as before**.</br>

<img width="1917" height="1047" alt="image" src="https://github.com/user-attachments/assets/8189c351-88e6-4cf3-8ed7-35ba73fca4d3" />

**Now, let's look into `syncres.v`.** </br>

<img width="1918" height="1027" alt="image" src="https://github.com/user-attachments/assets/698a1f8c-4832-4845-a137-830ed6ee03b5" />

### Sky130RTL D2SK3 L5 Interesting Optimizations part1
We will see some interesting optimization.</br>
Let us look at the RTL code into the RTL files.</br>

```gvim mult_*.v -o```

<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/87664284-1278-4309-b40e-1d182ffcdbaa" />

These are the two RTL files we are going to see, 'mult2' and 'mult8'.</br>
Now if see module mult2, it is a 3 pin input and generating a 4 pin output. Where the relation between input and output is `y = a*2`.</br>
If we write down the bits of input and output, we will see that at the output; y(3)=a(2); y(2)=a(1); y(1)=a(0) and y(0)=0{appending one 0}. Similarly for multiplying a number with 4 is the number itself plus appended zeros, for multiplying with 8 append 3 zeros and so on...</br>

<img width="886" height="492" alt="image" src="https://github.com/user-attachments/assets/1be10823-891b-4e38-aa48-b35241827a28" />

So we can see that we actually don't need any external hardware, that means multiplying with 2 or powers of 2 is just shifting the digits.</br>

Now let's do the synthesis;
1) ```read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
2) ```read_verilog mult_2.v```
3) ```synth -top mul2```
   Here we have inferred no memories, no cells
   
   <img width="1918" height="1038" alt="image" src="https://github.com/user-attachments/assets/88887a28-8d88-4a4b-8f8c-1739e8aefce6" />
5) ```abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
   As there is nothing to synthesize, so it will show nothing to map.
   
7) ```show```

   <img width="1918" height="1038" alt="image" src="https://github.com/user-attachments/assets/e61cf19a-3c31-430d-bf1d-a04302a8b14e" />

   We got the number 'a' appended with zero {a,0}, this is what we expected.</br>


### Sky130RTL D2SK3 L6 Interesting Optimizations part2
Let us take another special case:
Input a[2:0] and output y[5:0]. The relation between the two is such that</br>

```tcl
a*9 = y;
a*(8+1) = y;
a*8 +a*1 = y
```
We have already seen a * 8 which is [a,0,0,0]. So, now a * 9 will be as follows;

<img width="643" height="355" alt="image" src="https://github.com/user-attachments/assets/2b576399-8fe7-4fde-85ae-5d8b236e9d92" />

So, y will have two replicas of a--> [a,a]. Also we don't need any external hardware. The connections will be as shown below</br>

<img width="637" height="351" alt="image" src="https://github.com/user-attachments/assets/1cf82a98-fa99-4171-9580-67788cb50aa4" />

Let us execute this optimization</br>

* ```tcl
  # first write the netlist
  write_verilog -noattr mul2_net.v
  ```
* ```tcl
  # look at the netlist
  !gvim mul2_net.v
  ```

  <img width="1916" height="991" alt="image" src="https://github.com/user-attachments/assets/1138fcd5-e7a9-4722-a65c-e70996628f6a" />

  Now let us go to our next example `mult8`.

* ```tcl
  read_verilog mult_8.v
  ```
* ```tcl
  synth -top mult8
* ```tcl
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  show
  ```

  <img width="1913" height="1022" alt="image" src="https://github.com/user-attachments/assets/3b681170-9c4f-4551-b1cd-53251464ec66" />

* ```tcl
  # look at the netlist
  write_verilog -noattr mult8_net.v
  ```
* ```tcl
  !gvim mult8_net.v
  ```

  <img width="1918" height="991" alt="image" src="https://github.com/user-attachments/assets/f1835eb8-fb65-459d-a8ce-7e28b8477d2e" />


# Day-3-Combinatinal and Sequential Optimizations
## Introduction to Optimization
### Sky130RTL D3SK1 L1 Introduction to Optimization part1
We know in Digital circuits, we have two types pf logic circuits namely 'Combinational' and 'Sequential' logical circuits.</br>
Here we will first dicuss about  'Combinational logic Optimizations'.</br>

**Why do we need logic optimizations?**

<img width="912" height="452" alt="image" src="https://github.com/user-attachments/assets/cb5c4653-ea39-41a4-95e2-b5d05698177d" />

Let us consider the example shown below;

<img width="972" height="473" alt="image" src="https://github.com/user-attachments/assets/82645755-6cbb-4739-8e7a-0f2a18fb540d" />

Here if we realise the output, at A=0 we get output as C', which can be realised simply by using an 'Inverter' .</br>
If we realise this using Cmos, above circuit needs 6 Cmos transistors whereas an Inverter needs only 2. So, this is an example of logic circuit optimization.</br>

<img width="1186" height="632" alt="image" src="https://github.com/user-attachments/assets/47b8db88-2127-4551-bde0-49d7c355fae8" />

Now let us look at **Boolean Logical Optimization** as given;
`assign y = a?(b?c:(c?a:0)):(!c)`

This expression is of a multiplexer, it is in the form a?((a=1):(a=0))</br>

<img width="852" height="467" alt="image" src="https://github.com/user-attachments/assets/49baced3-bbac-4d36-aaea-c8f671b38423" />

But this is not the optimized circuit, let's optimize it. We will solve the boolean Expression and get the required expression.</br>

<img width="1147" height="540" alt="image" src="https://github.com/user-attachments/assets/aa454bbc-4dfa-4f5c-8ea0-7ec72d00bb37" />


### Sky130RTL D3SK1 L2 Introduction to Optimization part2
Now let us look at **Sequential Logic Optimization** Techniques; It is of two types: Basic and Advanced.

<img width="1045" height="467" alt="image" src="https://github.com/user-attachments/assets/d7e34bca-8739-49b1-bfdb-378f8cb6b869" />

Let's start with **Sequential Constant Propagation** 
Say, I have a Flop, with `clk` and `D` input tied low with `Reset` connected to it. Is there any way `Q` can become '1'..?

If RST = 0; Q = 0

 RST not equal to 0; Then also Q = 0 because D = 0 always.
 
 So o/p becomes '1' always irrespective of clk, Reset, Q or A. This happens because of 'Sequential Constant Propagation'.</br>

 <img width="1107" height="465" alt="image" src="https://github.com/user-attachments/assets/313b9e80-7479-4a97-a79a-644daf42a42a" />

 Let's say i have a 'Set' clock connected now and rest of logic is same.</br>
 If Set = 1; Q = 1</br>
 If Set is not equal to 1; clk is given; Q = 0</br>

 Now can we say Q = Set ?

 Let's draw the waveform of clock, SET and Q. As shown below we can see there is clock cycle delay. </br>
 Q goes '1' asynchronously but Q goes '0' synchronous to the clock. So we cannot say Q = SET. Therefore, this logic cannot be optimized as the set has to be retained and for the FLop to be sequential constant 'Q' pin should always be a constant value.</br> 

 <img width="942" height="333" alt="image" src="https://github.com/user-attachments/assets/99476f9c-27e3-4e0c-b872-ac2163760bd0" />
 
### Sky130RTL D3SK1 L3 Introduction to Optimization part3
We will now study about other types of optimization techniques such as; **State optimization**, **Retiming** and **Sequential Logic Cloning**.</br>
1) **State optimization**- Reducing the number of states. Re-encoding states to reduce complexity

2) **Retiming**-Retiming is the relocation of flip-flops across combinational logic blocks without changing the overall functionality. It improves clock speed by balancing delay across targets.

3) **Sequential Logic Cloning**-Sequential logic cloning involves duplicating sequential elements (flip-flops/latches) to reduce fanout or optimize logic sharing. Reduces load on Flip-flop.

<img width="1238" height="695" alt="image" src="https://github.com/user-attachments/assets/e656d38f-55ed-42be-8f3f-9a8843641f62" />

## Combinational Logic Optimizations
### Sky130RTL D3SK2 L1 Lab06 Combinatioanl Logic Optimization part1

Inside `/verilog_files/` folder, the files we are going to use are ```*opt*``` and ```*opt_check*```.

<img width="1917" height="1025" alt="image" src="https://github.com/user-attachments/assets/4f20b07a-40e0-4dc4-a101-b805bf99cf18" />

Let's check what is inside ```opt_check``` file.</br>

<img width="1918" height="1047" alt="image" src="https://github.com/user-attachments/assets/eaec8c48-86a1-4e76-8661-9cc3e9707872" />

`opt_check` is assigning value to y. When a=1, y=b; a=0,y=o. It is 2:1 Mux resulting in an AND gate.

<img width="566" height="187" alt="image" src="https://github.com/user-attachments/assets/bb1b5c62-9dac-4ef2-a9fd-217e37e5b3c0" />

Coming on to next ```opt_ckeck2``` file.

<img width="1917" height="1031" alt="image" src="https://github.com/user-attachments/assets/061fffb3-b5d2-4337-8d1e-d57d9cd6f783" />

Here when a=0, value is 'b'; a=1, value is '1'. So it is a 2:1 mux resulting in an OR gate.

<img width="560" height="117" alt="image" src="https://github.com/user-attachments/assets/6f403362-84ca-416d-9a5d-8a94b4f2bd0c" />

We will now load the libraries;
* ```tcl
  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  read_verilog opt_check.v
  ```
* ```tcl
  synth -top opt_check
  ```
* ```tcl
  # command to do to contant propagation and optimization, cleans up leftover gates, nets, ports, or registers that no longer contribute to the final design after transformations like constant propagation, logic folding, or retiming.
  opt_clean -purge
  ```
* ```tcl
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  show
  ```
  We are expecting an AND gate, and we got the same

  <img width="1918" height="1020" alt="image" src="https://github.com/user-attachments/assets/c6283b87-fb2a-4f12-a255-91f7d2e53916" />

  Now follow the same steps and read the other verilog file; ```opt_check2```.

  We will get an OR gate here

  <img width="1915" height="1051" alt="image" src="https://github.com/user-attachments/assets/95dc69af-7889-483d-b747-5b56e806b6e9" />

### Sky130RTL D3SK2 L2 Lab07 Combinatioanl Logic Optimization part2
Now we will see the file ```opt_check3.v```. 'a' has assigned mux (c?b:0) when it is '1', and '0' when a=0

<img width="1918" height="1026" alt="image" src="https://github.com/user-attachments/assets/fb1c7dba-c127-4435-913b-5c0eca2ba7e7" />

We are expecting a 3 input AND gate here.

<img width="566" height="302" alt="image" src="https://github.com/user-attachments/assets/e1585bb8-24fa-4cc1-9b22-b39034f1b624" />

<img width="1918" height="1053" alt="image" src="https://github.com/user-attachments/assets/3865afa2-06d5-46fe-9d24-8ec956273cd4" />

Similarly we will check for ```opt_check4.v```

<img width="1918" height="1045" alt="image" src="https://github.com/user-attachments/assets/426c0a89-4c3d-402c-9c5d-78e13611aacd" />

We are expecting an EXNOR gate here.

<img width="1907" height="1043" alt="image" src="https://github.com/user-attachments/assets/5b6e412e-a8c9-471e-879d-bc20cbb45544" />

Now we will check the ```multiple_module_opt*``` file.

<img width="1925" height="1040" alt="image" src="https://github.com/user-attachments/assets/8a69a5fd-3372-4fae-a7ed-24a51a21c286" />

<img width="1918" height="1022" alt="image" src="https://github.com/user-attachments/assets/ebd76c91-6d02-4bdc-ad13-56d764c14500" />

We need to follow the following steps:

* ```tcl
  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  read_verilog multiple_module_opt.v
  ```
* ```tcl
  synth -top multiple_module_opt
  ```
* ```tcl
  flatten
  ```
* ```tcl
  write_verilog -noattr multiple_module_opt.v
  ```
* ```tcl
  opt_clean -purge
  ```
* ```tcl
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  show
  ```
  
<img width="1917" height="1050" alt="image" src="https://github.com/user-attachments/assets/ea21b49c-f13a-42fe-b74b-39a04a2c4547" />

## Sequential Logic optimizations
### Sky130RTL D3SK3 L1 Lab07 Sequential Logic Optimization part1
Now we will start with Sequential circuit optimization. The files we will be dealing with are ```*dff_const*```.

<img width="1918" height="1077" alt="image" src="https://github.com/user-attachments/assets/e11fc0f0-b988-4e44-9444-2e0ef6bb155a" />

Let's look one by one inside the files.
Open multiple files in gvim using ```gvim dff_const1.v -o dff_const2.v```

<img width="1918" height="1053" alt="image" src="https://github.com/user-attachments/assets/7fc8ecc8-26a2-4902-9b2b-cbb73e727fd8" />

If we see the code for ```dff_const1.v```; On applying `RESET` `Q` should become '0', and when `RESET` is '0' `Q` should become '1' only when next `posedge` of clock is applied. ALso we cannot say that `Q` is inverter output of `reset`, it only happens when positive edge of clock is applied.

<img width="647" height="202" alt="image" src="https://github.com/user-attachments/assets/4e17041c-aa37-4b31-b3a5-a20674dd05f9" />

Next ```dff_const2.v```, on applying `reset` it is becoming high, on removing `reset` it is high and on next clock edge also it is high. So it is constant throughout.

<img width="607" height="122" alt="image" src="https://github.com/user-attachments/assets/ba4ab033-136f-4fd7-913b-84ed710c12c6" />

Let's simulate this
* ```tcl
  # jump into the test bench
  iverilog dff_const1.v tb_dff_const1.v
  ```
* ```tcl
  # executable file is generated
  ./a.out
  ```
* ```tcl
  gtkwave tb_dff_const1.vcd
  ```
  <img width="1916" height="1032" alt="image" src="https://github.com/user-attachments/assets/074bd23b-afba-47e2-9c90-8fbaf36681e5" />
  
Now let's simulate ```dff_const2.v```.By following the same steps as shown earlier.

<img width="1918" height="1060" alt="image" src="https://github.com/user-attachments/assets/8b7d0688-1b78-466a-a2f5-8e57e53e211f" />

Now launch yosys and see the circuit;
* ```tcl
  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  read_verilog dff_const1.v
  ```
* ```tcl
  synth -top dff_const1
  ```
* ```tcl
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
* ```tcl
  show
  ```

  <img width="1918" height="1047" alt="image" src="https://github.com/user-attachments/assets/f6606253-6264-458f-8be9-39b424ab5e68" />

  We can see a flop and it is coded as active low reset but our code show active high so we have inserted an inverter to reset pin.

### Sky130RTL D3SK3 L2 Lab07 Sequential Logic Optimization part2

Now do the same for ```dff_const2.v```. One thing to note that for executing ```dff_const1.v``` at the printing statistics there cells, and flops present whereas in ```dff_const2``` there are no flops and cells present.

<img width="1918" height="1042" alt="image" src="https://github.com/user-attachments/assets/413e4695-0498-440a-9b62-e7f8d5df9b21" />

<img width="1918" height="1031" alt="image" src="https://github.com/user-attachments/assets/0866f531-c24c-4221-ba4a-49821c661c43" />

All the flops has been removed as the output was always '1' so no need for external connections. This is what is sequential optimizations.
Let us see other sequential dff files, ```dff_const3.v```

<img width="1918" height="1038" alt="image" src="https://github.com/user-attachments/assets/d73cdb5d-e36a-4401-9877-b6baa4e1e8fa" />

Here there are 2 flops present and both getting `clk` and `reset`. `reset` of 1st is `set` of second. Upon `reset` Q1 is becoming 1'b0 and Q is becoming 1'b1; else Q1 is 1'b1 and Q is Q1.
Now let us see if we apply clock and reset what happens to Q1 and Q, also can any flop be optimized.

<img width="886" height="572" alt="image" src="https://github.com/user-attachments/assets/534308ea-02eb-4d3d-a091-212375e94204" />

We can see above that Q is becoming 0 only for one clock cycle t=due to the flop delay, so we cannot remove the second flop.

### Sky130RTL D3SK3 L3 Lab07 Sequential Logic Optimization part3
Let's simulate ```dff_const3.v```

<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/1d83b137-67ed-46ad-a4e7-7d0854354bd5" />

We can see Q going '1' after one clock edge.

Let us also see our synthesis. We can see there are 2 flops present.

<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/c85406ef-df79-4f82-a411-8c235ac1b899" />

<img width="1918" height="1022" alt="image" src="https://github.com/user-attachments/assets/f66efc17-bc68-4c3a-ac3d-f8d9382d5523" />

Similarly, we can do ```dff_const4.v``` and ```dff_const5.v```.

## Sequential Optimiazations for unused outputs
### Sky130RTL D3SK4 L1 Seq Optimization unused output part1
Besides Combinational logic optimization and Sequential logic optimization there one more kind of optimization which is called "Unused output Optimizations".

Let us open a code ```counter_opt.v```. </br>
We can see there is an input clk, input reset and output q. There isa signal internal to it which is a register 3 bit signal called `count`. We are writing `always` `posegde` clock. If there is a `reset`, the count is '000' else the count is incremental. So, if we look at the code, it is a 3 bit "Up-counter".

<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/680633bd-5dfd-4177-aa40-6a447bd45c50" />

If we see the circuit, the counter has 3 bit input out of which output is assigned to count[0] bit only, rest all the bits are unused.

<img width="837" height="250" alt="image" src="https://github.com/user-attachments/assets/04fc9a70-c548-476d-a56d-cfd995b539ac" />

Let us two cases:</br>
* Case1: assign q = count[0]
* Case2: assign q = count[2:0] == 3'b100

First we will discuss about case1 here.

let see what happens after synthesis; Here we can see that it in inferring only 1 D-FF but it is a 3 bit counter.

<img width="1918" height="988" alt="image" src="https://github.com/user-attachments/assets/d6cdd812-7ed1-405a-a400-368b9ea41b20" />

<img width="1910" height="1020" alt="image" src="https://github.com/user-attachments/assets/dc9e2feb-df1f-4ca6-9032-07c80d87c998" />

<img width="335" height="150" alt="image" src="https://github.com/user-attachments/assets/aaebdc08-1470-4d5a-84a3-f4b5f8aa7eb3" />

### Sky130RTL D3SK4 L2 Seq Optimization unused output part2
We will now modify the RTL.

```tcl
cp counter_opt.v counter_opt2.v
```

```tcl
gvim counter_opt2.v
```

As we are now doing Case2, make the changes as follows.

<img width="1918" height="1025" alt="image" src="https://github.com/user-attachments/assets/253dfe13-0e44-459d-ba4e-dd09aa7e4514" />

Now we have assigned all the three bits to the counter, so we expect all the bits to interact with the counter.</br>
If we do the synthesis, we will see 3 flops being present as all the bits are in use.</br>

<img width="1918" height="995" alt="image" src="https://github.com/user-attachments/assets/2977e8f0-6bf0-4345-b020-f9ab241839ee" />

<img width="1918" height="1026" alt="image" src="https://github.com/user-attachments/assets/af1fe244-48a8-4baa-b804-78b273ed8e42" />

If we see the circuit, as q = C[2].C[1]'.C[0]', the circuit will look like;

<img width="991" height="453" alt="image" src="https://github.com/user-attachments/assets/1d169182-70b5-4efd-a761-0e97a1ee11b6" />

Therefore here all the bits are in use, whereas in previous case only one of the bits were used and rest were optimized. 

# Day-5-Optimization in Synthesis
## If Case constructs
### Sky130RTL D5SK1 L1 IF CASE Constructs part1
Here we will see about **'IF'** and **'CASE'** statements and danger with 'CASE' statements.</br>
1) **if**: 
* It gives the priority logic
* Evaluates sequentially: top-to-bottom priority
* Syntax:
  ```tcl
  if (condition)
   begin
       statement;
   end
  else (condition)
   begin
       statement;
   end
  ```
  The top condition is of highest priority.</br>
  ```tcl
  if (condition1)
       statement;
  else if (condition2)
        c1;
  else if (condition2)
        c2;
  else if(condition3)
        c3;
  else (condition)
        E;
  end
  ```
  The priority order is condition1 > condition2 > condition3. So the hardware implementation will be as shown below.</br>

  <img width="348" height="287" alt="image" src="https://github.com/user-attachments/assets/ba75e54f-1208-4e9a-9bb3-ee1389186c9b" />

  **Danger/Caution with 'if'**: Called as "Inferred latches"
   We don't intend to put a latch, but this happens because of bad coding. Comes with incomplete "if" statement.

   e.g.

   ```tcl
   if (condition1)
       y=a;
   else if (condition2)
       y=b;
   end
   # There is no "else" condition specified
   ```
   
   Now if condition1 not happens and condition2 also not happens then the hardware will remain incomplete. Therefore the tool will try to Latch.
   It is very dangerous and should be avoided.

  <img width="358" height="269" alt="image" src="https://github.com/user-attachments/assets/29531cb1-f687-4045-8d49-6eed24d49e1d" />

### Sky130RTL D5SK1 L2 IF CASE Constructs part2
Let us take an example of a Counter;</br>

```tcl
always @ (posedge clk, posedge reset)
 begin
   if (reset)
          count <= 3'b00;
   else if (en)
          count <= count + 1;
 end
# although it is incomplete code but it is correct
```

Let' look at the hardware. (Always look for the harware).</br>
When the 'enable' pin is ON, the counter is count+1 but when it is OFF, counter latches the value to previous value. So this is intended behaviour.

Inferred Latches is fine for Sequential Circuits, but not fine for Combinational circuits.

<img width="335" height="272" alt="image" src="https://github.com/user-attachments/assets/6d8a6172-2245-468e-98b2-6def19acafd5" />

2) **Case** :
   * 'if' and 'case' are assigned inside `always` block; they should be assigned under `reg` value.
   * Used to implement multi-way branching, like a switch-case in C.
   * Good for implementing multiplexers, state machines, and decoders.
   * All case branches are evaluated simultaneously (unlike if).
   * You should always include a `default` case to avoid unintended latch inference.
  ```tcl
   always @(sel or c1 or c2)
begin
    case (sel)
        2'b00: out = c1;
        2'b01: out = c2;
        default: out = 1'b0;
    endcase
end
```
<img width="230" height="217" alt="image" src="https://github.com/user-attachments/assets/535b76ab-1606-455b-b4bd-dd2b88146a31" />

  **Caveats with case**:</br>
    1) Incomplete case --> Lead to "Inferred Latches"
       e.g. 
   ```tcl
reg [1:0] sel ; 
  always @(*) 
  begin
    case (sel)
        2'b00: begin
            out = c1;
        end
        2'b01: begin
            out = c2;
        end
    endcase
   end
# rest of the pins will be latched to the output
```

<img width="228" height="256" alt="image" src="https://github.com/user-attachments/assets/e7adb08f-93bd-4fac-ba38-e9b9638c541e" />

To avoid this we write code case with `default`

    e.g. 
   ```tcl
reg [1:0] sel ;
  always @(*) 
  begin
    case (sel)
        2'b00: begin
            out = c1;
        end
        2'b01: begin
            out = c2;
        end
        default: begin
            out = 1'b0;
        end
    endcase
   end
# with deafult we avoid inferred latches
```

   2) Partial Assignment in "case": </br>
      Suppose we are trying to control two outputs in "case".</br>
      
      e.g.
      
      ```tcl
      reg [1:0] sel;
      reg x, y;
      always @ (*)
       begin
          case (sel)
              2'b00: begin
                 x = a;
                 y = b;
              end
              2'b01: begin
                 x = c;
              end
              default: begin
                 x = d;
                 y = b;
              end
          endcase
       end
      # We have assigned the value for select line '0', but when select line is '1' only value for x is assigned and not y.
      ```

      Partial assignment leads to inferred latches.

<img width="295" height="315" alt="image" src="https://github.com/user-attachments/assets/8e5fba6c-4b74-41c7-9094-6bb51c14429d" />

*Note: Assign all the outputs in all the segment of case.*

   3) Comparison between 'if' and 'case' statements: </br>
      **if**
      
      ```tcl
      if    # highest priority
      else if
      else if
      else  # lowest priority
      ```

      In case of 'if' only one segment executes at a time following the priority order.</br>

      **case**

      ```tcl
      case (sel)
         2'b00:
         2'b01:
         2'b10:
         2'b1?: #one bit not specified
      endcase
      ```

      In case of a bad code as given here both 2'b10 and 2'b11 can execute at the same time giving unpredictable outputs. Therefore we should not have overlapping        case.</br>

## Labs on "Incomplete If Case"
### Sky130RTL D5SK2 L1 Lab Incomplete IF part1
We will see how the synthesis and simulator behaves when there is "incomplete if and case".

Our files required here are  inside `*incomp*`.

<img width="1657" height="816" alt="image" src="https://github.com/user-attachments/assets/16320ed2-c045-45f4-8a2f-405cc26fb209" />

We will open all the files; `gvim *incomp* -o` and start with "incomplete if";

<img width="1655" height="812" alt="image" src="https://github.com/user-attachments/assets/fbfc3ab1-3e5f-4c1f-ae4e-76b1bbfa62c2" />

Let us look at the harware, here if always translates into a 'Mux'. So here select line is `i0`, if we `i0` is '1' output is 1 but else part is missing so `i0 = 0`, it will be latched.

<img width="291" height="217" alt="image" src="https://github.com/user-attachments/assets/1886234f-119a-4482-88cd-1ec197659ab0" />

The behaviour of this mux is similar to D-latch which latch enable as `i0`. It's a poselatch. Whenever `i0` is present `i1` is seen on y, whenever absent it latches on to it's value.

<img width="216" height="177" alt="image" src="https://github.com/user-attachments/assets/455a0962-ffd2-40e8-88a0-d1b21963502a" />

Let's see the simulation and synthesis;
* **Simulation**
  ```tcl
  iverilog incomp_if.v tb_incomp_if.v
  ```
  ```tcl
  ./a.out
  ```
  ```
  gtkwave tb_incomp_if.vcd
  ```
Here we can see that when `i0` is high, output 'y' is following input, but when `i0` is low, y becomes a latch on`i1` and remains constant throughout.

<img width="1657" height="806" alt="image" src="https://github.com/user-attachments/assets/a3e6ccb7-b629-41c0-8376-ffbdd5b1ac18" />

* **Synthesis**
  ```tcl
  yosys
  ```
  ```tcl
  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  ```tcl
  read_verilog incomp_if.v
  ```
  ```tcl
  synth -top incomp_if
  ```
  ```tcl
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  ```tcl
  show
  ```

  <img width="1656" height="802" alt="image" src="https://github.com/user-attachments/assets/cb87a6b6-b6d2-4bf6-8159-1339bfd5b1fb" />

  <img width="1650" height="801" alt="image" src="https://github.com/user-attachments/assets/d5fa98ab-4ce5-4368-b9e3-cfb0cd8274f9" />

  We can clearly see it's a D-latch and not a mux due to "incomplete if" statement.

### Sky130RTL D5SK2 L2 Lab Incomplete IF part2
Now let us see `incomp_if2.v`

<img width="1657" height="807" alt="image" src="https://github.com/user-attachments/assets/689baa95-c2f6-4f05-8fe7-346fdf5951c9" />

Considering the hardware, it has two mux where else past is missing, so it will latch as shown below.

<img width="387" height="245" alt="image" src="https://github.com/user-attachments/assets/dd2e808c-78e4-46ec-ab5f-1c7b6d952426" />

It will represent a D-latch where EN is when any of `i0` and `i2` can exist, so it will be ORed. At the input there will be a combined circuit of the multiplexer with values of `i0`, `i1`, `i2` and `i3`.

<img width="578" height="316" alt="image" src="https://github.com/user-attachments/assets/0c73f25a-5e20-48b6-978e-491d25315e21" />

Now we will Simulate and Synthesize and see if it shows similar behaviour or not.
The steps followed are same as in previous case.

<img width="1660" height="812" alt="image" src="https://github.com/user-attachments/assets/def9d297-4d12-4792-9f0f-ba78b3114fce" />

* We can see whenever `i0 = 1`--> Output 'y' is following `i1`.
* When `i0 = 0` --> it looks towards `i2`:
    * When `i2` is low --> output is constant
    * when `i2` is high --> output starts following `i3`

Now let's synthesize:

<img width="1656" height="803" alt="image" src="https://github.com/user-attachments/assets/794529ee-1edd-40b7-bfdc-c396e020cbc0" />

We got the same what we expected.

## Lab on "Incomplete overlapping case"
### Sky130RTL D5SK3 L1 Lab Incomplete overlapping Case part1
Here we will discuss about the "case" statements labs in detail.

Let's open all the required files; ```gvim comp_case.v -o incomp_case.v -o partial_case_assign.v -o bad_case.v```.

<img width="1665" height="811" alt="image" src="https://github.com/user-attachments/assets/05f10222-497d-40fb-a869-37c8923379c6" />

First, we will look into ```incomp_case.v```

<img width="1658" height="812" alt="image" src="https://github.com/user-attachments/assets/7247f189-9301-4187-a69a-640561a470c3" />

According to the code it is clear that if 'select' is '00', `i0` will be selected and for select line '01' `i1` will be selected. But for '10' and '11' there is no input and also `default` statement is missing, so it will latch. Also the enabling condition for latch is sel[1]'.

<img width="316" height="246" alt="image" src="https://github.com/user-attachments/assets/8a50815f-a0de-4ae4-b9e3-bdf36ea77d1a" />

The logic we are expecting is a D-latch, when the select[1] is '0' the output is same as input, but when selct[1] is '1' the output is latched.

<img width="585" height="282" alt="image" src="https://github.com/user-attachments/assets/5c7a1de8-1c54-4851-9104-2ce8075e34c8" />

Let us do the functional simulation:
```tcl
iverilog incomp_case.v tb_incomp_case.v
```
```tcl
./a.out
```
```tcl
gtkwave incomp_case.vcd
```

<img width="1662" height="806" alt="image" src="https://github.com/user-attachments/assets/3dce5431-91f7-4400-885c-fec45dd306d4" />

When select is '00' y is following `i0`</br>
When select is '01' y is following `i1`</br>
The moment select is becoming '11' or '10', y is latching to that value.</br>

Let us now to the synthesis:
```tcl
  yosys
  ```
  ```tcl
  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  ```tcl
  read_verilog incomp_case.v
  ```
  ```tcl
  synth -top incomp_case
  ```
  ```tcl
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  ```tcl
  show
  ```

<img width="1660" height="813" alt="image" src="https://github.com/user-attachments/assets/24c53605-bc94-49b2-8925-f1d48c4abdee" />

<img width="1662" height="811" alt="image" src="https://github.com/user-attachments/assets/0626c360-0f32-43a7-bcbf-89f7a9f87173" />

### Sky130RTL D5SK3 L2 Lab Incomplete overlapping Case part2
Now we will look into the complete case; ```comp_case.v``` file. We can see here everything is same except that we added `default`.

<img width="1652" height="808" alt="image" src="https://github.com/user-attachments/assets/99c92b12-6771-4dae-96bd-72021c4555f6" />

The hardware looks something as shwon below.

<img width="473" height="307" alt="image" src="https://github.com/user-attachments/assets/214033f9-0893-4038-86d6-5a9c11dcf55b" />

Let's see the simulation and synthesis

* **Simulation**
  We can see when select is '10' or '11' it is exactly following `i2`. There is no latching action.

  <img width="1655" height="811" alt="image" src="https://github.com/user-attachments/assets/dcd159bb-86b1-4e37-8180-46c4a6b34318" />

* **Synthesis**
  Upon synthesis we can see that there is no latch present.

  <img width="1656" height="812" alt="image" src="https://github.com/user-attachments/assets/1acbd8f9-a3f6-4801-9916-ba7298c9b7d5" />

  <img width="1660" height="817" alt="image" src="https://github.com/user-attachments/assets/b35ae00e-19c8-4760-a07f-85e0b6e650f4" />

Let us look at the `partial_case_assign.v` file as well.

<img width="1657" height="800" alt="image" src="https://github.com/user-attachments/assets/24b98256-c140-4098-8472-81aa3cce3371" />

Here there are two outputs, x and y. Even though `default` is mentioned in the code, it is not complete.

<img width="548" height="241" alt="image" src="https://github.com/user-attachments/assets/70a1258e-34fd-4c64-bdfb-2301a291cf6f" />

WHat is the condition for latching. Latch enable condition is sel[1] + sel[0]'.

### Sky130RTL D5SK3 L3 Lab Incomplete overlapping Case part3
let us synthesis ```partial_case_assign.v```

<img width="1661" height="811" alt="image" src="https://github.com/user-attachments/assets/32e8a56f-f871-4cbf-b8d6-33b02b371a3b" />

We can see here in the path of 'y' there is no latch but in the path of 'x' there is a latch.

<img width="1658" height="808" alt="image" src="https://github.com/user-attachments/assets/d0099e7a-da1a-4498-b28b-2a5c01c52803" />

Let us see ```bad_case.v``` file.</br>
In 'case' statements there can be execution of two logics at the same time which casues mismatch if there is a bad case.

<img width="1652" height="808" alt="image" src="https://github.com/user-attachments/assets/69886f70-ac29-4e74-b0dc-6148c97b4731" />

Here, for 2'b10 `i2` is assigned and for input 2'b1? `i3` is assigned. So simulator will try to execute both at the same time. Simulations will be getting confused with each other.

<img width="1657" height="810" alt="image" src="https://github.com/user-attachments/assets/a7be833a-0997-4c1f-9461-9cb61a12f9c0" />

We can clearly see when the select is '11' the output is getitng latched, the simulator is not able to decide the output, it is getting confused whar to execute.

### Sky130RTL D5SK3 L4 Lab Incomplete overlapping Case part4
Since the code is code is complete, we will not ahve an inferred latch here but we are having problem with execution as it is a bad case.

Let us Synthesize the code:</br>
```tcl
  yosys
  ```
  ```tcl
  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  ```tcl
  read_verilog bad_case.v
  ```
  ```tcl
  synth -top bad_case
  ```
  ```tcl
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  ```tcl
  write_verilog -noattr bad_case_net.v
  ```
  ```tcl
  show
  ```
After synthesis we can observe that there are no latches as we expected.</br>

<img width="1657" height="807" alt="image" src="https://github.com/user-attachments/assets/080002e4-3ced-4951-9067-825d630683b8" />

after the synthesis, do simulations;
```tcl
# read the standard cell models, netlist and the test bench
iverilog ../my_lib/verilog_model_primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_case_net.v tb_bad_case.v
```
```tcl
./a.out
```
```tcl
gtkwave tb_bad_case.vcd
```

<img width="1662" height="808" alt="image" src="https://github.com/user-attachments/assets/91c9fcdf-a6bf-4e26-bb01-766fd35213e7" />

Now we can see that at select line '11' it is not constant and behaving as `i3`. Hence there is no latching action here.

<img width="1658" height="805" alt="image" src="https://github.com/user-attachments/assets/cb309cd3-7c9b-42a9-9395-eee555e5f31f" />

## for loop and for generate
### Sky130RTL D5SK4 L1 For Loop and For Generate part1
We will now use an important switch "for loop" and "for generate" constructs to generate any hardware.

| Feature             | `for` Loop (Behavioral)                        | `generate for` Loop (Structural)                        |
|---------------------|------------------------------------------------|---------------------------------------------------------|
| Purpose             | For iterating inside `always` blocks           | For generating hardware blocks                          |
| Used In             | Simulation (RTL/testbench)                     | Elaboration/Synthesis                                   |
| Loop Variable       | `integer`                                      | `genvar`                                                |
| Execution Time      | At simulation time                             | At compile/elaboration time                             |
| Use Case            | Iterating logic or array manipulation          | Instantiating multiple module copies                    |
| Syntax Scope        | Inside `always` block                          | Inside `generate` block                                 |
| Common Application  | Data processing, testbench loops               | Bus logic, N-bit registers, scalable designs            |
| Synthesis Friendly  | Only if correctly used (no infinite loops)     | Yes (specifically meant for synthesis)                  |

Example:
**For Loop**
* 2:1 mux
  ```verilog
  always @(*) begin
   case (sel)
      1'b0 : y = i0;
      1'b1 : y = i1;
   endcase
  end
  ```
* 4:1 mux
 ```verilog
  always @(*) begin
   case (sel)
      3'b00 : y = i0;
      3'b01 : y = i1;
      3'b10 : y = i2;
      3'b11 : y = i3;
   endcase
  end
```
* 32:1 mux
  ```verilog
  always @(*) begin
   case (sel)
      5'b00000 : y = i0;
      5'b00001 : y = i1;
      5'b00010 : y = i2;
      5'b00011 : y = i3;
      .
      .
      .
      5'b1111 : y = i31;
   endcase
  end
  ```
But we can't write big codes like this, this is where the power of "Blocking statements" comes into picture.





















































      


   
    
        


   
   









  

   
  




























  
























  

  











 


 

 



























   















  

  
  
  


  

















  






     

     



     



















    




   








































































  












  
