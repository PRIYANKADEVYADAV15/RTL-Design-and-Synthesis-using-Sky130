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
  - [Labs using Yosys and Sy130 PDKs](#Labs-using-Yosys-and-Sy130-PDKs)
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

## Labs using Yosys and Sy130 PDKs
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
4) ```abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
   As there is nothing to synthesize, so it will show nothing to map.
5) ```show```
   <img width="1918" height="1038" alt="image" src="https://github.com/user-attachments/assets/e61cf19a-3c31-430d-bf1d-a04302a8b14e" />















  

  
  
  


  

















  






     

     



     



















    




   








































































  












  
