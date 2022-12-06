
# Syahrul Nazri-Intel SD Training 

## Table of contents
* [ Day 0 - System/Tool Setup Check. GitHub ID creation ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-0)
* [ Day 1 - Labs using iverilog and gtkwave ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-1)
* [ Day 2 - Timing libs,hierarchical vs flatsynthesis and effecient flop coding styles ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-2)

## Day 0
### Topic - System/Tool Setup Check. GitHub ID creation

**Package** is a container that holds die and was connected to outside (external device) by using wire bonding.
Example of package - Quadruple in-line package (QIP) and Dual in-line package (DIP).

<img width="628" alt="note1" src="https://user-images.githubusercontent.com/118953939/203918518-83e1ebe2-6916-4413-8744-d658031c02b4.PNG">

**Quad Flat Package(QFP)**-A quad flat package (QFP) is a surface-mounted integrated circuit package with "gull wing" leads extending from each of the four sides.

**Wafer Level Chip Scale Package (WLCSP)** - variant of the flip-chip interconnection technique where all packaging is done at the wafer level
![wlcsp](https://user-images.githubusercontent.com/118953939/203919063-b82fb9f6-838d-4b7b-a10b-52427af17cf0.gif)

* **Wire Bond** - The method of making interconnections between an integrated circuit (IC) or other semiconductor device and its packaging during semiconductor device fabrication.
* **Pad** - used to connect inside (core) to outside (I/O), good at ESD protection to prevent charge coming from outside damage the core inside.
* **Core** - consists of all the main logic gate (NMOS/PMOS) and cell block such as macro cell and foundry IP's.
* **I/O** - help in communication between die with external and will be connected to die by using wire bonding.
* **Macro** - a simple core/cell with simple functionality and can be easily found online.
* **Foundry IP's** - cell with more specific functionality and the design was patent/owned by a company. Has higher value compared to macro.

**Synthesis Flow** - convert software's instructions which is written in high level language to gate level language/machine language which is normally in binary format.

<img width="808" alt="3" src="https://user-images.githubusercontent.com/118953939/203920288-65b97ed6-e0c0-4679-a99e-4618555f3209.PNG">


### Lab Result

<img width="959" alt="labday0" src="https://user-images.githubusercontent.com/118953939/205489130-4253ae38-30fa-458d-9cea-a238e9445fd1.PNG">


## DAY 1
### Topic-Lecture Video  Introduction to iverilog design test bench 

**What is Simulator ?**

The tools that used to checking the design for example iverilog 

**Design ?**

Actual Verilog code or set of verilog code which has the intended functionality to meet with the required specifications. 

**TestBench ?** 

To obey the required specification or the setup to apply stimulus  to the design to check its  functionality. 

**How simulator works ?** 

-changes value of the inputs. 

![GetImage](https://user-images.githubusercontent.com/118953939/205494417-a25becfa-e3d3-484d-9e90-b0db171bf96e.png)

![GetImage (1)](https://user-images.githubusercontent.com/118953939/205494411-6372f70c-ca9e-4af6-9ea4-795fc3e24f4c.png)

* **Hdl=** hardware description language  
           Others ways than HDL is high level Synthesis(HLS) 
* **IVerilog=** compiler translates verilog code to executable programs. 
* **GTKWave=** analysis tool used to perform debugging on Verilog or VHDL. 
* **Syntax Analysis:** Takes input of HDL files and checks for syntax errors. 
* **Library Definition:** Provides and allocates standard cells and IP libraries. 
* **Elaboration and Binding:** Translates RTL into the Boolean structure. Binds all cells and  makes libraries available. 
* **Constraint Definition:** For building a customized and specific chip, we need to define constraints according to which the chip will function. For example, clock frequency, power efficiency, etc. 
* **Pre-mapping Optimization:** It performs mapping to generic cells in the library. 
* **Technology Mapping:** Performs mapping of the generic libraries to technology 
libraries. 

------------------------------------------------------------------------------------------------------

### Topic = Lecture video Introduction to Yosys and Logic synthesis 

**What is Synthesizer?** 
-Tool that used for converting the RTL to netlist 
-Yosys is the synthesizer used in this course. 

![GetImage (2)](https://user-images.githubusercontent.com/118953939/205494889-542c0afd-d07e-422a-b146-991b5bc650e7.png)

* **Read_verilog=** To read the design  
* **Read_liberty=** To read .lib 
* **Write_Verilog=** to write netflist file  
* **.lib=** collection of logical module  like And,Or,Not  

**How to verify the Synthesis**
* Netlist & test bench(same as RTl tb)  -->iverilog --> vcd file --> gtkwave(same as output aboserve during RTL simulation)

------------------------------------------------------------------------------------------------------

### Topic - Introduction to lab 

**Combinational delay in logic path**
* **Why need Fast Cell?**
- To meet setup,meen the time needed for the data stable before clock edge.
- Tclk> TF1+Tcombi+TsetupofF2 (data must be stable before the capturing edge of clock)

* **Why need Slow Cell?**
-Slow cell needed to meet hold,means the time need to data stable after clock edge.
-TholdF2<TF1+Tcombi

------------------------------------------------------------------------------------------------------

### Topic - Labs Introduction

* Using command **git clone** https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git

* **GitClone**= used to point to an existing repo and make a clone or copy of that repo at in a new directory.

<img width="933" alt="lab2part2Code" src="https://user-images.githubusercontent.com/118953939/205489471-073f46d8-b430-465b-aef0-5216a69a781c.PNG">

------------------------------------------------------------------------------------------------------

### Topic - Labs using iverilog and gtkwave
1.Open Output File using GTKWAVE
* Output waveform using command **gtkwave tb_godd_mux.vcd**
* 
<img width="962" alt="lab2waveform" src="https://user-images.githubusercontent.com/118953939/205324453-9eb7165e-7d6f-47f8-905a-2bd511f4593b.PNG">'
When the sel=1 the output y will follow input i1 but when the input sel=0 the output y will follow the input=i0

2.RTL code 
* RTL code for  **tb_good_mux.v** and **good_mux.v**

<img width="382" alt="vimcode" src="https://user-images.githubusercontent.com/118953939/205324818-34a12188-1419-425f-88fd-ba0018f80a47.PNG">

<img width="449" alt="vimcode2" src="https://user-images.githubusercontent.com/118953939/205324920-6ad1c570-7f5a-4619-8cbf-c4a4fda100bf.PNG">

------------------------------------------------------------------------------------------------------

### Topic-Lab using Yosys and Sky130PDKs

1.How to open Yosys
* Using command **yosys** 
<img width="528" alt="Openyosys" src="https://user-images.githubusercontent.com/118953939/205490668-1637ca90-4ba6-421a-8ce9-26b5c8ba860f.PNG">


2.Read Liberty 
* Using command **read_liberty -lib path of lib** 
<img width="346" alt="read_liberty" src="https://user-images.githubusercontent.com/118953939/205490674-7ccee751-fe63-4866-91df-79e91b79a368.PNG">


3.Read the design 
* Using command **read_verilog good_mux.v**
<img width="296" alt="readdesign " src="https://user-images.githubusercontent.com/118953939/205490680-081022c7-9035-4cb0-9d0a-2e4dc03d0b21.PNG">


4.Synthesize the module 
* Using command **synth -top good_mux**
<img width="298" alt="top" src="https://user-images.githubusercontent.com/118953939/205496851-fe6d4c8e-403e-42e9-8f72-fb21c7ce2994.PNG">


5.Convert RTl code and specified gate design  
* Using command **abc -liberty**
<img width="740" alt="Generating rtl code to netlist " src="https://user-images.githubusercontent.com/118953939/205490960-e0caca40-74a3-4d4b-b904-e847b0e38577.PNG">

<img width="481" alt="genpart2" src="https://user-images.githubusercontent.com/118953939/205490966-66dd3f9b-2870-44cc-8352-32ae6ab42084.PNG">

<img width="492" alt="genpar3" src="https://user-images.githubusercontent.com/118953939/205490975-f8414c28-1c3a-48a7-864c-104ce7a84b12.PNG">
There are 3 input signals,1 output signals and 0 internal signals.


6.Show the gate design
* Using command **show**
<img width="656" alt="show" src="https://user-images.githubusercontent.com/118953939/205490977-c7929ce8-64e3-4f6f-a01a-4cfea35db691.PNG">

i0,i1 and sel is primary input.


7.Show the netlist
* Using command **write_verilog good_mux_netlist.v** 
* Using vim to open the scripting  **!vim write_verilog good_mux_netlist.v** 
<img width="440" alt="show netlist" src="https://user-images.githubusercontent.com/118953939/205492020-6ebaf762-7f59-4e2e-beb8-d63bfc1d1bc5.PNG">


8.Make the netlist more simple 
* Using command  **write_verilog -noattr good_mux_netlist.v**
* Using command  **gvim good_mux_netlist.v**
<img width="483" alt="modified " src="https://user-images.githubusercontent.com/118953939/205492030-b8579566-06ba-4ee7-bec8-c9a854b49fa2.PNG">


### Day 2

### Topic-Lab Introduction to .Lib 

1.Open .lib content 
* **vim../my_lib/lib/sky130_fd_sc_hd_tt_025C_1v80.lib**
* :syn off --->switch off the syntax
<img width="275" alt="0PNG" src="https://user-images.githubusercontent.com/118953939/205858752-781f8077-b72c-4ca8-8706-0af672aa04a1.PNG">

**Tt=** typical(fas/slow/typical)
**C=** temperature 
**V=** voltage 

2.lib content of the std cell
* Each cell have different flavour  and in the lib we can see all the detail of the cell.

<img width="348" alt="3" src="https://user-images.githubusercontent.com/118953939/205858806-16963ea3-f24d-4b15-9414-4e53bbeb9532.PNG">

<img width="794" alt="1" src="https://user-images.githubusercontent.com/118953939/205858861-1afdbfa5-0791-47ff-9299-4f3dda5e6f03.PNG">
* As we can see from the figure above,in the circle shows the  gate with 5 input and  have the 32 input possible combination.To see all the detail command **:vsp ../my_lib/verilog_model/sky130_fd_sc_hd.v"** 

* The lib also shows the other detail such as power pot and information of the each cell pin

![image](https://user-images.githubusercontent.com/118953939/205938000-279e0c20-2f30-4bcc-bd8b-7fd9c4a0be2e.png)
*Figure above shows the area and power port information. 
![image](https://user-images.githubusercontent.com/118953939/205938060-ff56c886-66b1-46cb-858a-69617719ea36.png)
*Figure above shows the information of capacitance,transition,power associated to the pin.*
* In the lib also shows the timing information 

![image](https://user-images.githubusercontent.com/118953939/205939075-a263e287-4781-4565-8933-2eb09a263d0e.png)

* Lastly,the comparison of the 3 types of cell :And2_0,And_2 & And_4
![image](https://user-images.githubusercontent.com/118953939/205939144-08b4a37f-5877-4b43-a8ca-3b3779376878.png)
*As we can see form the figure above when the area large the power will be more and delay will be less.But when area low,the power will low and delay will more.*

-------------------------------------------------------------------------

### Topic-hierarchical vs FLat Synthesis 

* **Setup Design**

i)Gvim multiple_module.v

ii)Launch yosys 

iii)Read_liberty –lib ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

iv)Synth –top multiple module

v)Abc –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

vi)Show multiple_module 

vii)write_verilog multiple_modules_hier.v



![image](https://user-images.githubusercontent.com/118953939/205958229-b10636d0-3215-4402-b75c-5d3e35e9cbc5.png)
![image](https://user-images.githubusercontent.com/118953939/205958260-6421517a-61f2-4aeb-bb5e-8a2fe6acc867.png)
![image](https://user-images.githubusercontent.com/118953939/205958288-8c0a0a8c-5909-4dd6-b72f-73805aacc080.png)
*As you can see from the figure above the module was devided to 2 which is module 1 and module 2.Module 1 was and2 gate and module 2 was or2 gate.*
