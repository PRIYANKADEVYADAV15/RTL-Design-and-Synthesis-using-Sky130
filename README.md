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
![Uploading image.png…]()










    




   








































































  












  
