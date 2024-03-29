
# Syahrul Nazri-Intel SD Training 

## Table of contents
* [ Day 0  -System/Tool Setup Check. GitHub ID creation ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-0)
* [ Day 1  -Labs using iverilog and gtkwave ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-1)
* [ Day 2  -Timing libs,hierarchical vs flatsynthesis and effecient flop coding styles ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-2)
* [ Day 3  -Combinational and Sequential Optimizations](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day3)
* [ Day 4  -GLS,Blocking vs Non-blocking and Synthesis-Simulation mismatch](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day4)
* [ Day 5  -Design of Testability](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day5)
* [ Day 6  -Introduction Logic Synthesis](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-6)
* [ Day 7  -Basic of Static Timing Analysis(STA)](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-7)
* [ Day 8  -Advance Constraints](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-8)
* [ Day 9  -Optimizations](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-9)
* [ Day 10 -Quality Checks ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-10)
* [ Day 11 -Baby SoC  ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-11)
* [ Day 12 -Baby SoC Modelling ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-12)
* [ Day 13 -Post-Synthesis](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-13)
* [ Day 14 -PVT Corner](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-14)
* [ Day 15 - Inception of EDA and PDK ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-15)
* [ Day 16 - Good Floorpan vs Bad Floorplan and Introduction to Library cells ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-16)
* [ Day 17 -Design Library cell using Magic layout and Ngspice characterization  ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-17)
* [ Day 18 - Pre-layout timing analysis and importance of good clock tree](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-18)
* [ Day 19 - Final steps for RTL2GDS using tritonroute and open STA](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-19)
* [ Day 20 - Physical Design flow ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-20)
* [ Day 21 - Placement and  CTS ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-21)
* [ Day 22 - Analysis CTS  ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-22)
* [ Day 23 - Clock Gating Technique  ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-23)
* [ Day 24 - ECO Timing  ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-24)
* [ Day 25 - RISC-V core RTL2GDS flow ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-25)
* [ Day 26 - Introduction to mixed-signal flow  ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-26)
* [ Day 27 - Introduction to crosstalk - glitch and delta delay ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-27)
* [ Day 28 & 29 -  Introduction and DRC/LVS ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-28--29)

## Day 0
### Topic - System/Tool Setup Check. GitHub ID creation
<Details>
 <summary>Theory</summary>
 
### Theory 
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

<img width="808" alt="3" src="https://user-images.githubusercontent.com/118953939/203920288-65b97ed6-e0c0-4679-a99e-4618555f3209.PNG">\
</details>

<details>
 <summary>Lab Results</summary>
 
### Lab Result


<img width="959" alt="labday0" src="https://user-images.githubusercontent.com/118953939/205489130-4253ae38-30fa-458d-9cea-a238e9445fd1.PNG">

</details>
  
## DAY 1

### Topic-Introduction to Verilog RTL design and Synthesis 
<details>
 <summary>Lecture Video  Introduction to iverilog design test bench</summary>
 
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
</details>

<details>
 <summary>Lecture Video Introduction to Yosys and Logic Synthesis</summary>

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
</details>

  <details>
 <summary>Introduction to Lab</summary>

### Topic - Introduction to lab 

**Combinational delay in logic path**
* **Why need Fast Cell?**
- To meet setup,meen the time needed for the data stable before clock edge.
- Tclk> TF1+Tcombi+TsetupofF2 (data must be stable before the capturing edge of clock)

* **Why need Slow Cell?**
-Slow cell needed to meet hold,means the time need to data stable after clock edge.
-TholdF2<TF1+Tcombi
 </details>

 <details>
 <summary>Lab Introduction</summary>

### Topic - Labs Introduction

* Using command **git clone** https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git

* **GitClone**= used to point to an existing repo and make a clone or copy of that repo at in a new directory.

<img width="933" alt="lab2part2Code" src="https://user-images.githubusercontent.com/118953939/205489471-073f46d8-b430-465b-aef0-5216a69a781c.PNG">

</details>

 <details>
 <summary>Lab Using iverilog and gtkwave</summary>
  
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

 </details>
 
 <details>
 <summary>Lab Using Yosys and Sky130PDKs</summary>

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
 </details>

## Day 2

### Topic-Timing libs,hierarchical vs flat synthesis and efficient flop coding styles
 <details>
 <summary>Lab Introdcution to .lib</summary>

### Topic-Lab Introduction to .Lib 

1.Open .lib content 
*  vim../my_lib/lib/sky130_fd_sc_hd_tt_025C_1v80.lib
* :syn off --->switch off the syntax
![image](https://user-images.githubusercontent.com/118953939/206341510-fe0978a6-2175-4184-823e-75cd08a80c0b.png)
<img width="275" alt="0PNG" src="https://user-images.githubusercontent.com/118953939/205858752-781f8077-b72c-4ca8-8706-0af672aa04a1.PNG">

**Tt=** typical(fast/slow/typical)
**C=** temperature 
**V=** voltage 

2.lib content of the std cell
* Each cell have different flavour  and in the lib we can see all the detail of the cell.*

<img width="348" alt="3" src="https://user-images.githubusercontent.com/118953939/205858806-16963ea3-f24d-4b15-9414-4e53bbeb9532.PNG">

<img width="794" alt="1" src="https://user-images.githubusercontent.com/118953939/205858861-1afdbfa5-0791-47ff-9299-4f3dda5e6f03.PNG">
>*As we can see from the figure above,in the circle shows the  gate with 5 input and  have the 32 input possible combination.To see all the detail command* **:vsp ../my_lib/verilog_model/sky130_fd_sc_hd.v"** 

>*The lib also shows the other detail such as power pot and information of the each cell pin*

![image](https://user-images.githubusercontent.com/118953939/205938000-279e0c20-2f30-4bcc-bd8b-7fd9c4a0be2e.png)
>*Figure above shows the area and power port information.* 
![image](https://user-images.githubusercontent.com/118953939/205938060-ff56c886-66b1-46cb-858a-69617719ea36.png)
>*Figure above shows the information of capacitance,transition,power associated to the pin.*
* In the lib also shows the timing information 

![image](https://user-images.githubusercontent.com/118953939/205939075-a263e287-4781-4565-8933-2eb09a263d0e.png)

* Lastly,the comparison of the 3 types of cell :And2_0,And_2 & And_4
![image](https://user-images.githubusercontent.com/118953939/205939144-08b4a37f-5877-4b43-a8ca-3b3779376878.png)
*As we can see form the figure above when the area large the power will be more and delay will be less.But when area low,the power will low and delay will more.*

 </details>
 
 <details>
 <summary>Hierarchical vs Flat Synthesis</summary>

### Topic-hierarchical vs FLat Synthesis 
  
i)vim multiple_module.v

ii)Launch yosys 

iii)Read_liberty –lib ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

iv)Synth –top multiple module

v)Abc –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

vi)Show multiple_module 

vii)write_verilog -noattr multiple_modules_hier.v

**Result**

![image](https://user-images.githubusercontent.com/118953939/206330522-d9c4ff26-360d-4dba-bd25-c4d37dc4933b.png)
![image](https://user-images.githubusercontent.com/118953939/206330550-46a98643-a9b5-4f7a-80ec-b1d971db2710.png)
![image](https://user-images.githubusercontent.com/118953939/206331720-5a7c59cc-6e47-4cc6-9be5-f95c1b0dde5d.png)


* **Flat Synthesis**
>* Flatten
>* Write_verilog -noattr multiple_modules_flat.v
>* !vim multiple_modules_flat.v

>*The diagram below compares the hierarchy to the flat. We only see the net netlist in flat, and the modules for 1 and 2 are not visible.*
![image](https://user-images.githubusercontent.com/118953939/206075155-e587e8d2-2df2-4624-9372-17474f01b4c8.png)
*The diagram below also shows the multiple modules netlist.The output of U! will be input to the U2 and with another input coming from C.*
![image](https://user-images.githubusercontent.com/118953939/206075469-12b7e8dd-4977-41d3-8d4d-1404dce8d7b4.png)

>*Figure Below shows the slack PMOS and slack NMOS .Slack PMOS is always bad, and it requires a wide cell to improve.*
![image](https://user-images.githubusercontent.com/118953939/206349611-6f629aa5-29bf-47c8-b342-2c68e7d5a905.png)


* **Excuting the Sub module 1 & 2**

>i) yosys

>ii) read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib

>iii) read_verilog multiple_modules.v

>iv) synth -top sub_module1 --> If want to see module 2 change it to sub_module2

>v) abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib

>vi) show 

>*As you can see the figure below is sub module 1 and sub module 2*
![image](https://user-images.githubusercontent.com/118953939/206332888-e96cfcbf-6103-464e-885d-dc8454cb4258.png)


* **Why sub module level synth**

(a)When we have multiple instances of same module.

(b)Devide and conquer approach .Instead giving massive to the tool better to give in one portion.

 </details>
 
 <details>
 <summary>Why Flops and Flop Coding Styles</summary>
  
### Topic-Why Flops and Flop coding styles 

>There are many of the gate in the combinational circuit that lead to the glitch.So glitch is the result when an input signal changes state, provided the signal takes two or more paths through a circuit  and one path has a longer delay than the other. The increased delay on one path can cause a glitch when the signal paths are recombined at an output gate.To prevent this glitch we need flop.
![image](https://user-images.githubusercontent.com/118953939/206349620-b7212ab4-ae30-46f2-a74d-3a759d361ba7.png)

* **Why we need Flop**
> To avoid the glitch 
> Output will be stable or setlle down.
> To initialise the flop will need reset or set.Both of this can be asynchronous and synchronous.


* **DFF asynchronous**
>The output of DFF will triggered when the posedge clock and posedge async_reset.If the async_reset the output will be low else the output will follow the input D.This asynchronous reset does not wait for the clock or inrespective of clockThis synchronous reset respective to the clock.So,diagram below shows the comparison of flop with Synchronous and asynchronous or both of it.
![image](https://user-images.githubusercontent.com/118953939/206349631-75774c3b-3fc0-4565-befb-1ae412288bef.png)
</details>
 
<details>
 <summary>Lab Flops Synthesis Simulation</summary>

### Topic- Lab Flops synthesis simulation
**Steps**
>* iverilog dff_asyncres.v tb_dff_asyncres.v
>* ./a/out 
>* gtkwave tb_dff_asyncres.vcd
![image](https://user-images.githubusercontent.com/118953939/206333736-945ecfd2-1bd3-4158-af50-b1b0b7023244.png)

>*As from figure below,when reset low before clock,the output q  not immediately going to 1 but it wait for the clock edge .So,D align with the clock and q synchronous to the clock*
![image](https://user-images.githubusercontent.com/118953939/206140716-3b79cf85-9346-4a22-829f-69e512d8615d.png)
 
 >*Diagram below shows the when reset become the 1,the q automatically become 1 and not waiting to the clock edge.* 
![image](https://user-images.githubusercontent.com/118953939/206140751-4857b0bf-bb86-407c-929d-87488b8d821c.png)

>*When async_set=0 the,q follow the D respective to clock.*
![image](https://user-images.githubusercontent.com/118953939/206141715-6831ef51-937a-43a1-9134-924d555fa65d.png)

>*Async_set=1 the output q follow the async_set not effected by D* 
![image](https://user-images.githubusercontent.com/118953939/206143006-993866cf-a6ce-4bc5-aa9b-0aa26c7d352d.png)

>*When Sync_reset was 1,the output of y was change to 0 no immediately because it follow the clock edge.*
![image](https://user-images.githubusercontent.com/118953939/206143074-83a0e5fe-38e5-403f-8c18-e2b0e263579d.png)

* **Synthesis**
**1. Read asyncrhronous reset** flop netlist
>i) yosys

>ii)Read_liberty –lib ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>iii)read_Verilog dff_asyncres

>iv)Synth –top dff_asyncres

>v)Dfflibmap –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>vi)Abc –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>vii)Show

**2. Read asyncrhronous set**

>i)Read_liberty –lib ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>ii)read_Verilog dff_async_set

>iii)Synth –top  dff_async_set

>iv)Dfflibmap –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>v)Abc –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>vi)Show

**3. Read syncrhronous set**

>i)Read_liberty –lib ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>ii)read_Verilog dff_sync_set

>iii)Synth –top  dff_sync_set

>iv)Dfflibmap –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>v)Abc –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>vi)Show

![image](https://user-images.githubusercontent.com/118953939/206335570-38eb0ba3-54f9-4e84-ba91-f9fb1b91e9a2.png)

>*The inverter needed because the active high reset.*
![image](https://user-images.githubusercontent.com/118953939/206144049-2d08e800-adb0-473d-9cdc-4e7115992ada.png)
>*Because the library have active low set so the inverter was needed.*
![image](https://user-images.githubusercontent.com/118953939/206144093-4bf33a89-efd4-4b1a-8ff4-e7f8f7ffe064.png)
![image](https://user-images.githubusercontent.com/118953939/206144141-2d0acb83-af53-485e-854e-ddb84c7ddbc7.png)
 </details>
 
 <details>
 <summary>Interesting Optimisations</summary>
 
### Topic-Interesting Optimisations 

>i)yosys

>ii)Read_liberty –lib ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>iii)read_Verilog  mult_2.v  -->if want to see other mux change to mult8

>iv)Synth –top mul2 -->if want to see other mux change to mult8

>v)Dfflibmap –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>vi)Abc –liberty ../my_lib/lib/sky130_fd_sc_hd__tt025C_1v80.lib

>vii)Show

>viii)write_verilog mul2_simp.v -->if want to see other mux change tomult_8_simp.v 

>ix)!vim mul2_simp.v --> if want to see other mux change to mult_8_simp.v 

>*Explanation from lecture video*
![image](https://user-images.githubusercontent.com/118953939/206195075-74bd67f7-9e15-4deb-844a-499f01f3f9ad.png)

* **Mult_2**
![image](https://user-images.githubusercontent.com/118953939/206339930-bc5f93d8-070f-4e18-b433-a34f0acd8a7a.png)

* **Mult_8**

![image](https://user-images.githubusercontent.com/118953939/206340719-32f94a4f-7cae-4b51-a9ca-c2dea6b7ab2a.png)

 </details>
 
## Day3

### Topic-Combinational and sequential Optimizations

<details>
 <summary>Lab Introdcution to Opitmizations</summary>
 
### Topic - Introduction to optimizations 

* **Combinational logic Optimisation**  
* To Squeezing the logic to get the most optimised design.Optimize in area and power savings.
* There are Two type of technique 
  
  * **Constant Propagation** = Direct Optimisation 
  * **Boelean Logic Optimisation** = Kmap & Quaine McKluskey 
  * **Kmap** = K-map can take two forms Sum of Product (SOP) and Product of Sum (POS) according to the need of problem. K-map is table like representation but it gives                  more information than TRUTH TABLE. 
  
 ![image](https://user-images.githubusercontent.com/118953939/206657513-c8093880-d8bb-4a8a-88f4-458b2f891aee.png)
  
 * **Notes from the lecture video**

 ![nota1](https://user-images.githubusercontent.com/118953939/206659875-2f57c570-1e59-4199-b51d-30607b323d78.JPG)
  
 ![nota2](https://user-images.githubusercontent.com/118953939/206659884-945fb74a-9344-4323-b65c-01d1d316bda6.JPG)
</details>

<details>
 <summary>Lab Combinational Logic Optimizations</summary>
 
## Topic - Lab Combinational Logic Optimizations 
* **Invoke yosys**
>yosys

>read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd_tt__-25C_1v80.lib

>read_verilog opt_check --------> can change toif want  opt_check3,opt_check4,opt_check5

>synth -top opt_check

>opt -clean_purge

>abc -liberty ../my_lib/lib/sky130_fd_sc_hd_tt__-25C_1v80.lib

>show

**(1).Opt_check1**

*2 input AND Gate*
>![Slide1](https://user-images.githubusercontent.com/118953939/206728179-97377bd2-8fb9-4fa4-a0b3-837465825c8f.PNG)

**(2).Opt_check2**

*2 input OR gate*
>![Slide2](https://user-images.githubusercontent.com/118953939/206728251-6cbcde34-008f-4bce-bab4-ba1bcd4f7119.PNG)


**(3).Opt_check3**

*3 Input AND gate*
>![Slide3](https://user-images.githubusercontent.com/118953939/206728273-07e8b3d8-b9ed-49ee-9e66-b96829c91aff.PNG)


**(4).Opt_check4**

*2 Input XNOR gate*
>![Slide4](https://user-images.githubusercontent.com/118953939/206728317-a88e7e0d-7974-482d-8754-b8f81bff769f.PNG)

**Invoke yosys**
>yosys

>read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib

>read_verilog multiple_module_opt.v   ----> if want sys opt2 change command to multiple_module_opt2 

>synth -top multiple_module_opt    ----> if want sys opt2 change command to multiple_module_opt2 

>flatten

>opt_clean -purge

>abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib

>show


**(5).Multiple_module_opt**
>![Slide5](https://user-images.githubusercontent.com/118953939/206729044-df195939-409c-40ae-b264-3180d5116928.PNG)


**(6).Multiple_module_opt2**

*sub_module1= AND gate*
!![Slide6](https://user-images.githubusercontent.com/118953939/206729075-31462252-f244-473d-9885-cbb48bab6253.PNG)
</details>

<details>
 <summary>Sequential Logic Optimizations</summary>

## Topic-Sequential logic Optimizations 
**(1).dff_const1**

*If reset was high the output  q will below and it turn back to high on next positive clock edge  if reset was high .*
>![Slide7](https://user-images.githubusercontent.com/118953939/206729234-d49990f2-32a9-476f-8d2f-439214319015.PNG)
>![Slide8](https://user-images.githubusercontent.com/118953939/206729280-c4bbe0ae-abc6-45c3-b107-969a1f9576f8.PNG)


**(2).dff_const2**

*If reset  was high the q will high  and even the reset was low the q will not change.In conlusion, q was not make anychanges even the reset high or low.*
>![Slide9](https://user-images.githubusercontent.com/118953939/206729417-86f0dc3d-6af1-4d7b-a81b-9be18a894f2c.PNG)

>![Slide10](https://user-images.githubusercontent.com/118953939/206729469-80e01574-c7ba-4c4d-ac0d-768117be7f07.PNG)

**(3).dff_const3**

*There are 2 flip flop and the output q1 will be low iff the reset high and it will change high if the reset low.But for q it will be always high except for 1 clock cycle.More detail on the diagram below.*

>![Slide11](https://user-images.githubusercontent.com/118953939/206729530-aff0840b-aab7-4fc8-8368-8843e7a74adb.PNG)

>![Slide12](https://user-images.githubusercontent.com/118953939/206729562-c67081de-02eb-4510-ad16-0fe9f52480be.PNG)

**(4).dff_const4**

*Q and q1 always 1.No change.*
>![Slide13](https://user-images.githubusercontent.com/118953939/206729622-dfeddbf9-36a9-4d91-b7cf-7c9cb37b52b8.PNG)

>![Slide14](https://user-images.githubusercontent.com/118953939/206729673-cfdd1f3b-109d-42cf-89b1-fdfb4dff893b.PNG)

**(5).dff_const5**
>![Slide15](https://user-images.githubusercontent.com/118953939/206729699-b0b5c740-5bb1-4b2b-ab5b-d4fd5144ec91.PNG)
>![Slide16](https://user-images.githubusercontent.com/118953939/206729837-d8b2e865-bd29-4ec6-bbd7-b3095b9eaac1.PNG)


## Topic-Unused Output Optimization
**(1).counter_opt**

*The count[0] used the 1 bit and others bit are unused.From netlist diagram we can show the only one flop was available because only count[o] was used.The others unused flop was not showed.*
>![Slide17](https://user-images.githubusercontent.com/118953939/206729992-a194188f-5661-4840-b2e0-f62d1ef1a2e1.PNG)

>![Slide18](https://user-images.githubusercontent.com/118953939/206730011-5c69efd6-9869-47b3-b7f2-750f384b2daf.PNG)

**(2).counter_opt2**

*In this case the q was assign  count[2:0] .So from the diagram below,we can see that the netlist are shows the 3 avalaible flop because all of them are used.We have a large amount of logic within the design since all the bit was used.*
*Modified count[0] --->count [2:0]
>![Slide19](https://user-images.githubusercontent.com/118953939/206730040-3469b5c5-5b75-4fba-91e4-8e6a4e823f9b.PNG)

>![Slide22](https://user-images.githubusercontent.com/118953939/206691179-ebe9a1c3-103d-40e1-8f31-3b99133080db.PNG)

>![Slide21](https://user-images.githubusercontent.com/118953939/206730086-bae6966a-afc3-492d-963f-9fe875128ca4.PNG)

 </details>
  
## Day4

### Topic - GLS,Blocking vs non-blocking and Synthesis-Simulation mismatch  

<details>
 <summary>Introduction to GLS,Synthesis-Simulation mismatch and Blocking/Non-blocking statements</summary>

 
📖 Topic-Introduction to GLS,Synthesis-Simulation mismatch and Blocking/Non-blocking statements
 
 * **Notes from the lecture video**
 
 >**GLS Concept and Flow Using Iverilog** 
 
 >![image](https://user-images.githubusercontent.com/118953939/206908941-02ec9771-9b5c-46f4-8aa7-0a603948be96.png)
 >![image](https://user-images.githubusercontent.com/118953939/206908999-9534160f-4d50-472f-ad61-f620aba802f3.png)
 
 
 >**Synthesis Simulation Mismatch**
 
 >![image](https://user-images.githubusercontent.com/118953939/206909064-cad81aeb-e2ff-49c8-b293-76377cd37803.png)
 
 >**Blocking/Non Blocking and Caveats** 

 >![image](https://user-images.githubusercontent.com/118953939/206909429-07cfa9f2-c9a2-4c93-b91b-ca8b7841c772.png)
 >![image](https://user-images.githubusercontent.com/118953939/206909451-7a608dbe-9d00-415a-9fbd-0466d0436031.png)
</details>

<details>
 <summary>Lab On GLS Synthesis_simulation Mismatch</summary>
 
📖 Topic - Lab On GLS Synthesis_simulation Mismatch 
 
 **Step**
>>iverilog ternary_operator_mux.v tb_ternary_operator_mux.v

>>./a.out

>>gtkwave_tb_ternary_operator_mux.vcd
 
>**(1).Ternary_operator_mux**

>![image](https://user-images.githubusercontent.com/118953939/206979815-dcd38240-a46e-4b06-9776-2b90a58795c4.png)

**Step Synthesis**
>>yosys

>>read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80

>>read_verilog ternary_operator_mux.v

>>synth -top ternary_operator_mux.v

>>abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80

>>write_verilog -noattr ternary_operator_mux.net.v

>>show

>![image](https://user-images.githubusercontent.com/118953939/206983673-a2bf9733-024d-4705-b581-1756c3cc7b3a.png)

 
**GLS output**
**Step**

>>iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_mux_net.v tb_ternary_operator_mux.v

>>./a.out

>>gtkwave tb_ternary_operator_mux.vcd

>![image](https://user-images.githubusercontent.com/118953939/206909853-63cc18c0-8e52-4995-9a0a-f74e7c6770ee.png)

>**(2).Bad_mux**

>![image](https://user-images.githubusercontent.com/118953939/206980742-9d626d6c-6f78-47a9-a328-e51ebb205b71.png)
 
 **Synthesis**
>![image](https://user-images.githubusercontent.com/118953939/206909917-63654fb3-70a8-4d0b-9fed-551f5101ee9a.png)

**GLS output**
>![image](https://user-images.githubusercontent.com/118953939/206909948-d642c1ba-bb91-4e6e-99c7-16dda7c45701.png)
 
>**(3).Good_mux**
 
>![image](https://user-images.githubusercontent.com/118953939/207000028-a4cd727b-7e3d-4449-b6cc-58753cf1eb2d.png)
 
**Synthesis & GLS output**
>![image](https://user-images.githubusercontent.com/118953939/207000117-caf23d4b-298d-40dd-bc50-d8c9f3bf7dd7.png)


</details>

<details>
 <summary>Lab on Synth-Sim mismatch for blocking statement</summary>
 
📖Topic-Labs on Synth-sim mismatch for blocking statement

**Step**
 >>iverilog blocking_caveat.v tb_blocking_caveat.v
 >>./a.out
 >>gtkwave tb_blocking_caveat.vcd
 
>![image](https://user-images.githubusercontent.com/118953939/206910002-3fbf310a-d377-49bd-aeb8-70d098256f7f.png)
 
**Step Synthesis**
>>yosys
>>read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80

>>read_verilog blocking_caveat.v

>>synth -top blocking_caveat

>>abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80

>>write_verilog -noattr blocking_caveat_net.v

>>show
 
>![image](https://user-images.githubusercontent.com/118953939/206910018-3400ae9a-d2f6-4102-9b9c-2bd84619a0c8.png)

**GLS Output**
>![image](https://user-images.githubusercontent.com/118953939/206910031-2e0b3072-3771-4f01-b09f-8398b8129124.png)
 </details>

## Day5
### Topic - Design of Testability.  

<details>
 <summary>Introduction of DFT</summary>
 
 >![CamScanner 12-15-2022 12 46 (2)-01](https://user-images.githubusercontent.com/118953939/207797227-0310528f-5e06-45ce-b8c4-5ecab603a7a8.png)
 
 </details>
 
 <details>
   <summary>Pro's & Con's and Basic Terminologies</summary>
 
 >![CamScanner 12-15-2022 12 46 (2)-02](https://user-images.githubusercontent.com/118953939/207797254-9dd0f0fe-60c2-4c82-ae30-a39f50d80ab9.png)
 
 >![CamScanner 12-15-2022 12 46 (2)-03](https://user-images.githubusercontent.com/118953939/207797561-c11d6905-acd3-41a0-8eda-cb532b06977f.png)
 
 </details>
  
 <details>
 <summary>DFT Techniques</summary> 
 
 >![CamScanner 12-15-2022 12 46 (2)-04](https://user-images.githubusercontent.com/118953939/207798024-38a93344-1ab9-46fb-9e3a-2b37bec722f2.png)
 
 </details>
 
 <details>
 <summary>Typical Scan Chain</summary>
 
 >![CamScanner 12-15-2022 12 46 (2)-05](https://user-images.githubusercontent.com/118953939/207798236-9d87ff3a-fce7-4dda-9276-9b5e829f11b1.png)
 
 >![CamScanner 12-15-2022 12 46 (2)-06](https://user-images.githubusercontent.com/118953939/207798274-34b3c386-047d-4768-a9c2-cb57fc417c56.png)
 </details>
 
 <details> 
 <summary>Calculation</summary>
 
 >![CamScanner 12-15-2022 12 46 (2)-07](https://user-images.githubusercontent.com/118953939/207799274-f5eec5eb-54e4-4706-8a22-09ac57e588da.png)
  </details>
 
 <details>
 <summary>How DFT can be game Changer for VLSI engineer</summary>
 
 >![CamScanner 12-15-2022 12 46 (2)-08](https://user-images.githubusercontent.com/118953939/207799437-61a56ec0-f539-4ab4-9917-878b26aa56c7.png)
 
 </details>
 
 <details>
 <summary>Automatic Test Equipment (ATE) Flow</summary>
 
 >![CamScanner 12-15-2022 12 46 (2)-09](https://user-images.githubusercontent.com/118953939/207799536-288b96da-63bf-47c4-85e4-8009c769a67b.png)
 
 </details>
 
 <details>
 <summary>Overview</summary>

 >![CamScanner 12-15-2022 12 46 (2)-10](https://user-images.githubusercontent.com/118953939/207799787-76c5f5f7-14e6-4762-b05a-2f800be9d9c7.png)

 </details>
 
 ## Day 6 
 ### Topic-Introduction to Synthesis 

<details>
<summary>Introduction to the Course</summary>

>![day6 (1)-1](https://user-images.githubusercontent.com/118953939/208287161-7aae30dd-58ae-4e6b-8086-c30fc121c2a1.png)
 
>![day6 (1)-2](https://user-images.githubusercontent.com/118953939/208287180-5875b396-32d9-48f4-b62e-3616c45193ab.png)
 
>![day6 (1)-3](https://user-images.githubusercontent.com/118953939/208287184-8c35d86e-878f-4306-a3a6-b345057318f8.png)
 
>![day6 (1)-4](https://user-images.githubusercontent.com/118953939/208287233-ddb2748c-ccbd-40cd-b41b-3da84ec8763c.png)
</details>

<details>
<summary>Introduction to DC</summary>

>![CamScanner 12-19-2022 09 59-2](https://user-images.githubusercontent.com/118953939/208333861-9104e2b7-ff7d-420c-9fda-7aa587bd8075.png)

>![CamScanner 12-19-2022 09 59-1](https://user-images.githubusercontent.com/118953939/208333805-5b731138-6ca0-471c-83e0-83bfdf2320a7.png)

</details>

<details>
<summary>Introduction to Tcl</summary> 

>![day6 (1)-5](https://user-images.githubusercontent.com/118953939/208287236-dfd3392e-aa66-4e79-b2e8-f825ad916f0f.png)

>![day6 (1)-6](https://user-images.githubusercontent.com/118953939/208287240-3344d529-e387-40fe-a0b5-323de260d3fd.png)

</details>

<details>
<summary>Invoking to DC setup</summary>

>**Lib Information**
![image](https://user-images.githubusercontent.com/118953939/208297262-23eea680-5352-4ae8-be0b-8639446c60eb.png)
 
>**Invoke DC**
>>i)git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
>>ii)/p/hdk/pu_tu/prd/sams/mig76_wlw/setup/enter_p31 -cfg ip76p31r08hp7rev03 -ov ./
>>iii)dc_shell


>![image](https://user-images.githubusercontent.com/118953939/208297486-e6a21602-eb4c-41d4-8d20-81597232cb0f.png)

>![image](https://user-images.githubusercontent.com/118953939/208297503-485d9f3d-aa01-4e56-9b13-66bac6cd3b37.png)

>![image](https://user-images.githubusercontent.com/118953939/208297519-0c4fbcff-20c2-46aa-98fa-f0a04c31fc21.png)

>![image](https://user-images.githubusercontent.com/118953939/208350177-8aac85ba-97e3-400b-838a-43c64af2ab64.png)


>>Set target_library

>>set library_link 

>>compile 

>>write -f verilog -out lab1_net

>![image](https://user-images.githubusercontent.com/118953939/208297568-6af2d520-f180-4238-a11d-4cf96d117466.png)
 </details>
 
 <details>
 <summary>ddc gui with Design Vision</summary>

>![image](https://user-images.githubusercontent.com/118953939/208297610-9d9f253b-acf8-4d40-9219-d672eee3442e.png)

>![image](https://user-images.githubusercontent.com/118953939/208297623-0055df3d-0b29-41cf-b256-bf442b9286e2.png)>

</details>

<details>
<summary>DC Synopsys DC Setup</summary>

>![image](https://user-images.githubusercontent.com/118953939/208297943-3f415606-6964-4493-a8f4-b49038c98ea3.png)

>![image](https://user-images.githubusercontent.com/118953939/208297954-05912442-d792-428b-89c6-295b1f3d0b28.png)

</details>
 

<details>
<summary>TCL</summary>

>![image](https://user-images.githubusercontent.com/118953939/208298013-8f647f7d-e75f-45cd-a1bc-89b1b4c111f5.png)
 
>![image](https://user-images.githubusercontent.com/118953939/208298028-f2695a51-5f46-4ae8-b81c-0c6dee465c25.png)

>![image](https://user-images.githubusercontent.com/118953939/208298035-5b2ee4c5-ff02-4afb-bee8-3e42e54de6e1.png)

>![image](https://user-images.githubusercontent.com/118953939/208298043-b48e7f06-f1f8-42e4-a0dd-3d452e91f13a.png)

>![image](https://user-images.githubusercontent.com/118953939/208298066-795d7881-db1b-433a-910d-843790ebb7df.png)
 
>![image](https://user-images.githubusercontent.com/118953939/208298087-3e693a2b-36c6-4357-b4cc-6f7974bc9795.png)

</details>
 
## Day 7 
### Topic-Basic of Static Timing Analysis (STA)

<details>
<summary>Introduction to STA </summary>
 
>![CamScanner 12-21-2022 14 11-1](https://user-images.githubusercontent.com/118953939/208837684-04d6afc8-8502-4ca2-9693-4bd95034212c.png)
>![CamScanner 12-21-2022 14 11-2](https://user-images.githubusercontent.com/118953939/208837689-3db2067f-8aaf-4d0d-8bf0-0f813f8ea2a4.png)
>![image](https://user-images.githubusercontent.com/118953939/208845407-d8c9e8ce-f1e0-4e08-b889-1e8a39ef5090.png)
>![image](https://user-images.githubusercontent.com/118953939/208845474-ee2c9e8e-0006-4e4d-a631-c55f84bd32dc.png)
>![CamScanner 12-21-2022 14 11-3](https://user-images.githubusercontent.com/118953939/208837695-313b7601-ff92-4fed-aeda-e129c290dd05.png)
>![CamScanner 12-21-2022 14 11-4](https://user-images.githubusercontent.com/118953939/208837699-2d9fe5ab-0cca-4ecb-a880-e878f507e678.png)
>![CamScanner 12-21-2022 14 11-5](https://user-images.githubusercontent.com/118953939/208837703-3b4f9c55-2983-4ae4-92dc-50f10b9ee631.png)
>![CamScanner 12-21-2022 14 11-6](https://user-images.githubusercontent.com/118953939/208837708-5a97bf00-ea65-4a7a-b563-0643add0f5d8.png)
</details>

<details>
<summary>Timing dot lib</summary>
 
>![image](https://user-images.githubusercontent.com/118953939/208848579-0ec71077-f3d7-4d13-bef5-5b5505769ba0.png)
>![image](https://user-images.githubusercontent.com/118953939/208848653-177b43e3-c65f-4dbe-9017-bd324bfaa994.png)
>![image](https://user-images.githubusercontent.com/118953939/208848878-dfb8fa27-01b5-4309-8a41-393c4567d04c.png)>
>![image](https://user-images.githubusercontent.com/118953939/208849021-8065243e-72b0-4c3a-8a76-bf29c86d3041.png)
>![image](https://user-images.githubusercontent.com/118953939/208859296-3a6d6f86-eddd-427a-bee2-2c4e44c4c556.png)
>![image](https://user-images.githubusercontent.com/118953939/208850668-4acc35e2-b276-4bbe-8f5d-385a1f2e2b5c.png)
>![image](https://user-images.githubusercontent.com/118953939/208850721-360a8c66-751e-4b6c-84ee-c3499bbe1650.png)
 </details>

 <details>
<summary>Exploring dot libs</summary>
  
 >![image](https://user-images.githubusercontent.com/118953939/208850960-a324e847-8921-4b4a-ba9d-8d4521ab719c.png)
 >![image](https://user-images.githubusercontent.com/118953939/208850998-759fa0d6-0920-47a1-b5b6-94c22c1392da.png)
 >![image](https://user-images.githubusercontent.com/118953939/208851029-34414c8e-9bb4-4d42-aab4-8af1f6c94e91.png)
 
 >>foreach_in_collection my_lib_cell [get_lib_cells */*] {
 >>  set my_lib_cell_name [get_object_name $my_lib_cell];
 >>    echo $my_lib_cell_name;
 
 >![image](https://user-images.githubusercontent.com/118953939/208852402-f9502867-bcfe-4e4d-9f5e-0620878d8ad1.png)

 >>get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0
 
 >>foreach_in_collection my_pins [get_lib_pins  sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/*] {
 >>    set my_pin_name[get_object_naem $my_pins];
 >>    set pin_dir [get_lib_attribute $my_pins_name direction];
 >>    echo $my_pin_naem $pin_dir: }
 
 >>get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/X function
 
 >![image](https://user-images.githubusercontent.com/118953939/208854873-297586f2-e0e4-4e0f-9fe8-adc2ecbe969e.png)

  
 >>get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2b_1/X function
 
 >![image](https://user-images.githubusercontent.com/118953939/208854957-08599a49-616b-4089-82d6-c740a5bda282.png)


 >> **Sourcing from myscript.tcl**
 >![image](https://user-images.githubusercontent.com/118953939/208855052-87fd6cb7-bca2-4498-8bce-ea27e6b510e1.png)
 >![image](https://user-images.githubusercontent.com/118953939/208855113-0ea3332b-f9c6-471a-a0f7-5fff54c045a4.png)

>> **Other ways**

>>list_lib
>> get_lib_cells */* -filter "is_sequential == True "

>>get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dfbnn_2/*

>>get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dfbnn_2/CLK_N capacitance

>>get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dfbnn_2/D capacitance  

>![image](https://user-images.githubusercontent.com/118953939/208861690-9a7565c5-9dcf-4ac9-a33c-7b8b5f10898c.png)
>![image](https://user-images.githubusercontent.com/118953939/208855303-dccd6eea-9618-4638-b9a6-82127f86cba5.png)

>>list_attributes -app > a
>> sh gvim a  
*Can see all the attributes such as area on lib_cell and cell,capacitance on the port and pin,fucntion also shows the on the cell and port.*
 
>>![image](https://user-images.githubusercontent.com/118953939/208856456-967d75f7-c334-44ab-b9f6-4787ff5f08fd.png)
 </details>

  ## Day 8
  ### Topic 8 -Advance Constraints

<details>
<summary>Clock-Clock Tree Modelling-Uncertainty (Theory)</summary>
  

 >![image](https://user-images.githubusercontent.com/118953939/209515539-b3534155-4683-4e05-a7f8-cb21e67022c4.png)

 >![image](https://user-images.githubusercontent.com/118953939/209515571-1014b790-a8af-432a-a3f1-bcfc30c18401.png)

 >![image](https://user-images.githubusercontent.com/118953939/209515597-cf5b0026-6397-4c0e-8fd7-f10552e8d974.png)

 >![image](https://user-images.githubusercontent.com/118953939/209515610-bcefac0d-3cd8-47c4-b2bd-81fab60ea2af.png)

 >![image](https://user-images.githubusercontent.com/118953939/209515678-21afa0c3-3960-4f51-b6b2-ab96f786b131.png)


 
- Clock modelling
```
 
* Period
-Source latency: time taken by the clock source to generate clock
-Clock Network Latency: time taken by clock distribution network
-Clock skew: clock path delay mismatches which causes difference in the arrival of the clock
  > CTS will balance the clocks, but still the skew cannot be reduced to 0
-Jitter: stochastic variations in the arrival of clock edge
  > Duty cycle jitter
  > Period jitter 
-Collectively clock skew and jitter are called Clock Uncertainty
 ```
 >![image](https://user-images.githubusercontent.com/118953939/209515789-2c1aab93-08a3-489e-ba50-6f21f90915fc.png)
 </details>

<details>
<summary>SDC Part 2 -IO delay (Theory)</summary>
  
![image](https://user-images.githubusercontent.com/118953939/209516086-b5b5e02a-a4c7-46cb-ab0b-9b9da4b5f7f0.png)



-	Command Getting the Ports in DC
```
get_ports clk ;	= command query the ports call clk  in the design  (.port,pin,clock etc all name  are case-sensitive).
get_ports *clk*;	= A collection of ports whose name contains clk
get_ports*; 	= all of ports of design 
Get_ports *-filter ‘direction == in”; 	= all input ports
Get_ports *-filter ‘direction ;==out” 	= all output ports
```

- Command Getting the clocks in DC
```
get_clocks * = all the clocks in the design 
get_clocks *clk* = all clocks which has the name clk in it.
get_glock *filter “period >10” = filter the clk that greater than 10ns
get_attribute [get_clocks my_clk ] period = attributed the clock period
get_attribute [get_clocks my_clk ]is_generated 
Report_clocks my_clock 
```
>![image](https://user-images.githubusercontent.com/118953939/209516362-611f5f71-c48b-4f30-bc4d-81128e4559c7.png)

>![image](https://user-images.githubusercontent.com/118953939/209517574-6d08e031-467e-43dc-abaf-946922abfcda.png)

>![image](https://user-images.githubusercontent.com/118953939/209517625-291ad8b6-3173-4ae8-a3c0-196290f011e4.png)

>![image](https://user-images.githubusercontent.com/118953939/209517694-c698ac0a-c409-42fb-8529-00e800072982.png)

>![image](https://user-images.githubusercontent.com/118953939/209517784-a0f84995-ff37-4f9c-a743-4f290175923c.png)>

>![image](https://user-images.githubusercontent.com/118953939/209517856-6ba95a06-70e3-4ccf-9398-3d4dbe229dab.png)

- Summary
```
1.Create_clock 
2.Set_clock_latency
3.Set_clock_uncertainty  skew + jitter pre cts and only jitter on post cts 
4.Set_input_delay 
5.Set_input_trainsition 
6.Set_output_delay
7.Set_load
8.Get_ports,get_clocks,get_cells,etc
```
</details>
 
<details>
<summary>Lab 8 -Loading Design get_cells,get_ports,get_nets (LAB)</summary>
 

>![image](https://user-images.githubusercontent.com/118953939/209518209-48b94cfb-723c-4414-b6a9-cb00586faae9.png)

- Command
```
-csh                                                        
-dc_shell                                
-echo $target_library 
-echo $link_library 
-read_verilog DC_WORKSHOP/verilog_files/lab8_circuit.v 
-link
-compile_ultra
```
- Listing the collection of port name and its direction
```
foreach_in_collection my_port [get_ports *] {                   
set my_port_name [get_object_name $my_port];
set dir [get_attribute [get_ports $my_port_name] direction];     
echo $my_port_name $dir;
}
Get Cells 
get_attribute [get_cells U9] is_hierarchical                        (Checking the desired cell is hierarchical/not)
get_cells * -hier -filter "is_hierarchical == false"                (Listing the false hierarchical cell)
get_cells * -hier -filter "is_hierarchical == true"                 (Listing the true hierarchical cell)
```
>![image](https://user-images.githubusercontent.com/118953939/209518233-2b144e05-5632-464a-915c-f183cd78926e.png)

- Get reference Name 
```
foreach_in_collection my_cell [get_cells * -hier] {                 (Listing cell name and its reference name)
set my_cell_name [get_object_name $my_cell];
set rname [get_attribute [get_cells $my_cell_name] ref_name];
echo $my_cell_name $rname;
} 
```
- Write DDC
 ```
write -f ddc -out lab8_circuit.ddc
csh
design_vision
read_ddc DC_WORKSHOP/verilog_files/lab8_circuit.ddc
get_nets *
all_connected N1
all_connected n5
```

>![image](https://user-images.githubusercontent.com/118953939/209518318-be26f497-b3fd-48ad-b9d8-709721306463.png)

 - Driving 
 ```
 foreach_in_collection my_pin [all_connected n5] {                   (Listing the driver of the net)
set pin_name [get_object_name $my_pin];
set dir [get_attribute [get_pins $pin_name] direction];
echo $pin_name $dir;
}
```
>![image](https://user-images.githubusercontent.com/118953939/209518373-6c407beb-231f-48ca-9253-e3d98e1413b3.png)
</details>
 
 
<details>
<summary>Get Clocks and Querying Clocks (LAB)</summary>

- Get All the Pin Name 
 
foreach_in_collection my_pin [get_pins *] {                            (Listing out the pins)
set pin_name [get_object_name $my_pin];
echo $pin_name;
}

```
- Get the pin name and Direction 
 
foreach_in_collection my_pin [get_pins *] {
set pin_name [get_object_name $my_pin];
set dir [get_attribute [get_pins $pin_name] direction];
echo $pin_name $dir;
}
 ```
>![image](https://user-images.githubusercontent.com/118953939/209520858-7ad91127-0168-42f8-8bb9-3579fa5b32a3.png)
 </details>
 
 <details>
 <summary>Create Clock waveform </summary>

 - Create Clock waveform 
 ```
 -create_clock -name MYCLK -per 1-[get_ports clk]
 -get_clock *
 -report_clocks *
  ```
 - Put in Gvim 
  ```
-foreach_in_collection my_pin [get_pins *] {                              (Listing input pin name with clock - The pin is meant to be a clock pin/not)
	       set my_pin_name [get_object_name $my_pin];
        set dir [get_attribute [get_pins $my_pin_name] direction];                                                                                              
	       if { [regexp $dir in] } {
	      	if { [get_attribute [get_pins $my_pin_name] clock] } {
		       echo $my_pin_name $clk_name;
	     	          }
	         }
        } 
 -source query_clock_pin.tcl
 ```
 
 > ![image](https://user-images.githubusercontent.com/118953939/209520956-f94a9361-36d7-43f0-b81a-6e4e5a76f685.png)
 
 - Create Clock and what happen if we change arrangement 
 ```
 -create_clock -name MYCLK -per 1-[get_ports clk] -waive (5 10)
 -report_clocks *
 -create_clock -name MYCLK -waive (15 20) [get_ports clk] -per 10
 
 ```
 
 >![image](https://user-images.githubusercontent.com/118953939/209522657-081b2117-db8d-4813-a850-a2eb5cb5793c.png)

 </details>
 
<details>
<summary>Uncertainty Report Timing  (LAB)</summary>

 - Modelling the clock Tree Attribute
  ```
 -create_clock -name MYCLK -per 1-[get_ports clk]
 -report_timing
 -set_clock_latency 1 [get_clocks MYCLK]
 -report_clocks *
 -set_clock_latency 1 [get_clocks MYCLK]						(Modelling the network latency)
 -set_clock_uncertainty 0.5 [get_clocks MYCLK]					(Max delay for setup time by default)
 -set_clock_uncertainty -hold 0.1 [get_clocks MYCLK]				(Min delay for hold time) 
  ```
>![image](https://user-images.githubusercontent.com/118953939/209523205-69448219-d46a-4ac6-a9b0-3355679a9afb.png)

>![image](https://user-images.githubusercontent.com/118953939/209524767-0982ed02-69c5-48c7-afff-6b218d707453.png)

- Report delay 
 ```
-report_timing -to REGC_reg/D -delay min
 ```
 ![image](https://user-images.githubusercontent.com/118953939/209525984-7f59c1db-1e7e-47a6-8367-63875cec8aca.png)
 
 - Report all ports
 ```
 - set_input_delay -max -clock [get_clocks MYCLK] [get_ports IN A]
 - set_input_delay -max -clock [get_clocks MYCLK] [get_ports IN B]
 -report_port -verbose 
 ```
 >![image](https://user-images.githubusercontent.com/118953939/209526016-8a52f8e7-18ea-443e-ae20-c6890197a47e.png)
 
 </details>
 
 <details>
  <summary>IO Delays (LAB)</summary>
  
 * External delay and Capacitance  
 >![image](https://user-images.githubusercontent.com/118953939/209526883-3d770902-2491-4288-a22f-54745e0052e7.png)

  - Setting Input Transition 
 ```
-set_input_transition -max 0.3 [get_ports IN_A]
-set_input_transition -max 0.3 [get_ports IN_B]
-set_input_transition -min 0.1 [get_ports IN_B]
-set_input_transition -min 0.1 [get_ports IN_A]
-report_timing -from IN_A -trans  -cap -delay_type max
 ```
>![image](https://user-images.githubusercontent.com/118953939/209527270-7de2f4a6-db77-4a80-ad0d-8050d177613e.png)

 - Setting Output Delay 
 ```
-set_output_delay  -max 5 -clock [get_ports MYCLK] [get_ports OUT_Y]
-set_output_delay  -min 1  -clock [get_clocks MYCLK] [get_ports OUT_Y]
-report_timing -to OUT_Y -cap -trans
 ```
 >![image](https://user-images.githubusercontent.com/118953939/209527833-1ab9c5df-b89d-41a0-ba2c-80c88c0f9ca7.png)
  
- Setting for load
 ```
-set_load -max 0.4 [get_ports OUT_Y]
-report_timing -to OUT_Y -cap -trans -nosplit > out_load
-set_load -min 0.1 [get_ports OUT_Y]- report_timing -to OUT_Y -cap -trans -nosplit -delay min  > out_load
 ``` 
![image](https://user-images.githubusercontent.com/118953939/209527901-f3d31d03-9a0a-4d4a-9c2b-fd1f415e4385.png)
 </details>

<details>
<summary>SDC Generated_clk(Theory)</summary>

> ![image](https://user-images.githubusercontent.com/118953939/209528784-2fee7d66-c0d6-4b92-96f2-d9f257478741.png)

>![image](https://user-images.githubusercontent.com/118953939/209528828-c9883989-e877-48df-ba04-1b0250d35871.png)
</details>
	
<details>
<summary>SDC Generated_clk(LAB)</summary>

- Generated Clock 
```
-create_generated_clock -name MYGEN_CLK -master MYCLK -source [get_ports clk ] -div 1 [get_ports out_clk]
-report_clocks *
 ```
>![image](https://user-images.githubusercontent.com/118953939/209529041-e498fd37-968c-4ccd-9792-ea2d639e735d.png)

- Generated Clock 
```
-set_clock_latency -max 1 [get_clocks MYGEN_Clk]
-set_output_delay -max 5 [get_ports OUT_Y ] -clock [get_clocks MYGEN_CLK]
-report_timing -to OUT_Y
```
>![image](https://user-images.githubusercontent.com/118953939/209529066-763e5a18-fcb9-44e4-b6d4-6695cfd83cad.png)

- Reset Design and Put in GVIM  
```
-reset_design
-sh gvim lab8_cons.tcl 
-create_clock -name MYCLK -per 10 [get_ports clk];
	set_clock_latency -source 2 [get_clocks MYCLK];
	set_clock_latency 1 [get_clocks MYCLK];
	set_clock_uncertainty -setup 0.5 [get_clocks MYCLK];
	set_clock_uncertainty -hold 0.1 [get_clocks MYCLK];
	set_input_delay -max 5 -clock [get_clocks MYCLK]  [get_ports IN_A];
	set_input_delay -max 5 -clock [get_clocks MYCLK]  [get_ports IN_B];
	set_input_delay -min 1 -clock [get_clocks MYCLK]  [get_ports IN_A];
	set_input_delay -min 1 -clock [get_clocks MYCLK]  [get_ports IN_B];
	set_input_transition -max 0.4 [get_ports IN_A];
	set_input_transition -max 0.4 [get_ports IN_B];
	set_input_transition -min 0.1 [get_ports IN_A];
	set_input_transition -min 0.1 [get_ports IN_B];
	create_generated_clock -name MYGEN_CLK -master MYCLK  -source [get_ports clk] -div 1 [get_ports out_clk];
	create_generated_clock -name MYGEN_DIV_CLK -master MYCLK  -source [get_ports clk] -div 2 [get_ports out_div_clk];
	set_output_delay -max 5 -clock [get_clocks MYGEN_CLK] [get_ports OUT_Y];
	set_output_delay -min 1  -clock [get_clocks MYGEN_CLK] [get_ports OUT_Y];
	set_load -max 0.4 [get_ports OUT_Y];
	set_load -min 0.1 [get_ports OUT_Y];
-source lab8_cons.tcl 
-report_clock *
-report_port -verbose
```
>![image](https://user-images.githubusercontent.com/118953939/209529888-a1bb0670-773a-43e2-a350-8de5034dce69.png)
>![image](https://user-images.githubusercontent.com/118953939/209530255-28dd0195-c604-4a2e-b0f3-9adad6d2f4be.png)
>![image](https://user-images.githubusercontent.com/118953939/209530333-07ee15f2-f80e-4560-a99a-f463034077e9.png)
</details>

	
<details>
<summary>VCLK,MAX_LATENCY,RISE_FALL IO DELAYS (Theory)</summary>

>![image](https://user-images.githubusercontent.com/118953939/209530521-d87817b5-0c70-4732-b35c-075fe4b28d1f.png)

>![image](https://user-images.githubusercontent.com/118953939/209530575-062b87f0-6480-43df-8085-98e5d6f78266.png)

>![image](https://user-images.githubusercontent.com/118953939/209530685-62054522-c998-4d08-a6ca-6b6dd3bf1d93.png)

>![image](https://user-images.githubusercontent.com/118953939/209530743-c49aca60-042f-4229-8337-47919b89cda7.png)

>![image](https://user-images.githubusercontent.com/118953939/209530795-1b7e70eb-c6b6-4ced-9ade-f925455e517e.png)

>![image](https://user-images.githubusercontent.com/118953939/209530853-4c70d0e9-25db-4c20-a0c6-1105f42b09c0.png)

>![image](https://user-images.githubusercontent.com/118953939/209530904-9ba0de4c-7d51-4dcf-9367-4b325a64fb7a.png)

>![image](https://user-images.githubusercontent.com/118953939/209530936-48b29745-d04b-4eb9-9a66-b478749c0240.png)

>![image](https://user-images.githubusercontent.com/118953939/209531032-37bde9f5-9a9d-4fe3-b718-6c8f2155e82e.png)
	</details>
	
<details>
<summary>Set_max_delay (LAB)</summary>

- Open Lab14_circuit.v   
```
-sh gvim Lab14_circuit.v
 ```
>![image](https://user-images.githubusercontent.com/118953939/209531229-ebc0a315-1f88-450c-945e-5d752231b042.png)

- seting max delay 
```
-report_timing to OUT_Z   (to see if the path is constrained or not)
-set_max_delay 0.1 -from [all_inputs] -to [get_ports OUT_Z]
-report_timing -to OUT_Z  (the path constrained)	
 ```
![image](https://user-images.githubusercontent.com/118953939/209531360-b553a72b-611c-4bca-8229-be67c577d875.png)

- Optimized
```
-report_timing to OUT_Z  -sig 4	
 ```
>![image](https://user-images.githubusercontent.com/118953939/209531752-5a07d9dc-1823-437b-9695-72de333f5805.png)

- Design
```
-start_gui 
-lab8_circuit.ddc
 ```	
![image](https://user-images.githubusercontent.com/118953939/209531969-e98d4317-a080-4dfa-89ba-b9b57b66f63d.png)
	</details>
<details>
<summary>Virtual CLock-VCLK (LAB)</summary>

- Created Virtual Clock 
```
-Created_clock -nmae MYVCLK -per 10 
-report_clocks 
-set_input_delay -max 5 [get_ports IN_C] -clock [get_clocks MYVCLK]
-set_input_delay -max 5 [get_ports IN_D] -clock [get_clocks MYVCLK]
-set_output_delay -max 4.9 [get_ports OUT_Z -clock [get_clocks MYVCLK]
-report_timing
 ```
>![image](https://user-images.githubusercontent.com/118953939/209532415-24e0adcf-e592-47fa-a98f-9109afc4ebd6.png)
>![image](https://user-images.githubusercontent.com/118953939/209532803-8e73393f-a558-45f3-b372-9feca52099e8.png)
	</details>

## Day 9 
### Topic -Optimization 
 
<details>
<summary>Optimizations Combinational Opt</summary>

**What is goal of Optimization ?**
Optimization till cost is met. Over optimization of one will harm other goals.

**Goal for Synthesis ?**
To meet timing, area and power .If we want to meet timing we make cell faster but the power and area will be bad situation. But when area is smaller the power will higher but the timing is still in bad condition.
Timing cost function  IO Delay ,Clock period and max delay.

**Combinational Logic Optimisation** 
-Squeezing the logic to get them most optimised design which is area and power saving.
-Constant propagation --> Direct optimisation 
-Boolean Logic Optimisation 
   >K-Map 
   >Quine McKluskey

>![image](https://user-images.githubusercontent.com/118953939/209912053-29f354f9-a4eb-49c3-91e5-70a3cd73ba5f.png)

>![image](https://user-images.githubusercontent.com/118953939/209912293-a80e16e7-7ba8-4da9-8c3d-eff69af576d2.png)

>![image](https://user-images.githubusercontent.com/118953939/209912375-c3b0fe96-db9c-4ee5-bd86-dc7fcedc17e2.png)

>![image](https://user-images.githubusercontent.com/118953939/209912417-c6e49661-30c4-4d31-b97d-f3ad0ff7583e.png)

>![image](https://user-images.githubusercontent.com/118953939/209912441-594c5faf-b7c4-4aca-94b5-54d8672efeba.png)
</details>

<details>
<summary>Sequential Logic Optimisations</summary>

>![image](https://user-images.githubusercontent.com/118953939/209912578-f1a18bc6-1a53-4677-8bf7-0173c49ac6b8.png)
	
>![image](https://user-images.githubusercontent.com/118953939/209912635-89672f1a-ae31-436d-891d-ea90245c812d.png)

>![image](https://user-images.githubusercontent.com/118953939/209912691-c4c22112-f359-4c5b-8a4b-fdcffca4575b.png)>

>![image](https://user-images.githubusercontent.com/118953939/209912975-bc0ee78b-59be-46f2-bef3-2b442a4db2ca.png)

>![image](https://user-images.githubusercontent.com/118953939/209912992-bce2e5a9-cf34-42fb-b4b0-aca321141beb.png)

```
Controlling sequential optimizations in DC
Compile_seqmap_propagate_constants
     --> for constant optimization 
Compile_delete_unloaded_sequential_cells 
     -->for sequential optimization 
Compile_register_replication (advance technique) 
     --> for cloning register !
```
</details>
	
<details>
<summary>Combinational Optimizations(LAB)</summary>

- Optimization of Opt_Check.v
	
```
IN DESIGN COMPILER
sh gvim DC_WORKSHOP/verilog_files/opt_check*.v -o
read_verilog DC_WORKSHOP/verilog_files/opt_check.v
report_timing
get_cells *
report_timing -to y2
report_timing -to y1
write -f ddc -out opt_check.ddc
```
	
>![image](https://user-images.githubusercontent.com/118953939/209914894-50088c89-327c-451a-9330-b12ab5e012b2.png)
>![image](https://user-images.githubusercontent.com/118953939/209914905-4e968dcc-4024-43e7-a564-274bbf3d82da.png)

- Optimization of opt_check2.v

```
IN DESIGN COMPILER
reset_design
read_ddc DC_WORKSHOP/verilog_files/opt_check2.v 
link
compile
write -f ddc -out opt_check2.ddc
IN DESIGN VISION
reset_design
read_ddc DC_WORKSHOP/verilog_files/opt_check2.ddc
```
	
>![image](https://user-images.githubusercontent.com/118953939/209914938-7bb6e658-c323-4407-bec7-9cfe44c63fed.png)
>![image](https://user-images.githubusercontent.com/118953939/209914954-425a20df-6ab5-4145-8282-0ab58176e3fb.png)


- Optimization of opt_check3.v
	
```
IN DESIGN COMPILER
reset_design
read_ddc DC_WORKSHOP/verilog_files/opt_check3.v 
link
compile
write -f ddc -out opt_check3.ddc
IN DESIGN VISION
reset_design
read_ddc DC_WORKSHOP/verilog_files/opt_check3.ddc
```

>![image](https://user-images.githubusercontent.com/118953939/209914980-f608b398-5cac-4a73-bf0d-28a65633348e.png)
>![image](https://user-images.githubusercontent.com/118953939/209915189-72d350dc-0609-4ced-9a1a-de748d50fa5a.png)


- Optimization of opt_check4.v

```
IN DESIGN COMPILER
reset_design
read_ddc DC_WORKSHOP/verilog_files/opt_check4.v 
link
compile
write -f ddc -out opt_check4.ddc
IN DESIGN VISION
reset_design
read_ddc DC_WORKSHOP/verilog_files/opt_check4.ddc
report_timing -to y
set_max_delay 0.06 -from [all_inputs] -to [get_ports y]
compile_ultra 
report_timing 
size_cell U3  sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__xnor2_4
report_timing
compile_ultra
report_timing

```
	
>![image](https://user-images.githubusercontent.com/118953939/209915246-33d477f4-5aab-4d58-ba82-59934cd9bb9e.png)
>![image](https://user-images.githubusercontent.com/118953939/210177616-519e2287-41ad-42de-bc73-683cb9173114.png)

</details>

<details>
<summary>Resource Sharing optimizations(LAB)</summary

- resource_sharing_mult_check.v balance optimization (no constrain set)

```
read_verilog DC_WORKSHOP/verilog_files/resource_sharing_mult_check.v
link
compile_ultra
report_area
```
>![image](https://user-images.githubusercontent.com/118953939/209917404-df838fbd-7461-4872-8475-971ed40b339f.png)

- resource_sharing_mult_check.v (max delay 2.5ns)
	
```
set_max_delay -from [all_inputs] -to [all_outputs] 2.5
report_timing
compile_ultra
report_timing
report_area
```
>![image](https://user-images.githubusercontent.com/118953939/209917876-4c8eb1f0-c864-418c-a059-c39e1a20825c.png)

- resource_sharing_mult_check.v (max delay 0.1ns)
```
set_max_delay -from [all_inputs] -to [all_outputs] 0.1
report_timing
compile_ultra
report_timing
report_area
```
>![image](https://user-images.githubusercontent.com/118953939/209918285-9ff4c0aa-0893-4463-a51d-63a3a39e6a7e.png)

- resource_sharing_mult_check.v (area 800)
```
set_max_area 800
compile_ultra
report_timing
report_area
```
>![image](https://user-images.githubusercontent.com/118953939/209918409-b395be1a-828e-4083-ad1d-21d074fce1fe.png)
	
```
- Conclusion for all run 
```
>![image](https://user-images.githubusercontent.com/118953939/209918482-d5307969-0987-470f-87eb-111001ebf6d5.png)
 </details>
 
 <details>
<summary>Sequential Optimizations (LAB)</summary
 
 - DFF_CONST1 
	
 ``` 
 -sh gvim DC_WORKSHOP/verilog_files/dff_cons* -o
 
 -foreach_in_collection my_cell [get_cells *] {
   set cell_name [get_object_name $my_cell];
   echo $cell_name; 
   }
	
 -foreach_in_collection my_cell [get_cells *] {
    set cell_name [get_object_name $my_cell];
    set rn [get_attribute [get_cells $cell_name] ref_name];  
    echo $cell_name $rn; 
    }
 -read_verilog DC_WORKSHOP/verilog_files/dff_const1.v
 -link
 -compile
 >Run in Design Vision 
 -read_verilog DC_WORKSHOP/verilog_files/dff_const1.v
 -link
 -compile
 ```
 
 ![image](https://user-images.githubusercontent.com/118953939/210133066-21ac035a-1ab9-42ab-b22c-ee0b0bfaa7fb.png)
 
 - DFF_CONST2
 ``` 
 -sh gvim DC_WORKSHOP/verilog_files/dff_cons* -o
 
 -foreach_in_collection my_cell [get_cells *] {
   set cell_name [get_object_name $my_cell];
   echo $cell_name; 
   }
	
 -foreach_in_collection my_cell [get_cells *] {
    set cell_name [get_object_name $my_cell];
    set rn [get_attribute [get_cells $cell_name] ref_name];  
    echo $cell_name $rn; 
    }
 -read_verilog DC_WORKSHOP/verilog_files/dff_const2.v
 -link
 -compile

 >Run in Design Vision 
 -read_verilog DC_WORKSHOP/verilog_files/dff_const2.v
 -link
 -compile
 ```
>![image](https://user-images.githubusercontent.com/118953939/210133127-19396d57-e22f-4c74-8be4-4e9227575fc7.png)

- DFF_CONST3
 ``` 
 -sh gvim DC_WORKSHOP/verilog_files/dff_cons* -o
 
 -foreach_in_collection my_cell [get_cells *] {
   set cell_name [get_object_name $my_cell];
   echo $cell_name; 
   }
	
 -foreach_in_collection my_cell [get_cells *] {
    set cell_name [get_object_name $my_cell];
    set rn [get_attribute [get_cells $cell_name] ref_name];  
    echo $cell_name $rn; 
    }
 -read_verilog DC_WORKSHOP/verilog_files/dff_const3.v
 -link
 -compile

 >Run in Design Vision 
 -read_verilog DC_WORKSHOP/verilog_files/dff_const3.v
 -link
 -compile
 ```
>![image](https://user-images.githubusercontent.com/118953939/210133132-9ca8a4c0-e989-4286-8dcf-2e16bef09c4d.png)

- DFF_CONST4
 ``` 
 -sh gvim DC_WORKSHOP/verilog_files/dff_cons* -o
 
 -foreach_in_collection my_cell [get_cells *] {
   set cell_name [get_object_name $my_cell];
   echo $cell_name; 
   }
	
 -foreach_in_collection my_cell [get_cells *] {
    set cell_name [get_object_name $my_cell];
    set rn [get_attribute [get_cells $cell_name] ref_name];  
    echo $cell_name $rn; 
    }
 -read_verilog DC_WORKSHOP/verilog_files/dff_const4.v
 -link
 -compile

 >Run in Design Vision 
 -read_verilog DC_WORKSHOP/verilog_files/dff_const4.v
 -link
 -compile
 ```
>![image](https://user-images.githubusercontent.com/118953939/210133150-a7a593ff-2d7f-4b73-8002-c5ba03df13bc.png)

- DFF_CONST5
	 
 ``` 
 -sh gvim DC_WORKSHOP/verilog_files/dff_cons* -o
 
 -foreach_in_collection my_cell [get_cells *] {
   set cell_name [get_object_name $my_cell];
   echo $cell_name; 
   }
	
 -foreach_in_collection my_cell [get_cells *] {
    set cell_name [get_object_name $my_cell];
    set rn [get_attribute [get_cells $cell_name] ref_name];  
    echo $cell_name $rn; 
    }
 -read_verilog DC_WORKSHOP/verilog_files/dff_const5.v
 -link
 -compile

 >Run in Design Vision 
 -read_verilog DC_WORKSHOP/verilog_files/dff_const5.v
 -link
 -compile
	 
 ```

>![image](https://user-images.githubusercontent.com/118953939/210133170-ba9ea212-bfc0-40cb-89a2-e9a16bbe8567.png)
	
</details>
	
 <details>
<summary>Special Optimization(Theory)</summary>
	 
>![image](https://user-images.githubusercontent.com/118953939/210133281-e690cb59-2702-445f-8fac-9655faee9091.png)

>![image](https://user-images.githubusercontent.com/118953939/210133286-9e339ad8-42d5-4e83-a112-308456c043e8.png)

>![image](https://user-images.githubusercontent.com/118953939/210133289-fe0d5b02-4154-4360-8dec-91d3cb346e6e.png)

>![image](https://user-images.githubusercontent.com/118953939/210133300-34483916-1024-4536-b088-e4b688b25b1f.png)

>![image](https://user-images.githubusercontent.com/118953939/210133323-bcc0a390-d342-4d17-8e6e-0a0a105b283e.png)

>![image](https://user-images.githubusercontent.com/118953939/210133352-77a89b65-2833-48f4-83a7-6d7ba1cb79ea.png)
</details>
	
 <details>
<summary>How Paths are timed MCP? (Theory)</summary

>![image](https://user-images.githubusercontent.com/118953939/210133392-a040a8aa-26cf-4746-b476-fd72f84a03c3.png)

>![image](https://user-images.githubusercontent.com/118953939/210133398-4cfd65a5-792a-45a1-ac87-b2c2e4027dd2.png)

>![image](https://user-images.githubusercontent.com/118953939/210133413-0f63f947-ce20-4d74-94a0-3ad01e1fc130.png)
</details>

 <details>
	 <summary>Boundary Optimization  (LAB)</summary>

- Boundary Optimization 
```
sh gvim DC_WORKSHOP/verilog_files/check_boundary.v
	read_verilog DC_WORKSHOP/verilog_files/check_boundary.v
-link
-compile_ultra
-write -f ddc -out boundary.ddc
-get_cells
	
>In design_vision
-read_verilog DC_WORKSHOP/verilog_files/check_boundary.v
-link
-get_cells						
-set_boundary_optimization u_im false
-compile_ultra
-start_gui
```

>![image](https://user-images.githubusercontent.com/118953939/210133514-4b0b9d09-c38d-4edc-ad72-acfc3cfffe31.png)

>![image](https://user-images.githubusercontent.com/118953939/210133521-f2a3dbf0-e15f-4a73-bae8-6f7317ee78a4.png)
	</details>
	
 <details>
	 <summary>Register Timing  (LAB)</summary>
	 
- Command 
```
-sh gvim DC_WORKSHOP/verilog_files/check_reg_retime.v
```
>![image](https://user-images.githubusercontent.com/118953939/210133670-0f754cca-7858-45ed-82b7-aa51213483b3.png)

- In Design Vision 
```
-read_verilog DC_WORKSHOP/verilog_files/check_reg_retime.v
-link
-compile
-start_gui
-sh gvim DC_WORKSHOP/verilog_files/reg_retime_cons.tcl			(Setting the constraints)
-source DC_WORKSHOP/verilog_files/reg_retime_cons.tcl
-report_clocks
-report_timing
-compile_ultra -retime
-start_gui
```
>![image](https://user-images.githubusercontent.com/118953939/210133678-5ede04fd-3fe0-41ff-b29d-67b6aca6cc9a.png)



- Report Timing  
```
report_timing
compile_ultra
report_timing -from [all_inputs]
report_timing -from [all_inputs] -trans -cap -nosplit -sig 4
```
>![image](https://user-images.githubusercontent.com/118953939/210133686-e82e1539-71a4-4dd6-89b8-ac5c15feebe8.png)

</details>

<details>
<summary>Isolating Output Ports (LAB)</summary>
	
```
sh gvim DC_WORKSHOP/verilog_files/check_boundary.v
```
>![image](https://user-images.githubusercontent.com/118953939/210134334-57050b2e-0fc1-416e-adef-ab7ca68c4fdc.png)

	 
- isolated setup 
	 
```
-read_verilog DC_WORKSHOP/verilog_files/check_boundary.v
-link
-compile_ultra
-start_gui
-set_isolate_ports -type buffer [all_outputs]
-compile_ultra
-start_gui
	
>![image](https://user-images.githubusercontent.com/118953939/210134342-0ce51d8a-304e-4f9e-82e4-eb11a36f84eb.png)
```
	
- Set constraints and vie report before isolated
```
read_verilog DC_WORKSHOP/verilog_files/check_boundary.v
link
compile_ultra
create_clock -per 5 -name myclk [get_ports clk]
set_input_delay -max 2 [all_inputs] -clock myclk
set_output_delay -max 2 [all_outputs] -clock myclk
set_load -max 0.3 [all_outputs]
report_timing -nosplit -inp -cap -trans -sig 4
report_timing -to val_out_reg[0]/D -inp -trans -nosplit -cap -sig 4		(Viewing report timing before isolating portr -> reg to reg path)
```
	
- Report Timing After isolated	 
```
set_isolate_ports -type buffer [all_outputs]
compile_ultra
report_timing -nosplit -inp -cap -trans -sig 4
report_timing -from val_out_reg[0]/CLK -to val_out_reg[0]/D -nosplit -inp -cap -trans -sig 4
```
>![image](https://user-images.githubusercontent.com/118953939/210134351-338b3938-3f8a-4ad3-815f-96f3708e2bb7.png)
</details>

<details>
<summary>Multi Cyle Path (LAB)</summary>

```
sh gvim DC_WORKSHOP/verilog_files/mcp_check.v
```
![image](https://user-images.githubusercontent.com/118953939/210134607-45925f53-a463-4380-ab46-6129275b960d.png)

- set constraints 
```
read_verilog DC_WORKSHOP/verilog_files/mcp_check.v
link
compile_ultra
sh gvim DC_WORKSHOP/verilog_files/mcp_check_cons.tcl
source DC_WORKSHOP/verilog_files/mcp_check_cons.tcl
report_timing
compile_ultra
report_timing
set_multicycle_path -setup 2 -to prod_reg[*]/D -from [all_inputs] 	(Must put all_inputs -> valid to prod_reg is a single cycle path. If [all_inputs] didn't     	                                                         there, it will mcp the valid to prod_reg path too. This is a CRIMINAL MISTAKE!)
report_timing -to prod_reg[*]/D -from valid_reg/CLK
report_clock *
report_timing -to prod_reg[*]/D -from [all_inputs]
```
>![image](https://user-images.githubusercontent.com/118953939/210134697-d9cdc8d6-8d95-4119-ae4c-65640625a90d.png)

>![image](https://user-images.githubusercontent.com/118953939/210134705-212464ff-f6ae-4628-928a-a3857e870627.png)

- Hold time
```
-report_timing -delay min
```
- Apply MCP hold time 
```
set_multicycle_path -hold 1 -from [all_inputs] -to prod_reg[*]/D
report_timing -delay min -to prod_reg[*]/D -from [all_inputs]
```	
![image](https://user-images.githubusercontent.com/118953939/210134821-15373113-6e9c-466b-a320-0600c58b1490.png)

- Isolated Output ports 

```
-set_isolate set_isolate_ports -type buffer 
-report_timing -nosplit -inp -cap -trans -sig 4
-report_timing -to prod_reg[*]/D -from [all_inputs]
```

![image](https://user-images.githubusercontent.com/118953939/210134838-957e43dc-2f0e-45bb-a867-578be4017152.png)
![image](https://user-images.githubusercontent.com/118953939/210134850-9453d20d-8c89-42d8-84f8-c90b661ed0ce.png)

</details>

## Day 10 
### Topic -Quality Checks
 
 <details>
<summary>Report Timing (Theory)</summary>

>![image](https://user-images.githubusercontent.com/118953939/210150544-5837b65c-7971-4c26-ae34-604848969670.png)

>![image](https://user-images.githubusercontent.com/118953939/210150554-7f645bcd-f5f6-4103-a7c0-59d68c35902c.png)

>![image](https://user-images.githubusercontent.com/118953939/210150562-7def7570-1878-4a4b-8466-87c8b8d4371f.png)

>![image](https://user-images.githubusercontent.com/118953939/210150566-2b6b688c-85a5-4169-8a00-7dc1ca453731.png)

>![image](https://user-images.githubusercontent.com/118953939/210150581-5c8c97c7-b613-49df-ba3f-236028c98f3c.png)
	</details>

<details>
<summary>Report Timing (LAB)</summary>	
	
```	
report_timing -nosplit -trans -cap -nets -inp -from IN_A > t1.rpt
report_timing -rise_from IN_A -sig 4 -trans -cap -nets -inp > t2.rpt
```
>![image](https://user-images.githubusercontent.com/118953939/210150664-3ddc61b5-f50a-4c60-873e-d941ca827d1c.png)

```
report_timing -nosplit -trans -cap -nets -inp -from IN_A > t1.rpt
report_timing -rise_from IN_A -sig 4 -trans -cap -nets -inp -to REGA_reg/D
```
>![image](https://user-images.githubusercontent.com/118953939/210150779-2717bc93-0ca2-4276-97ab-f13a39067be1.png)

```
report_timing -delay min -from IN_A
report_timing -thr U15/Y
report_timing -thr U15/Y –delay min
```
>![image](https://user-images.githubusercontent.com/118953939/210150814-dd7c0839-f924-4b81-a071-9d7b2f7a768c.png)

</details>

<details>
<summary>Lab check_timing,Check_design,Set_max_capacitance and HFN(LAB)</summary>
	
```
read_verilog DC_WORKSHOP/verilog_files/lab8_circuit.v
link
check_design
compile_ultra
checking_timing 
report_constraint
```
>![image](https://user-images.githubusercontent.com/118953939/210175392-c2f75285-8933-4cca-8a72-2750df1bdec5.png)

```
source DC_WORKSHOP/verilog_files/lab8_cons_modified.tcl
checking_timing 
report_constraint
```
>![image](https://user-images.githubusercontent.com/118953939/210175403-343e18b8-a3ac-443a-9e52-a9b755f12276.png)

```
read_verilog mux_generate_128_1.v 
link
compile_ultra
write -f verilog -out mux_generate_128_1_net.v
sh gvim mux_generate_128_1_net.v &
dc_shell> get_cells * -hier -filter "is_sequential == true"
dc_shell> get_cells * -hier -filter "is_sequential == false“
```
>![image](https://user-images.githubusercontent.com/118953939/210175421-afb13551-62c7-4dd6-8704-67865e6de048.png)

```
report_timing -net -cap -sig 4
check_timing
set_max_delay -from [all_inputs] -to [all_outputs] 3.5
````
>![image](https://user-images.githubusercontent.com/118953939/210175450-32a68566-a06b-4554-94ff-72aacc9d54f6.png)
	
```
set_max_capacitance 0.025 [current_design]
report_constraint -all_violators
compile_ultra
report_constraint
report_timing
report_timing –net –cap –sig 4
```
![image](https://user-images.githubusercontent.com/118953939/210175488-6cf3450b-a444-43a6-820d-adb729fc285d.png)

```
reset_design 
read_verilog en_128.v
link
compile_ultra
report_timing -from en -inp -nets –cap
report_constraint
```
```
set_max_capacitance 0.03 [current_design]
compile_ultra
report_timing -from en -inp -nets –cap
report_constraint
write -f ddc -out en_128.ddc
Design vision
Read_en_18.ddc
```
>![image](https://user-images.githubusercontent.com/118953939/210175517-6e83772e-b655-4857-86be-eb36e44afcaa.png)

```	
report_timing -from en -inp -nets –cap –trans –sig 4
set_max_transition 0.150 [current_design]
report_constraints
Check_timing 
Report_timing 
```
>![image](https://user-images.githubusercontent.com/118953939/210175536-e2a79a89-2251-4cc0-ab86-9800e999b400.png)

```
report_timing -from en -inp -nets -cap -trans -sig 4 -from en -to y[116]	
```
>![image](https://user-images.githubusercontent.com/118953939/210175552-5861d687-67f2-4d14-925e-1479a14cfb5b.png)

</details>

<details>
<summary>Summarizing Synthesis</summary>

>![image](https://user-images.githubusercontent.com/118953939/210175592-7571fa42-f71b-4406-916d-638cd04dd6e3.png)
</details>

<details>
<summary>Timing Models(ETM,QTM)</summary>
Timing Models (ETM & QTM)

* Timing Model 
If we want to perform static timing analysis on a chip using PrimeTime, every leaf cell must have a timing model. For static timing purposes, a leaf cell can be a simple macro cell (such as a NAND, NOR, or flip-flop) or a complex block (such as a RAM or microprocessor).

* ETM (Extracted Timing Models) ?
The Extracted Timing Model (ETM) is an abstraction of the block using sequential and combinational timing arcs. NLDM lookup tables are extracted for each of the timing arcs whose delay is a function of input transitions and output loads, which makes the ETM usable with different input transition times and different output loads.Using ETMs to abstract the timing model of a complex block or IP hides the detailed design implementation information. This usage model is ideal for IP providers.

```	
1.Block based model (.lib)
	
2.Contents of block are hidden
	
3.Original netlist replaced by model containing timing arcs for block interfaces.
	
4.NLDM lookup tables are extracted for each of the timing arcs.
	
5.These arcs whose delay are a function of input transition and output load. This makes ETM usable with different input transition times and different output loads.
	
6.Multiple modes per model
	
7.Single PVT per model
```
	
* QTM (Quick Timing Models):
In the early stages of the design cycle, if a block does not yet have a netlist, you can use a quick timing model to describe its initial timing. Later in the cycle, you can replace each quick timing model with a netlist block to obtain more accurate timing

Reference
http://mantravlsi.blogspot.com/2014/06/timing-models-etm-qtm-ilm.html
	
</details>

	
## Day 11
Topic - BabySoC

<details>
<summary>How Chips Manufactured ?</summary>
	
* **How Chips are made**? 
Chips begin with a very simple raw ingredient called SAND. Complex chemical and physical techniques are necessary to manufacture a pure monocrystalline silicon ingot, known as a boule, from sand, with only one impurity atom for every ten million silicon atoms. A specific sawing process is then used to cut extremely thin wafers from the silicon boules. Wafer sizes of 150, 200, and 300 mm are the most popular. Larger diameter wafers provide greater area for semiconductors. This wafer has the ability to carry electricity while also acting as an insulator.


* **How to allow wafer become conductive ?.**
Small quantities of specific atoms are added as impurities to the wafer. These impurity atoms must have a number of outer electrons that is either one more or one less than that of silicon. For example boron and phosphorus.The material becomes p-conductive or n-conductive depending on the amount of outside electrons. Transistors are formed on the doped wafer's p- and n-conductive layers. Microchips' smallest control units are transistors. They are the most crucial components of electronic circuits because they control electric voltages and currents.


* **How layer created on a wafer?**

1.The manufacturing of chips from a wafer begins with the layout and design phase. Highly complicated chips are composed of billions of integrated and connected         transistors.

2.The wafer's surface is oxidised in a high-temperature furnace operating at around 1000 degrees Celsius to form a non-conductive layer. Then, employing centrifugal  	force, a photo resist substance is uniformly placed on this non-conductive layer.

3.The wafer is then exposed to light through the photomask in steppers. The chip pattern's exposed area is created, disclosing the layer of oxide beneath. The wafer      is then exposed to light via the mask after another application of photoresist.

4.The following step is the doping procedure, which involves introducing impurity atoms into the exposed silicon. To inject impurity atoms into the silicon, an ion     implanter is employed. 

5.Following the removal of the photoresist residue, another oxide layer is placed. The wafer goes through another cycle of photoresist application, mask exposure, and stripping. A chemical-mechanical technique is used to polish away surplus material with millimetre accuracy to provide the insulating layer above the interconnections the smooth finish it requires. During the fabrication process, these individual processes may be performed several times.

6.Assembly is the final stage of manufacture. Individual chips are placed in a package and terminals are connected. The end product is a completed semiconductor         device that may be installed on circuit boards using several types of connections. It is possible to make over a thousand connection contacts.
	
**REFERENCE : https://www.infineon.com/cms/en/product/promopages/how-a-chip-is-made-video/**
</details>
	

	
<details>
<summary>SoC</summary>


* **What is SoC ?**
	
Soc acronym for system on chip is an IC which intergrates all the components into a single chip.It may contain analog,digital mixed signal and other radio frequency.Today,SoCs are very common in electronics industry due to its low power consumption.

* **Why is SoC ?**
To increased performance and reduced power consumption as well as a smaller semiconductor die area.

* **SoCs consists :**

1.Control Unit :In SoCs,the major control units are microprocessors,microcontrollers and digital signal processors.
	
2.Memory Blocks :ROM,RAM.Flash memory and EEPROM are the basic memory units inside a SoC chip.
	
3.Timing Units :Oscillators and PLLs are timing units of the System on Chip.
	
4.Other perpherals of SoCs are counter timers,real-time timers and power on reset generators.
	
5.Analog interfaces,external interfaces,voltage regulators adn power management units form the basic interfaces of the SoCs.

* **Structure of Snapdragon**
	
>![image](https://user-images.githubusercontent.com/118953939/210299468-67724854-53b7-49c0-a4d0-1c0764ea046b.png)

* **Type of SoC**
 
1.SoCs built around a microcontroller.

2.SoCs built around a microprocessor.

3.Specialized application-specific integrated circuit SoCs designed for specific application that cannot fit into theabove two categories.
	
* **SoC Design Flow**

>![image](https://user-images.githubusercontent.com/118953939/210301229-0affa0bb-e865-445c-b52c-545d3b7f16fb.png)

</details>
	
	
<details>
<summary>BabySoC</summary>

* **Introduction to BabySoC**
VSDBabySoC is a small 

The VSDBabySoC is a small but capable RISCV-based SoC. The primary goal of creating such a small SoC is to **test three open-source IP cores together for the first time and calibrate the analogue portion of it**. The **RVMYTH CPU, an 8x-PLL to provide a reliable clock, and a 10-bit DAC** to interface with other analogue devices are all included in the VSDBabySoC.

>![image](https://user-images.githubusercontent.com/118953939/210303616-3abe26cc-a177-4295-b426-e8831ee4c8a4.png)

**Credit : VLSI System Design https://www.vlsisystemdesign.com/

* **What is RVMYTH**?
RVMYTH core is a simple RISCV-based CPU,introduced in a workshop by RedwoodEDA and VSD .RVMYTH is designed and created by the TL-Verilog lanuage.So,we need a way to compile and transform it to the Verilog Language and use the result in our SoC.


* **What is PLL**?
PLL or Phase-locked Loop  is a control system that generated an output signal whose phase is related to the phase of an inout signal.
	
* **What is Digital-to Analog converter(DAC)**?
A digital-to-analog converter or DAC is a system that converts a digital signal to an analog signal.
</details>
	
## Day-12
### Topic:BabySoC Modelling 

<details>
<summary>Theory</summary>
	
**What exactly is modelling?**

The use of a physical/logical representation of a given system to create data and help determine decisions/predictions about the system is known as modelling and simulation (M&S).In the VLSI arena, M&S is commonly used.
	
**Purpose of modelling**

System models are created to assist in the analysis, specification, design, verification, and validation of a system, as well as to communicate specialised information.

**What are we modelling ?**

-Some initial input signal will be fed into vsdbabysoc module.

-That will get the pll start generating the proper CLK for the circuit.

-The clock signal will make the rvmyth to execute instructions and some are values are generated.

-3 main element(IP cores) and a wrapper as an SoC.

**RVMYTH-Risc-V based MYTH (Microsprocessor for you in Thirty Hours)**

-RISC = RISC stand for Reduced Intruction set computer.

-RISC-V(Risk-Five) -Instruction set Architecture(ISA) is defined as base integer ISA,which must be present in any implementation plus optional extensions to the base ISA.
-The width of the integer registers and the associated size of the address space, as well as the number of integer registers, distinguish each base integer instruction set. RV32I and RV64I are the two basic base integer versions.

**Simple one cycle CPU for Risc-V**

>![image](https://user-images.githubusercontent.com/118953939/210682666-f16d8ac8-85e0-4565-afd6-54990d05bb48.png)

Refference : https://www.vlsisystemdesign.com/


**Phase Locked Loop(PLL)**

- An electronic circuit with a voltage or voltage -driven oscillator that constantly adjusts to match the frequency of an input signal.

- This PLLs are used to generate,stabilize,modulate,demodulate.

**WHy off-chip clocks can't be used all the time ?**

- Clock will be supply for a lot of blocks on the chip.If we used only one clock source it will have delays due to long wires.

- One small cip will suply on some block with different frequency 200Mhzs adn some might need 100Mhz.

- A concept of ppm(parts per million) clock accuracy comes in,when ever quarts is acquired,it comes with a x ppm error.
	
**PLL used on SoC**

Main components:

- Phase detector

- Loop filter

- Voltage controlled oscillator

- Frequency divider
	
**Digital Analg Converter**
	
- puporse-converts a digital input signal to an analog output signal.

- digital signal is repsented with binary code (combinations logic 0 adn 1).

- consists of anumber of binary inputs and a single output.

- Two types DACs 
	
	- Weighted Resistor DAC = resistor DAC prduces an analog output,which is almost equal to the digital(binary) input by using binary weighted resistor in the                                      inverting adder circuit.
	
	- R-2R Ladder DAC =overcomes the disadvantages of a binary weighted resistor DAC.It produces an analog output which is almost equal to the digital(binary)               input by using aR-2R ladder network in the 

**Weighted Resistor DAC**
	
![image](https://user-images.githubusercontent.com/118953939/210687752-54a2f06c-1e63-4842-9f77-fbb37be73864.png)

reference : https://microcontrollerslab.com/binary-weighted-resistor-dac-working-example-circuits-advantages/

**R-2R Ladder DAC**
	
![image](https://user-images.githubusercontent.com/118953939/210688990-348d0537-c5d8-48f5-97ea-634892929c8b.png)

references :https://www.electronics-tutorials.ws/combination/r-2r-dac.html
	
**Tips modelling in design**

- Avoid race conditions (use VCS race detection tool).

- Use a optimized Testbench for debugging your design.

- Creating models that simulate faster.

- case statement behavior.

**DVE(Normal mode**
- provides graphical user interface(GUI) to debug the design.

- Step Open GUi with normal mode

  1.Run the design with valid testbench 

  2.compile 

  3.cross check .vcd file

  4.invoking DVE tool.

**DVE (Interactive mode)**

- Debugging the design in interactive mode or in post-processing mode with a valid testbench

- Steps to open GUI with interactive mode:

  1.Run the design with a valid testbench

  2.Get the code dump file (.vcd)

  3.This should open the tool automatically and we can fully run our test bench or debug it step by step

**RVMYTH modelling**

- RISC-V CPU core has been written in Verilog and already written testbench code for the same

- Entire C program will be converted into a hex format and will be loaded into memory

- CPU will then read the contents of the memory, process it and display the output result of sum numbers from 1 to n
</details>

<details>
<summary>Lab 12</summary>

- Modelling RVMYTH Core
>![image](https://user-images.githubusercontent.com/118953939/210833664-23ad940e-096b-4960-bf08-81601bb59e25.png)

>![image](https://user-images.githubusercontent.com/118953939/210833707-99000591-a1b6-41f8-8d44-9e33f847fbf7.png)

- DAC modelling (avsddac.v & avsddac_tb_test.v)
> ![image](https://user-images.githubusercontent.com/118953939/210834328-99579ae1-de0a-48ed-b36c-ea17f3f0c9fd.png)

> ![image](https://user-images.githubusercontent.com/118953939/210834389-9703585b-d791-4742-95fc-ab0f54c0d614.png)

- PLL(avsd_pll_1v8.v & pll_tb)

>![image](https://user-images.githubusercontent.com/118953939/210835668-07e78d0b-39f6-4746-a3a0-ca0280b8fa62.png)

>![image](https://user-images.githubusercontent.com/118953939/210835746-5ac92cee-40ac-445d-99e4-7d8eca5dc692.png)

- Debug mode 

>![image](https://user-images.githubusercontent.com/118953939/210835855-af3ebc9a-4c01-49da-b7fe-80aea017dc7b.png)

* **Verified Block Separately**

>![image](https://user-images.githubusercontent.com/118953939/210836041-430b1f0f-7d3e-4a44-b665-197acbdc372f.png)

>![image](https://user-images.githubusercontent.com/118953939/210836185-642de8cf-05ff-43df-b8da-d5a3c270c6b5.png)

- rvmyth_avsddac.v & rvmyth_avsddac_TB.v

>![image](https://user-images.githubusercontent.com/118953939/210837004-c419b9bc-9a0f-4cb6-840f-bf6b743b9628.png)

>![image](https://user-images.githubusercontent.com/118953939/210837058-c1c7f68f-b2e4-419a-8082-401fcd62db3e.png)

- Difference Modes

>![image](https://user-images.githubusercontent.com/118953939/210837347-32558eb1-3a99-4d85-9052-45ab7d017cf7.png)
	
>![image](https://user-images.githubusercontent.com/118953939/210956227-11ba413a-50cd-4f86-97a9-e6bc10b067ec.png)


* **ADDTIONAL CIRCUIT**
- Up Counter 

> ![image](https://user-images.githubusercontent.com/118953939/210837598-8d2a160f-e8bf-4395-a72c-f164c5ae85e5.png)

- Block Diagram 

>![image](https://user-images.githubusercontent.com/118953939/210839918-4c6626ad-8194-4012-bc54-af5ac411216a.png)

refferences : https://www.electronics-tutorials.ws/counter/count_3.html
</details>

## Day 13
### Topic - Post Synthesis Simulation 

What did  Pre-synthesis ?
Basically - modelled and simulated the IP cores in VSDBabySoC(for checking its functionality) 

<details>
<summary>Recap on Pre-Synthesis </summary>

- **Why we did pre-synthesis** = modelled and simulated the ip cores in VSDBabySoc (for checking its functionality).

- **Synthesizable and non-Synthesiszable constructs?**
	
>![image](https://user-images.githubusercontent.com/118953939/211203816-b1137e5d-9b23-4489-9e90-b5d2a3e80dab.png)

- **Why we do pre-synthesis ?**
-Pre-synthesis simulation is done according to the logic you have designed for and written which is functionality.

</details>

<details>
<summary>Post-Synthesis </summary>

- **What Post-Synthesis ?**
Post synthesis /gate level simualtion (GLS) is done after synthesis considering each and every gate delays into account.This synthesis was reports the violations in both functionality and timing.This also shows's the mismatches we are likely to get due to wrong usage of operators and inteference of lathces.

- **Why we need to do Post-Synthesis ?**

- **Gate level Simualtion (GLS)**
1.The term "gate level" refers to the netlist view of a circuit, usually produced by logic synthesis. 

2.So while RTL simulation is pre-synthesis, GLS is post-synthesis. 

3.The netlist view is a complete connection list consisting of gates and IP models with full functional and timing behavior. 

4.RTL simulation is a zero delay environment and events generally occur on the active clock edge. GLS can be zero delay also, but is more often used in unit delay or

full timing mode. 

- **Synthesize using DC Compiler**

1.Point to one file and invoke DC & read the verilog file.For example tvmyth_avsddac.v

2.read.db file and set target library to sky130_fd_sc_hd__tt_025C_1v80.lib, avsddac.lib

- **What we need to do if we dont have .lib**
To make sure we consider each and every gate delays into account.How ever the pre-synthesis simulations were done using VCS and DVE(./simv) we do the samea nd observe the output.

1.lc_shell

2.read_lib library.lib(if in the same directory as the .lib) Else - > read_lib <your_path>/library.lib

3.write_lib library -format db -output library.db

4.Quit 

- **After getting the .db let us resume**

1.Invoke DC and Read the verilog file -> rvmyth_avsddac.v

2. Read .db file and set target_lib -> sky130_fd_sc_hd__tt_025C_1v80.db, avsddac.db(use both the timing libraries)

3.Write -f verilog command, synthesizing the code
 </details>
 
 <details>
<summary>Lab 13 </summary>

**Invoke lc_shell --> to change .lib to .db.THis step can be skip if we have .db file** 

(i)rvmyth_avsddac

- Step 
```
1.lc_shell
2.read_lib library.lib(if in the same directory as the .lib) Else - > read_lib <your_path>/library.lib
3.write_lib library -format db -output library.db
4.quit 
```
>![image](https://user-images.githubusercontent.com/118953939/211346771-5c7fc83c-4599-47fd-a0aa-d126bc3f278c.png)

>![image](https://user-images.githubusercontent.com/118953939/211347136-09be2a28-c308-4fec-a013-03847df6bc66.png)
```
we need to modified the error 
```
>![image](https://user-images.githubusercontent.com/118953939/211347171-a9dd19ed-f7c2-456e-8676-52abc8bf1e75.png)

**Synthesis can be resume after we have .db by invoke Dc_shell**
```
Target library and link library must be set with sky130_fd_sc_hd__tt_025C_1v80.db &  avsddac.db
read_file {mod_avsd_pll_1v8.v mod_mythcore_test.v clk_gate.v mod_rvmyth_pll.v } -autoread -format verilog -top rvmyth_pll_interface
```	 
>![image](https://user-images.githubusercontent.com/118953939/211759934-7c4a7af4-8648-4968-958e-e2635035db43.png)

**Compile**
```
Compile design until  optimization sucessfully
```
>![image](https://user-images.githubusercontent.com/118953939/211760397-8ae380b2-f22f-49d8-bee0-c3751b415248.png)

**Report constraint and report timing**

```
-report_constraint
-report_timing 
```
>![image](https://user-images.githubusercontent.com/118953939/211760505-ad0604fe-36c2-47e8-abd7-458f73418682.png)

**Create netlist file**
```
write -f verilog -out <new file>
```
>![image](https://user-images.githubusercontent.com/118953939/211760719-a3427c8e-99bb-466c-8301-f0d0e22af164.png)


(ii)rvmyth_pll 

The step was same as previous on rvmyth_avsddac.v 

**Target Library**
>![image](https://user-images.githubusercontent.com/118953939/211761272-ae42d39e-3c80-4c96-92f9-6051c8c39753.png)

**read_file**

```
Before read the file we need to fix all the error in rvmyth_pll.v mythcore_test.v and avsd_pll_1v8.v
read_file {mod_avsd_pll_1v8.v mod_mythcore_test.v clk_gate.v mod_rvmyth_pll.v } -autoread -format verilog -top rvmyth_pll_interface
```
>![image](https://user-images.githubusercontent.com/118953939/211763376-2d40e5fa-7637-4ab2-afb7-c906a151769f.png)

>![image](https://user-images.githubusercontent.com/118953939/211763423-bdc85de6-cb7f-4b41-b593-9ccc92be06f0.png)


**Report constraints and Report_timing**
>![image](https://user-images.githubusercontent.com/118953939/211761521-7546efae-9395-427b-a71d-cdf0a6b51b50.png)

**Creating netlist file**
>![image](https://user-images.githubusercontent.com/118953939/211763875-f3208bef-b796-461e-94bc-1d358890187c.png)
	 
(iii) VsdbabySoC
	 
**Repeat the same step as previous**
>![image](https://user-images.githubusercontent.com/118953939/212089894-657e22b4-7a7f-49ff-8d81-24095bf22739.png)
	 
**check report timing before constraints**

>![image](https://user-images.githubusercontent.com/118953939/212090089-d6a9d469-8c9c-4ad8-b6b7-0dd81b782722.png)

>![image](https://user-images.githubusercontent.com/118953939/212090126-7cd9755f-98e3-4fb7-a190-39eb48de0a18.png)

**After Constraint**
	 
>![image](https://user-images.githubusercontent.com/118953939/212090444-447b7787-d5d6-4769-a457-c9cfc5f20855.png)

>![image](https://user-images.githubusercontent.com/118953939/212090491-fa5a4af1-9bbf-46c2-a22d-d5048d7ad001.png)

**VSDBabySoc netlist**
	 
>![image](https://user-images.githubusercontent.com/118953939/212090583-cd9dfa36-bd35-499f-b56e-59e08b316c93.png)
	 
>![image](https://user-images.githubusercontent.com/118953939/212090934-d1c9bfc7-5b76-4b01-9c4a-0c4afa49fd71.png)

 </details>
	 

## Day 14
## Topic - PVT corner 
	 
<details>
<summary>Theory PVT Corner (Theory) </summary>

**What is PVT**
	
Process: refers to the variation.The parameters of transistors during fabrication, as layers getting fabricated cannot be uniform across the die.Process type 
	(tt=typical-typical,ff=fast-fast,ss=slow-slow,fs=fast-slow,sf=slow-fast)
	
Voltage: refers to the varying voltages on chip during operation, can be cause by few reason such as IO drop or supply noise from parasitic inductance

Temperature: refers to the varying temperature of chip during operation due to power dissipation in the MOS-transistors which will affect the delay on the cells

| PROCESS       | VOLTAGE       | TEMPERATURE   | 
| ------------- | ------------- | ------------- |
|![image](https://user-images.githubusercontent.com/118953939/212098886-d56b7836-eaef-4cbe-9101-28fb30dceb5e.png)|![image](https://user-images.githubusercontent.com/118953939/212100152-758840ef-7b85-4c45-9af2-d5a191f6c30d.png)|![image](https://user-images.githubusercontent.com/118953939/212102082-a1826235-0026-4346-8e86-7364ad828cc2.png)| 
|During fabrication, different tasks or die areas have different process variations.|The voltage change is caused by an IR dip or supply noise.|The density of transistors varies across the chip, resulting in power dissipation and temperature variations.|
	
**WNS=** Worst Negative Slack

**TNS=** Total Negative Slack = sum of the negative slack paths

**WHS=** Worst Hold Slack

**THS=** Total Hold Slack = sum of the negative hold slack paths
	
</details>
	
	 
<details>
<summary>Theory PVT Corner (Lab ) </summary>
 
- Step 
```
1) source setup.tcl
2) source target library 
3) read_file { mod_mythcore_test.v avsdpll_new.v mod_vsdbabysoc.v clk_gate.v} -autoread -format verilog -top vsdbabysoc
4) source vsdbabysocconstraint_new.tcl ---> constraints file 
5)link
6)compile
All step repeated by changing the .lib on target library 
```
** target library and set constraints**
	
![image](https://user-images.githubusercontent.com/118953939/212093524-04b075de-6e2f-4f44-8d8f-56019079fe5c.png)



	 
>![image](https://user-images.githubusercontent.com/118953939/212094064-e99d989e-d187-4b1a-b2c2-2686572f1250.png)
 
>![image](https://user-images.githubusercontent.com/118953939/212094090-b4f21912-b80b-459d-a641-5a189c95f9fb.png)

>![image](https://user-images.githubusercontent.com/118953939/212094129-15396c9a-2561-43c7-9feb-835cae6f2358.png)
 
**Summarizing**
	 
As we can see the base PVT has been choise because the wns and tns on the hold and setup small.
>![image](https://user-images.githubusercontent.com/118953939/212094283-3339b1bf-c4c7-489b-aa1f-ad12cdae6bdd.png)

</details>


## Day 15 
### Topic Inception of Open-source EDA,OpenLANE and Sky130 PDK

  
 <Details>
 <summary>Introduction to QFN-48 PAckage,Chips,PAds,Core,Die adn IPs</summary>
 
 Package it is the material that contains semiconductor device attached with a die using wire bonding. Package is a container that holds die and was connected to outside (external device) by using wire bonding. Example of package - Quadruple in-line package (QIP) and Dual in-line package (DIP).  
   
- Wire Bond - The method of making interconnections between an integrated circuit (IC) or other semiconductor device and its packaging during semiconductor device fabrication.
- Pad - used to connect inside (core) to outside (I/O), good at ESD protection to prevent charge coming from outside damage the core inside.
- Core - consists of all the main logic gate (NMOS/PMOS) and cell block such as macro cell and foundry IP's.
- I/O - help in communication between die with external and will be connected to die by using wire bonding.
- Macro - a simple core/cell with simple functionality and can be easily found online.
- Foundry IP's - cell with more specific functionality and the design was patent/owned by a company. Has higher value compared to macro.   

 >![image](https://user-images.githubusercontent.com/118953939/212259025-4bc6969f-83f9-4fee-8581-d38d4bf8816a.png)
 
 source :https://www.vlsisystemdesign.com/
  </details>
  
 <Details>
 <summary>Introduction to RISC-V</summary>
 
 **Process of converting RISC-V architecture to layout** 
 
  1) C++ codes will be compiled in RISC-V assembly language program.
  2) This assembly language will convert the code to the machine language which is binary language that containing logc 0 and logic .This binary language only              undertstood by the computer and it will be used to sketched in a layout by the computer program and we will get the required output.
  3) But another interface also played their role between architecture and layout of RISC-V which is Hardware Description LAnguage(HDL) where it used implementing the        specification of RISC-V.
 
 >![image](https://user-images.githubusercontent.com/118953939/212260209-f2a32a5a-afc7-4dac-a3b5-8d1398282856.png)
  source :https://www.vlsisystemdesign.com/
   </details>
   
  <Details>
 <summary>From Software Aplications to Hardware</summary>
 
 **Flow fo The Synthesis Process**
  
 - Software(HLL) --> System Sofware(aseembly Language) --> Hardware(machine language)
 - Essentially, the application software would enter the system software's clock, and the system software would turn the application programme into binary code.
 -  The Operating System (OS) is a major process in system software that takes specific applications and converts them into relevant assembly language programmes and      binary programmes so that the programme may be understood by the hardware.
 - The transformed binary language/machine language is fed into the hardware, which produces the output.
 
 - Operating Systems (OS) --> Handle IO operations,allocate memory and low level system functions
 - Compiler --> Cenverting the programming language intro the respective instructions.The syntax instruction is depending upon what kind of the hardware belong to        RISC-V format,the syntax would haev the syntax of RISC-V format instructions.
 - Assembler --> take particular instructions and convert it into the respective binary number which is machine language program.

 >![image](https://user-images.githubusercontent.com/118953939/212260151-810c2458-81aa-472d-893d-bb41b7a284ee.png)
 source :https://www.vlsisystemdesign.com/
</details>

  
 ### Topic SoC design and OpenLANE.
 
  <Details>
<summary>Introduction to all components of open-source digital asic design </summary>
 
**Element that required to designing an automated ASIC flow** 
  
 - Hardware Description Language (HDL) which Register Transfer Level (RTL) model of the function we want to implement including RTL's IP.
 - Tool used for automation such as Electronic Design Automation (EDA) tools.
 - Process Design Kit (PDK) data.
    - The interface between the FAB and the designers 
    - Collection of files used to model a fabrication process for the EDA tools used to design and IC.
        - Process Design Rules :DRC,LVS and PEX
        - Device Models
        - Digital Standard Cell Libraries
        - I/O Libraries
  
>![image](https://user-images.githubusercontent.com/118953939/212272437-d8b736be-8326-4716-b03d-bb0b107312b6.png)
 Source : Takens from lecture video.
  </details>
  
     
 <Details>
 <summary>ASIC Design Flow</summary>

 - ASIC Flow Objective :RTL to GDSII = Take Design from Resistor transfer level (RTL) to GDSII format for the final layout and it also called as Automated PnR and        Physical Implementation.
 - RTL to GDSII flow 
    - Synthesis --> Floor/Power Planing --> Placement --> Clock Tree Synthesis --> Routing --> Sign OFF 
 ![image](https://user-images.githubusercontent.com/118953939/212274137-89230947-0306-4e81-987d-dd887d607aac.png)
  Source : Takens from lecture video.
  
 **Synthesis**
 - Purpose of synthesis is to convert RTL to a circuit out of component from the stadndar cell library(SCL)
 - The result of circuit is described in HDL or in gate level netlist.
 - Standard cells have regular layout and each cell has different views or model which is Electrical,HDL,SPICE and Layout (Abstract and Detailed)
 
 >![image](https://user-images.githubusercontent.com/118953939/212276687-de4befaa-9a3e-457e-9827-c811e5e8bdb8.png)

 **Floor and Power Planing**
   - The objective to plan the silicon area and create robust distribution to the power circuit.
   - Chip Floor-planning = partition the chip die between different system building blocks and place the I/O Pads.
   - Macro floor-planing : Dimensions,pin locations and rows definition.
   - Power Planning : The power is provided to the every macros,standard cells and all other cells are present in the design.Typically,the power distribution network        using upper metal layers sice they are thicker than lower metal layers.
  
  >![image](https://user-images.githubusercontent.com/118953939/212283483-036fb3f7-8eb5-44f0-84e1-3e98ef5fa8f4.png) 
  Source : Takens from lecture video.

  **Placement**
  - Place the cells on the floopplan rows,aligned with the sites.Should place closed to preven interdisconnted .
  - Usually done in 2 steps : Global and detailed.
      -Global : It aims to generate a rough placement solution that may flout some placement restrictions while maintaining a broad view of the entire netlist in the                   very first stage of placement, where cells are placed inside the core area for the first time while considering timing and congestion.
      -Detailed :The position obtained from global placements are minimally altered.
  
  >![image](https://user-images.githubusercontent.com/118953939/212284737-5b9ee148-7a7f-4217-8257-0f8277ad1ef3.png)
  Source : Takens from lecture video.
 
 **Clock Tree Synthesis (CTS)**
 
  -Create a clock distribution network 
    -To deliver the clock to all sequential elements (eg FF)
    -With minimum skew (zero is hard to achive)
    - And in a good shape.
    -Usually a tree (H,X,..)
  
  >![image](https://user-images.githubusercontent.com/118953939/212286257-cb528e70-0bc8-4a2f-9cdd-8ef6f19dba35.png)
   source :lecture's video
 
  **Routing**
  
 - The process of implementing the interconnect using the available metal layers.
 - Metals is tracks from a routing grid and this routing grid is huge.So,devide and conquere approach.
    - Global Routing :Generating routing guides 
    - Detailed Routing :Using routing guides to implement the actual wiring.
>![image](https://user-images.githubusercontent.com/118953939/212286543-ea5ea5c5-516a-48c7-a418-a818235bd70e.png)
   source :lecture's video
 
  **Sign Off** 
 
 Final layout 
 -Physical Verifications 
    - Design Rules Checking (DRC) -to maek sure the fnal layout follow all the design rules. 
    - Layout vs Schematic (LVS) - Ensuring the final layout matches the gate level netlist of th design 
 - Timing Verification
    - Static Timing Analysis (STA) -To make sure all the timing constraints are met and the circuit will run at designated clock frequencies.
  </details>

 
 <Details>
 <summary>Intorduction to OpenLANE  and Strive chipset</summary>
  
 **OpenLANE** 
 - Started as an Open_source flow for a True Open source Tape-out Experiment.
 - Strive is a family of open everything SoCs 
    -Open PDK,Open EDA,Open RTL
 
**Example of strive SoC family and its features**
| SoC  | Features |
| ------------- | ------------- |
| StriVe  | Sky130SCL + Synthesized 1 Kbytes SRAM |
| striVe 2 | Sky130 SCL + 1Kybtes OpenRAM block   |
|StriVe 2a | striVe 2 with a single chip core module|
|striVe 3| OSU SCL + Synthesized 1 Kbytes SRAM |
|striVe 5 | Sky130SCL + 8x1 Kbytes Open RAM banks|
|striVe | strive 2 with DFT |
 
>![image](https://user-images.githubusercontent.com/118953939/212358770-b274f615-572c-4323-8af2-b7ea0975ad6d.png)
 source :lecture's video
- strive 2 was identical with strive 1 but it used 1 kbytes Open Ram instead of SRAM 
- Strive 2  also similar with strive 2 except its have different  hierarchy
- strive 3 have same strive 1.
- strive 5 same as strive 2 but its using 8 x 1 open ram banks 
- strive 6 same as strive 2it use for design testing.
  
 **Main Goal**
 - Produce a clean GDSII with no human intervention (no human in the loop)
 -Tuned for skywater 130nm Open PDK 
   -also support XFAB180 and GF130G
 **Containerized** 
   - Functional out of the box.
   - Instructions to build and run natively will follow.
 - Can be used harden Macros and chips
 **Two modes of operation**
    - Autonomous or interactive
    - Autonomous push button flow will configure the flow and push button to wait for some time and wait the GDS
    - Interactive we can run command step by step.
 **Design Space Exploration** 
    - Find the best set of flow configurations.
 **Large number of design example**
    - 43 design with the best configuration 
  </details>
  
  <Details>
 <summary>Intorduction to OpenLANE  and ASIC design flow</summary>
  
**OpenLANE ASIC Flow**

>![image](https://user-images.githubusercontent.com/118953939/212359133-ccbb0fa4-de22-43eb-805f-ee24a4bce08a.png)
source :lecture's video
  
-From RTL to synthesis using yosys with the design constraints.This Yosys will translate the RTL into logic circuits component and optimized it and then mapped using abc.
  
-Synthesis Exploration = used to generate reports that shows how the design delay and area(can pick the best strategy base on this).Its also generate report design .

>![image](https://user-images.githubusercontent.com/118953939/212361936-789849f1-f538-4321-92a6-6fb0035eec1c.png)
source :lecture's video
  
- Opelane Regression Testing 
    - The design exploration uitlity is also used of rregression testing (CI)
    - We run OpenLane on ~70 desgn and compare the results to the best known ones.
>![image](https://user-images.githubusercontent.com/118953939/212361588-045c58e0-de7a-47f8-9339-c54d29eb9a41.png)
source :lecture's video
  
- DFT (optional) 
   - After sysnthesis process have been done,Design for testability or DFT is ready to be testing before fabrication usng open source priject which is fault.
   - Step included :
      - Scan Insertion 
      - Automatic Test Pattern Generation (ATPG)
      - Test patterns Compaction 
      - Fault Coverage 
      - Fault simulation
  
  >![image](https://user-images.githubusercontent.com/118953939/212362643-2936b505-1d6f-4283-8227-d3e56b122171.png)
  source :lecture's video
  
- Physical Impelementation
   - Called Automated place and rouce or PnR
   - Using OpenRoad Open source to perform the implementation.
   - Involves several steps including 
      - Floor/Power Planning
      - End Decoupling Capacitors and Tap cells insertion.
      - placement :Global and Detailed 
      - Post placement optimizations
      - Clock Tree Synthesis (CTS)
      - Routing : Global and detailed.
  - Logic Equivalence Check (LEC) 
    - every time netlist is modified,verification must be performaed 
      - CTS modifies the netlist 
      - Post placement optimizations modifed the netlist
    - LEC is used to formally confirm that the function did not change after modifying the netlist. 
  - Dealing with antenna Rules Violations 
    - A special step during pysical impementation is called antenna diodes insertion.
    - This step is required for antenna worst violations
    - When a metal wire segment is fabircated and it is long enough,it can acts as antenna.
      -Reactive ion etching causes cahrge to accumulate on the wire.
      - Transistor gates can be damaged during fabrication
    - Solution 
      - Bridging attaches a high layer intermediary(requires routes awareness)
      - Add antenna dioded cell toleak away chages (antenna diodes are provided by SCL)
      >![image](https://user-images.githubusercontent.com/118953939/212366305-dd1958ee-c206-47d7-858e-929c8a4cf238.png)
        source :lecture's video
      
      **Dealing with antenna rules violations** 
  
      - We took a preventive approach  
        - Add a fake antenna diode next to every cell input after placement 
        - Run the antenna checker (MAGIC) in the routed layout 
        - Ift he checker reports a violation on the cell input pin,replace fake diode cell by a real one.
      
       >![image](https://user-images.githubusercontent.com/118953939/212366895-e6a891c0-d232-421d-b11d-1738fdf70713.png)
         source :lecture's video
      
      **Static Timing Analysis**
   
         - RC Extraction: DEF2SPEF
         - STA: OpenSTA (OpenROAD)
  
      **Physical verification DRC and LVS
  
          - Magic is used for DRC and SPICE Extraction from Layout
          - Magic and Netgen are used for LVS where extracted SPICE by Magic vs. Verilog netlist
  </details>
  
  ### Get Familiar to open-source EDA tools
  
    
  <Details>
 <summary>OpenLANE Directory Structure in Details</summary>
  
>![image](https://user-images.githubusercontent.com/118953939/212477299-3c68965f-2033-491a-a514-ed37f07ac534.png)

>![image](https://user-images.githubusercontent.com/118953939/212477313-41338577-8e4c-4b25-9021-d03e00aa75ae.png)

</details>
  
  
  <Details>
 <summary>Design Preparation Step</summary>
 
  - Step to invoke OPEN LANE 
  ```
 1)make mount 
  
 2)./flow.tcl -interactive
  
 3)package require openLane 0.9
  
 >[Uploading image.png…]()
  ```
  - Design File 

 >![image](https://user-images.githubusercontent.com/118953939/212477521-622a611b-6e54-4e70-8cf0-5f986a3c2ab1.png)

 >![image](https://user-images.githubusercontent.com/118953939/212477571-18da216a-12f2-46ac-943b-048a2d7ddb15.png)

 >![image](https://user-images.githubusercontent.com/118953939/212477591-fcc788ac-c464-4193-a21b-37f7710c26fc.png)

  </details>
  
  
 <Details>
 <summary>Review files after design prep and run synthesis</summary>
  
  >![image](https://user-images.githubusercontent.com/118953939/212477625-6c17e78e-6738-49ae-8dab-0e838ca926e8.png)

  ```
  run_synthesis --> execute synthesis 
  ```
  >![image](https://user-images.githubusercontent.com/118953939/212477631-ebec86cd-a3b0-41d0-9965-a733f36ee369.png)

</details>
  
  
  
  <Details>
 <summary>OpenLANE Project Git Link Description</summary>
 
 ```
 More about OPEN LANE can read on this GitHub : https://github.com/efabless/OpenLane
 ``` 
>![image](https://user-images.githubusercontent.com/118953939/212477652-28d008bf-8fba-4010-8613-040fe6dc7f40.png)

  
 </details>
  
 <Details>
 <summary>Step to Charactize Synthesis Result</summary>
  
  >![image](https://user-images.githubusercontent.com/118953939/212477695-57335e78-d3a5-41c7-b3d5-e8873ed7ee36.png)

  >![image](https://user-images.githubusercontent.com/118953939/212477701-86f4be2d-7a4f-4d96-a265-6e612bf60a0b.png)

  >![image](https://user-images.githubusercontent.com/118953939/212477707-ffba286b-f772-4589-90c8-24de0dd48cbd.png)

  </details>
  
  ## Day 16
### Topic Good Floor plan vs bad floor plan and introduction to library cells

### Topic:Chip Floor Planing Consideration  
 <Details>
 <summary>Utilization factor and aspec ratio </summary>
 
>![image](https://user-images.githubusercontent.com/118953939/212715488-dbc350da-b9bb-432a-896f-a5661762323a.png)
  
>![image](https://user-images.githubusercontent.com/118953939/212715520-a1a1e8c8-5429-47f9-95e7-b2e1057aa15c.png)

  </details>
  
 <Details>
 <summary>Concept of pre place cells</summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/212715673-a4f79c96-da28-4b07-a407-35a9c9c9262a.png)
  
 >![image](https://user-images.githubusercontent.com/118953939/212715709-cdb45af0-cc18-443b-8f36-32ab818351a2.png)

   </details>
   
  <Details>
 <summary>Decoupling Capacitor</summary>
 
>![image](https://user-images.githubusercontent.com/118953939/212716686-35ca751e-1f9a-4c23-8fc4-b1593049ae96.png)
 
>![image](https://user-images.githubusercontent.com/118953939/212716728-e180e2bb-e53c-4372-9e44-d28fa85897d6.png)
 
>![image](https://user-images.githubusercontent.com/118953939/212716782-d2d9b84e-9a6c-4e8c-be99-c2d1f8f17512.png)

</details>
 
  <Details>
<summary>Power Planing </summary>
 
>![image](https://user-images.githubusercontent.com/118953939/212716314-e179e386-2d3d-4294-9867-4795b37939db.png)

>![image](https://user-images.githubusercontent.com/118953939/212716368-62b1c117-a447-4830-960a-e5bde5fab000.png)

  </details>
  
  <details>
<summary>Pin placement and logical cell placement blockage</summary>

 ![image](https://user-images.githubusercontent.com/118953939/213113500-53f1786a-8fe0-413a-9932-c06aed0ef0c9.png)

</details>

<details>
<summary>Steps to run floorplan using OpenLANE</summary>

>![image](https://user-images.githubusercontent.com/118953939/213113609-c3b4bc4f-090b-4e46-ae63-7867b8ad50e0.png)

>![image](https://user-images.githubusercontent.com/118953939/213113642-e54e1a83-e52f-4227-b1b8-a70c3530ff24.png)

>![image](https://user-images.githubusercontent.com/118953939/213113668-1bbf6e13-3653-4e87-bfa6-3c43624b3d28.png)

>![image](https://user-images.githubusercontent.com/118953939/213113698-5b27baf1-1c80-4fce-bd12-394551c8faa1.png)

</details>


<details>
<summary>Review floorplan files and steps to view floorplan</summary>

 >![image](https://user-images.githubusercontent.com/118953939/213113816-fb3fddc6-bdde-4586-b48e-176cbd2ea467.png)

>![image](https://user-images.githubusercontent.com/118953939/213113858-bc463924-89bb-4d74-bb0c-79b55d8bdd65.png)
 
</details>

###  Library Binding and Placement

<details>
<summary>Netlist binding and initial place design</summary>

 >![image](https://user-images.githubusercontent.com/118953939/213114145-3dd1549d-e527-4f82-949c-e8a333b0f252.png)

 >![image](https://user-images.githubusercontent.com/118953939/213114212-d2cced5a-16bd-4b77-b001-e366d96c8076.png)
 
 >![image](https://user-images.githubusercontent.com/118953939/213114356-cff8c02c-008a-47f7-85ce-5be1f32cabc8.png)

 </details>
 
 <details>
 <summary>Optimize placement using estimated wire-length,capacitance and final placement </summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/213114612-27568e06-bc7e-49b1-aaaa-3b0dd4a84a90.png)

</details>

<details>
<summary>Congestion aware placement using Replace</summary>

 >![image](https://user-images.githubusercontent.com/118953939/213116110-2fad588c-441a-4e4a-bd27-dc2153d05c06.png)


</details>

 

###  Cell design and characterization flows

<details>
<summary>Inputs for cell design flow</summary>

>![image](https://user-images.githubusercontent.com/118953939/213116181-3c28faf4-6ca3-4bac-a88a-f3a0dd032ce9.png)

>![image](https://user-images.githubusercontent.com/118953939/213116216-758b24cf-7a4d-4811-adb8-86fef9122895.png)

</details>

<details>
<summary>Circuit design step</summary>

 >![image](https://user-images.githubusercontent.com/118953939/213116328-7b2b2863-bb1e-404f-adaa-07088107a8ed.png)

 >![image](https://user-images.githubusercontent.com/118953939/213116373-546b875a-5bef-4ce3-98f9-b3360f024501.png)

 >![image](https://user-images.githubusercontent.com/118953939/213116550-c8e75b88-0782-486d-a6e4-506227d30a1d.png)

</details>

<details>
<summary>Layout design step</summary>

>![image](https://user-images.githubusercontent.com/118953939/213116614-63cb610f-3225-4038-b11c-f760d39d0875.png)

>![image](https://user-images.githubusercontent.com/118953939/213116639-d6e34c5f-baca-49be-94f9-e314492e0b95.png)

</details>


<details>
<summary>Typical characterization flow</summary>

>![image](https://user-images.githubusercontent.com/118953939/213116767-22bf1b4b-6eb8-49cf-947a-d0ec6e917818.png)

>![image](https://user-images.githubusercontent.com/118953939/213116812-f8b653ef-4f1b-40bc-9735-476c6a3f7aba.png)
</details>

 

###  General timing characterization parameters

<details>
<summary>Timing threshold definitions</summary>

>![image](https://user-images.githubusercontent.com/118953939/213116905-820f448e-e303-4045-a66a-69f3882f0c12.png)

>![image](https://user-images.githubusercontent.com/118953939/213117298-9916e46b-5709-4a1c-80f3-d2611edcdde3.png)
 
>![image](https://user-images.githubusercontent.com/118953939/213117362-50e59a68-0c4f-4c77-acd4-063c81a6743f.png)

>![image](https://user-images.githubusercontent.com/118953939/213117397-8fbf09c7-4a3b-4307-ae8a-ff1d5c480049.png)

</details>

<details>
<summary>Propagation delay and transition time</summary>

>![image](https://user-images.githubusercontent.com/118953939/213117434-b1050779-7c8d-4923-be58-c9dc992c11ac.png)

>![image](https://user-images.githubusercontent.com/118953939/213117465-43ceda4c-186b-4fe0-8854-f286eb0bee9a.png)

>![image](https://user-images.githubusercontent.com/118953939/213117529-7cc77f64-0568-4db8-90fc-6d3b36205a1b.png)

>![image](https://user-images.githubusercontent.com/118953939/213117576-646a08ed-6d0f-48cd-b0aa-5978e492886a.png)

</details>   
 


## Day 17  

### Topic : Design Library cell using Magic layout and Ngspice characterization 

### Topic - IO Placer Version 

<details>
 <summary>IO placer revision</summary> 

 >![image](https://user-images.githubusercontent.com/118953939/214262318-787972dc-0666-42cf-b853-c9918d637dd2.png)
 
 >![image](https://user-images.githubusercontent.com/118953939/214262403-8ecde286-249f-4cf3-afcd-0950231607fc.png)
</details>

<details>
 <summary>Spice Deck Creation for CMOS inverter </summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214262585-63367e5f-65b2-4f92-ad69-809b121b6151.png)

</details>

<details>
 <summary>Lab Spice simulation lab for CMOS inverter </summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214262852-0cbf5d43-56e5-45d5-ade2-17164d7246d7.png)

 >![image](https://user-images.githubusercontent.com/118953939/214262883-45cb71d9-f042-4916-99aa-6419e4a55c1a.png)

 >![image](https://user-images.githubusercontent.com/118953939/214262984-e437d2d5-7399-4415-93b2-1cded8d80a47.png)

 >![image](https://user-images.githubusercontent.com/118953939/214263016-89f25d82-7b58-45b7-b13e-be756841cd71.png)

 >![image](https://user-images.githubusercontent.com/118953939/214263057-732b6111-2e30-4a65-a027-db4eb2eb8a67.png)

 >![image](https://user-images.githubusercontent.com/118953939/214263083-68595c01-10c6-4b73-bdf3-f659eaa8de44.png)
</details>


<details>
 <summary>Switching Threshold Vm </summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214263337-8ffac728-96ac-47f0-9221-18968b25db39.png)

 >![image](https://user-images.githubusercontent.com/118953939/214263375-10a1ea9d-dcef-4239-b162-778bac6ed8be.png)
</details>

<details>
 <summary>Static and Dynamic Simulation of CMOS inverter</summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214263535-0d81365a-fb76-424a-87d4-28b5607a1b38.png)

 >![image](https://user-images.githubusercontent.com/118953939/214263611-4abafd5f-e722-4062-b67b-2e0afbd48f8e.png)

 >![image](https://user-images.githubusercontent.com/118953939/214263649-0785bfc5-feb1-47fa-beb5-964edaf4c707.png)
 
 >![image](https://user-images.githubusercontent.com/118953939/214263701-16dc380b-900c-4397-9c40-f291f574933c.png)
 </details>
 
 
<details>
 <summary>LAB STEPS TO GIT CLONE VSDSTDCELLDESIGN </summary> 

>![image](https://user-images.githubusercontent.com/118953939/214263928-6d3c392b-15b5-4e96-9249-defb5bbdec5b.png)
</details>

### Topic Inception of Layout and CMOS fabrication process

<details>
 <summary>Create Active Regions </summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214264150-8ae1a4ca-c611-4a02-b356-3825bb677fd4.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264216-105b3833-aab2-4bf2-a455-ccd21fa55787.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264259-a087576d-975c-4a1f-b82e-7c724bfa27a7.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264295-68753666-5f0a-495a-b681-e2ccfad29c51.png)
</details>

<details>
 <summary>Formation Nwell and P well </summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214264498-50b3df6c-06f5-40be-923f-7743eca93e0d.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264543-64ca628c-f6d8-4eec-8fe8-1cad71446200.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264579-4a09c795-c1dd-48cc-8c9f-25d0fcec0730.png)
 </details>
 
 <details>
 <summary>Formation of Gate Terminal </summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214264768-972850dc-c6d9-4d71-994b-9c25e9243084.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264789-6305065d-e376-4f3b-84e6-0fd93c0dc22c.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264825-7ef38297-7158-49ce-9873-dd447a7fc516.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264852-ae6eeab8-5790-4218-a250-e5fe38268ca4.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264879-2a7df07d-caa3-44b8-aa49-3e70f1728d79.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264910-239e9a0d-3f91-4ae7-81a3-84f05942665e.png)

 >![image](https://user-images.githubusercontent.com/118953939/214264997-c9653064-acf4-491b-b3f6-73ffd9b3b66d.png)

 >![image](https://user-images.githubusercontent.com/118953939/214265031-3ceef52f-39b9-4fa0-96c6-f607cd1b432b.png)

 >![image](https://user-images.githubusercontent.com/118953939/214265090-15ae1bad-6d7c-4897-bdb6-8a08b5915e9e.png)
</details>

 <details>
 <summary>Source and Drain Formation</summary>

 >![image](https://user-images.githubusercontent.com/118953939/214265329-ef10dd5f-442d-4679-9d20-69ccfc8dc702.png)

 >![image](https://user-images.githubusercontent.com/118953939/214265356-88c45036-a50c-4676-b11e-31d55bb2c9eb.png)
</details>

<details>
 <summary>Local Interconnection Formation</summary>

 >![image](https://user-images.githubusercontent.com/118953939/214265649-6b701c59-1d74-430b-8be9-3e630cef6c81.png)

 >![image](https://user-images.githubusercontent.com/118953939/214265717-1b880c2c-9623-4ea3-a68b-8bcf60c88fe1.png)

 >![image](https://user-images.githubusercontent.com/118953939/214265751-261610da-e92e-455c-a0dc-efefd4b6e357.png)
 </details>
 
 <details>
 <summary>High Level Metal Formation</summary>

 >![image](https://user-images.githubusercontent.com/118953939/214265908-d4634718-3839-4e10-925f-ec495383d6e1.png)

 >![image](https://user-images.githubusercontent.com/118953939/214265954-3b662c08-cce1-438a-89a9-36a8a05fd3d8.png)

 >![image](https://user-images.githubusercontent.com/118953939/214266026-9dfc7a45-e6e6-430c-8584-4fce032ad959.png)

 >![image](https://user-images.githubusercontent.com/118953939/214266076-d800d2b5-2df4-4ffe-a13d-64bf43858564.png)

 >![image](https://user-images.githubusercontent.com/118953939/214266096-bbef8c71-d171-41f6-9068-adc62d9ebcfd.png)
</details>


 <details>
 <summary>Lab introduction to sky130 basic layers layout and LEF using inverter </summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/214266371-366ba8c8-6f1d-4fdb-a825-deee8cdd35b7.png)
 
 >![image](https://user-images.githubusercontent.com/118953939/214266394-8be659a8-050e-4233-90e3-fb957f7ea7c2.png)
 
 >![image](https://user-images.githubusercontent.com/118953939/214266419-e3766e0b-071b-4feb-9993-5e274efaabe7.png)
 
- Different between the layout and the lef.More detail on https://github.com/nickson-jose/vsdstdcelldesign#introduction-to-lef

>![image](https://user-images.githubusercontent.com/118953939/214266464-01233343-873b-4ca9-8e5d-913ce4225a19.png)
</details>

 <details>
 <summary>Lab steps to create std cell layout and extract spice netlist.</summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/214266750-d3adcc42-ac26-4c5e-9da3-1e82401b42de.png)

 >![image](https://user-images.githubusercontent.com/118953939/214266795-983387bb-c873-4d41-ba71-9c427d9dbdba.png)
</details>

### Topic SKY130 Tech File Labs 
<details>
 <summary>Steps to create final SPICE deck using Sky130 tech </summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/214267229-522ec585-83b6-4cd8-a34c-f5456df7190b.png)

 >![image](https://user-images.githubusercontent.com/118953939/214267267-8f575911-1b84-40c8-80bc-1ba44eeceb1c.png)

 >![image](https://user-images.githubusercontent.com/118953939/214267308-7aa19286-eae3-4080-900f-2d4221610d0b.png)

 >![image](https://user-images.githubusercontent.com/118953939/214267344-87fca278-fe36-4085-a484-0e39f6f2e1d3.png)

 >![image](https://user-images.githubusercontent.com/118953939/214267386-ad8e5223-8ad3-4397-bf90-f4bf65e37d5d.png)
</details>

<details>
 <summary>Lab Introduction to Magic Tool Option and DRC Rules</summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/214267636-691e02bc-3e18-4f14-ba8b-9cc910904bd1.png)

 - Refference  http://opencircuitdesign.com/magic/
</details>

<details>
 <summary>Lab introduction to sky130 pdk’s and steps to download labs</summary>
 
>![image](https://user-images.githubusercontent.com/118953939/214268146-550f8203-6ecf-478e-8e3a-cb346ac2dcb5.png)
</details>


<details>
 <summary>Lab introduction to Magic and steps to load Sky130 tech-rules</summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/214268363-70de186c-c464-45be-86b9-588e25d7090e.png)

 >![image](https://user-images.githubusercontent.com/118953939/214268403-7bb512b0-d317-4eff-bd7f-189587efefc6.png)

 >![image](https://user-images.githubusercontent.com/118953939/214268439-66e9be92-fbe3-4e24-a163-86d416bf0291.png)

 </details>
 
 <details>
 <summary>Lab exercise to fix poly.9 error in Sky130.tech-file</summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/214268644-56691e76-efb4-41f8-a861-51b3189c474c.png)

 >![image](https://user-images.githubusercontent.com/118953939/214268671-35c078c5-2095-4439-94b4-17aedb5a00cb.png)
</details>

 <details>
 <summary>Lab challenge exercise to describe DRC error as geometrical construct</summary>
 
>![image](https://user-images.githubusercontent.com/118953939/214268967-3fefc634-5882-4bf0-a7e8-b40548427701.png)

>![image](https://user-images.githubusercontent.com/118953939/214269036-fe0be159-c7a2-4076-aeca-2359197de54c.png)
 </details>
 
  <details>
 <summary>Lab challenge to find missing or incorrect rules and fix them</summary>

 >![image](https://user-images.githubusercontent.com/118953939/214269236-bde9c4bf-3e5c-442b-8218-44700b3f7e08.png)

</details>


## Day 18  

### Topic :  Pre-layout timing analysis and importance of good clock tree


<details>
 <summary> Timing modelling using delay tables: Lab steps to convert grid info to track info</summary> 

 >![image](https://user-images.githubusercontent.com/118953939/214892847-1a9fa6f0-4edf-48a3-8b74-57dc0395b3e3.png)

 >![image](https://user-images.githubusercontent.com/118953939/214892925-8855e92d-8814-4649-8e41-d4042fe07ac3.png)

</details>

<details>
 <summary>Steps to convert magic layout to std cell</summary> 
 
>![image](https://user-images.githubusercontent.com/118953939/214893275-bc941b8b-036b-479a-abe5-65228dfa3dc6.png)

>![image](https://user-images.githubusercontent.com/118953939/214893414-c11a4a9a-f5b3-4156-830c-899a6b376ff0.png)

>![image](https://user-images.githubusercontent.com/118953939/214893469-74a4de9f-c42a-414e-b584-c6b691f000c0.png)

</details>

<details>
 <summary>Introduction to Timing libs and step to  include new cells in synthesis</summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214893683-c38750a4-fe55-4662-856c-4dd639f1f443.png)
 
 >![image](https://user-images.githubusercontent.com/118953939/214893780-4853217d-293a-4fee-b875-a28bf86e25a7.png)

 >![image](https://user-images.githubusercontent.com/118953939/214893860-2ce56709-dc9b-49ba-b126-1a16fcc66a73.png)

</details>


<details>
 <summary>Introduction to delay tables</summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214894268-f072ace1-f216-4d64-b98f-622705a1de41.png)

</details>

<details>
 <summary>Delay table usage part 1 and part 2</summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214894801-ac9b5419-e45c-4f0d-b65c-197dd1e62e66.png)

 >![image](https://user-images.githubusercontent.com/118953939/214894868-9a01ad0e-6eb7-4559-8f09-51a263f580fb.png)

 </details>
 
 
<details>
 <summary> Lab steps to configure synthesis settings to fix slack and include vsdinv</summary> 

 >![image](https://user-images.githubusercontent.com/118953939/214895259-67b3a3a1-9b0e-4c60-b6a1-0f55c1e8eb19.png)

 >![image](https://user-images.githubusercontent.com/118953939/214895310-2cd250fc-612e-4867-af6c-bfea02b04997.png)

 >![image](https://user-images.githubusercontent.com/118953939/214895357-d331608f-4f60-44f7-96f4-056f3680b5e1.png)

</details>

### Topic Timing analysis with ideal clocks using open STA.


<details>
 <summary>Setup timing analysis and introduction to flip-flop setup time</summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214895534-db6615b3-1592-4c6d-8d75-9e6d33d71eb0.png)
 
</details>

<details>
 <summary>Introduction to Clock Jitter and Uncertainty  </summary> 

 >![image](https://user-images.githubusercontent.com/118953939/214895702-e2f8d7f3-fdc6-403b-ba63-fe2de04acdf5.png)

 </details>
 
 <details>
 <summary>Lab steps to configure OpenSTA for post-synth timing analysis</summary> 
 
 >![image](https://user-images.githubusercontent.com/118953939/214895910-37d2e7a7-d058-4032-8129-ea647bc63b53.png)

 >![image](https://user-images.githubusercontent.com/118953939/214895965-d60750da-779a-4b00-8ccb-0f1d35584de8.png)

</details>

 <details>
 <summary>Lab steps to optimize synthesis to reduce setup violations</summary>

>![image](https://user-images.githubusercontent.com/118953939/214896099-400c11b0-5779-482f-a9f6-90f5fd4d8f2a.png)

>![image](https://user-images.githubusercontent.com/118953939/214896164-c1fe21f5-7d76-4dd0-9e2f-84faf67ff2c4.png)

</details>

<details>
 <summary>Perform basic timing ECO </summary>

Ways to improve timing :

1)Increasing drive strength of the cell while at the sacrifice of size.

 2)Using cell replace 
  
  -->Replace_cell <lib cell>
  
  -->Report_check –from <oldcell>  -through <newcell>

 </details>
 
 ### TOPIC Clock tree synthesis Triton CTS and Signal Intergrity 

 <details>
 <summary>Clock tree routing and buffering using H-Tree algorithm</summary>
  
 >![image](https://user-images.githubusercontent.com/118953939/214901322-e6a59c68-b0e1-4be6-bc7f-37a984406943.png)


</details>

 
 <details>
<summary>Crosstalk and clock net shielding</summary>
 
  >![image](https://user-images.githubusercontent.com/118953939/214901374-8388ae77-e369-4576-acba-5fabaf3d6a34.png)

  
</details>
 
 <details>
 <summary>Steps to run CTS using Triton CTS</summary>
  
 >![image](https://user-images.githubusercontent.com/118953939/214897204-4d2312cf-a643-4867-9202-b62c34208a22.png)

</details>

 <details>
 <summary>Steps to verify CTS runs</summary>
 
 >![image](https://user-images.githubusercontent.com/118953939/214897376-7dad467a-4368-4c99-9311-8f8588775734.png)

 >![image](https://user-images.githubusercontent.com/118953939/214897579-da264d92-c99b-4f27-b990-09f8dde14a92.png)


</details>

### TOPIC:Timing Analysis with real clocks using openSTA 
<details>
 <summary>Step Timing Analysis using real clocks </summary>

>![image](https://user-images.githubusercontent.com/118953939/215038954-7c79cb98-7164-4676-bf46-bb856cfdfba1.png)

>![image](https://user-images.githubusercontent.com/118953939/215038997-28d344a0-ebfe-4bba-8a33-fc5c945bca7d.png)

</details>

<details>
 <summary>Hold timing analysis using real clocks </summary>

>![image](https://user-images.githubusercontent.com/118953939/215039153-3fdc1de7-6084-4a1b-a3d8-f6b799986561.png)

</details>

<details>
 <summary>Lab steps to analyze timing with real clocks using OpenSTA</summary>
>![image](https://user-images.githubusercontent.com/118953939/215039310-4ea1bdbe-e301-402b-ae03-6e8588d74dff.png)

>![image](https://user-images.githubusercontent.com/118953939/215039343-2c75ce45-2efb-4296-ad01-edc8e0743a8d.png)
</details>

<details>
 <summary>Steps to execute OpenSTA with right timing libraries and CTS assignment</summary>
> ![image](https://user-images.githubusercontent.com/118953939/215039606-cc460b88-04c4-4c92-869b-c6300d8eb5b8.png)

>![image](https://user-images.githubusercontent.com/118953939/215039657-68d01530-ecd4-426b-8cfe-a630fa1a48ef.png)
</details>

<details>
 <summary>Steps to observe impact of bigger CTS buffers on setup and hold timing</summary>

>![image](https://user-images.githubusercontent.com/118953939/215044376-d2530238-922d-4953-9fb4-53a88f837c45.png)

</details>


## Day 19 
	
###  Topic :Final steps for RTL2GDS using tritonroute and open STA

###  Topic Routing And design rule check 

	
<details>
<summary>Introduction to Maze Routing Lee’s algorithm</summary>

>![image](https://user-images.githubusercontent.com/118953939/215142083-ed61fbf5-eac9-4dd1-bf66-b9c287f04e19.png)


content
</details>
	
<details>
<summary>Lee’s Algorithm conclusion</summary>

  >![image](https://user-images.githubusercontent.com/118953939/215142183-36b5cc2d-6a2f-4685-a044-2a4574870658.png)

  
</details>
	
<details>
<summary>Design Rule Check</summary>

>![image](https://user-images.githubusercontent.com/118953939/215142360-ea7e4de0-c8e1-4f77-9eac-4855378c29bf.png)

>![image](https://user-images.githubusercontent.com/118953939/215142400-a694eca0-54b6-44d3-8e1b-26d3b0b1b83a.png)


</details>

###  Topic Power Distribution Network and routing

<details>
<summary>Lab steps to build power distribution network</summary>

  >![image](https://user-images.githubusercontent.com/118953939/215142515-2edfeff9-428e-4986-a6c1-25a731891080.png)
 
  >![image](https://user-images.githubusercontent.com/118953939/215142559-c39da50e-8202-4a2b-a8c5-a19459a50d79.png)

</details>
	
<details>
<summary>Lab steps from power straps to std cell power</summary>

  >![image](https://user-images.githubusercontent.com/118953939/215142689-5341c587-41a1-4407-bfe6-efe9f0e95744.png)

</details>
	
<details>
<summary>Basics of global and detail routing and configure TritonRoute</summary>

>![image](https://user-images.githubusercontent.com/118953939/215142760-a8258da7-be8f-4afc-bd51-560277602b23.png)

</details>


### Topic TritonRoute Features
	
<details>
<summary>TritonRoute feature 1 - Honors pre-processed route guides</summary>

>![image](https://user-images.githubusercontent.com/118953939/215142880-60f9288d-6997-4eac-9ba3-b6d6a2ba8cce.png)
</details>
	
<details>
<summary>TritonRoute Feature2 & 3 - Inter-guide connectivity and intra- & inter-layer routing</summary>

>![image](https://user-images.githubusercontent.com/118953939/215142946-51cbffd7-0ac0-4de6-b62c-8253ceb27dda.png)


</details>
	
<details>
<summary>TritonRoute method to handle connectivity</summary>

 >![image](https://user-images.githubusercontent.com/118953939/215143038-9ce5d9b7-8f6f-4dbf-9b87-61d62170d00d.png)

</details>

<details>
<summary>Routing topology algorithm and final files list post-route</summary>

>![image](https://user-images.githubusercontent.com/118953939/215143126-705d8e4b-d92c-44b9-aa77-5dfc85a88843.png)

>![image](https://user-images.githubusercontent.com/118953939/215143182-91537cd6-2844-407a-b159-90408f5de0af.png)

>![image](https://user-images.githubusercontent.com/118953939/215143236-562c3a59-ff4e-4e61-ab66-2baa50b3b7a1.png)

</details>


## Day 20 
  
### Topic - Physical Design flow 


<details>

<summary>Physical Design Flow</summary>

- process of converting synthesized netlist design restriction and standard library to a layout as per the design rules provided by the foundary. The layout is sent to  the foundary for the chip creation.
- step  
(i)   Partitioning = devides a circuit into smaller sub-circuits or modules, each of which can be constructed and examined separately.

(ii)  Chip-planning = consists of floorplanning and power planning process.

(iii) Placement = determines the dimensions of all the blocks and place them in appropriate spots on the chip. 

(iv)  Clock Tree Synthesis = establishes how the clock signal is buffered, gated and routed to fulfil specified skew and latency criteria.

(v)   Signal Routing = signal/global routing which allocates routing resources that are used for connections. Within the global routing resources, detailed routing assigns routes to individual metal layers and routing tracks.

(vi)  Timing closure = unique placement or routing strategies to improve circuit performance.

>![image](https://user-images.githubusercontent.com/118953939/217484529-e9f7b79a-cc90-42b5-affc-9b2be5c20e9b.png)

>![image](https://user-images.githubusercontent.com/118953939/217485087-5d8e653e-d78f-4fa0-9874-0f7c6cd1490e.png)

</details>

	

<details>

<summary>Lab 20 </summary>

*PHYSICAL DESIGN*

```
git clone https://github.com/manili/VSDBabySoC.git
git clone https://github.com/Devipriya1921/VSDBabySoC_ICC2.git
git clone https://github.com/bharath19-gs/synopsys_ICC2flow_130nm.git
git clone https://github.com/kunalg123/icc2_workshop_collaterals.git
git clone https://github.com/google/skywater-pdk-libs-sky130_fd_sc_hd.git
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```
- source  vsdbabysoc.tcl 
>![image](https://user-images.githubusercontent.com/118953939/217485295-ba9b6170-23ab-4a54-9c32-771d4286c187.png)

>![image](https://user-images.githubusercontent.com/118953939/217485369-929843ab-a0fb-4b79-86d7-833852c9d607.png)

>![image](https://user-images.githubusercontent.com/118953939/217485406-5a9c6561-12e4-4727-a49a-81a9a2f327ad.png)

>![image](https://user-images.githubusercontent.com/118953939/217485535-88ac8610-1ea0-4141-b12a-b6d6ff39672a.png)

![image](https://user-images.githubusercontent.com/118953939/217485584-404aac0e-912e-4b12-806c-aa3182f7a01e.png)

- source Top.tcl 

>![image](https://user-images.githubusercontent.com/118953939/217486259-6ae52c1b-c822-42d9-bb1a-e92ee2b17938.png)

>![image](https://user-images.githubusercontent.com/118953939/217486360-d94809f3-b99a-44be-99b0-94ee31fb891b.png)

>![image](https://user-images.githubusercontent.com/118953939/217486439-21aa1ebc-02cc-4a7c-9e2c-6cbb22bdb329.png)

>![image](https://user-images.githubusercontent.com/118953939/217486498-27ddb867-6dcb-43d3-a0e9-ee2e641ef9a2.png)

>![image](https://user-images.githubusercontent.com/118953939/217486581-e194a681-6d61-4c87-861d-cf5e0e21359d.png)

>![image](https://user-images.githubusercontent.com/118953939/217487687-90bf85c7-0b06-4b71-adf7-d55ccd0bf6d2.png)

>![image](https://user-images.githubusercontent.com/118953939/217487748-ae37f2cd-9356-454e-85a7-45ffa1e2c3f4.png)

>![image](https://user-images.githubusercontent.com/118953939/217487804-ce0db6c8-abd8-4c05-8000-edaeb929d7f4.png)

>![image](https://user-images.githubusercontent.com/118953939/217487870-9f8e1c0e-38b5-457d-ba67-86c77660554a.png)

>![image](https://user-images.githubusercontent.com/118953939/217487938-477d5647-8d04-445b-aa93-18358fdbb225.png)

>![image](https://user-images.githubusercontent.com/118953939/217488053-d49345be-1b05-4e6e-9a5e-9f038d29bf8d.png)

>![image](https://user-images.githubusercontent.com/118953939/217488102-c6d4f420-353c-4dc1-91a4-e59a0ffad384.png)

>![image](https://user-images.githubusercontent.com/118953939/217487988-5b0974c0-458e-4ab7-9192-73d4c79b160d.png)

>![image](https://user-images.githubusercontent.com/118953939/217488156-7a831346-7fbe-4361-8c4d-d28f2effbb27.png)

>![image](https://user-images.githubusercontent.com/118953939/217488215-33f274a5-f390-49c8-8bae-60162f295bab.png)
	
**Core utilization change to 0.4%**

>![image](https://user-images.githubusercontent.com/118953939/218671583-9664cba1-7147-437d-80fc-352a3aa0894b.png)

>![image](https://user-images.githubusercontent.com/118953939/218671658-393ecad8-a078-4d9a-b06b-3127ba2331ce.png)

>![image](https://user-images.githubusercontent.com/118953939/218671697-0d6ecbd4-6d30-42f7-8dfd-a4f193f0b351.png)

</details>


## Day 21
  
### Topic - Placement and Route  

<details>
<summary>Core utilization change to 0.4%</summary>

- Core Utilization (Cu): It indicates the amount of core area used for cell placement.
- The core Utilization was changes from 0.07 to 0.4 and we can see from the final result the size of DAC was bigger than before.
	
>![image](https://user-images.githubusercontent.com/118953939/218671583-9664cba1-7147-437d-80fc-352a3aa0894b.png)

>![image](https://user-images.githubusercontent.com/118953939/218671658-393ecad8-a078-4d9a-b06b-3127ba2331ce.png)

>![image](https://user-images.githubusercontent.com/118953939/218671697-0d6ecbd4-6d30-42f7-8dfd-a4f193f0b351.png)

</details>

<details>

<summary>Placement </summary>
	
**PLACEMENT**
	
- Placement is the process of determining the locations of circuit devices on a die surface. It is an important stage in the VLSI design flow, because it affects routability, performance, heat distribution, and to a less extent, power consumption of a
design. 
	
- step  
	
1. Global placement. Global placement aims at generating a rough placement solution that may violate some placement constraints (e.g., there may be overlaps among modules) while maintaining a global view of
the whole netlist.
2. Legalization. Legalization makes the rough solution from global placement legal (i.e., no placement constraint violation) by moving modules around locally.
3. Detailed placement. Detailed placement further improves the legalized placement solution in an iterative manner by rearranging a small group of modules in a local region while keeping all other modules fixed.


**CTS**

- Clock Tree Synthesis (CTS) is the process of inserting buffers/inverters along the clock paths of the ASIC design to balance the clock delay to all clock inputs. So in order to balance the skew and minimize insertion delay CTS is performed

- Check list Before CTS 

	1)Placement – Completed

	2)power ground nets – Prerouted

	3)Estimated Congestion – acceptable 

	4)Estimated Timing – acceptable (~ 0 ns slack)

	5)Estimated Max Tran/Cap – No violations

	6)High Fanout Nets
	
- Inputs required for CTS:

	1)Detailed Placement Database

	2)Target for latency and skew if specified

	3)Buffers or Inverters for building the clock tree

	4)Clock Tree DRC (Max Tran, Max Cap, Max fanout, Max no of buffer levels)

- Output of CTS:

	1)Database with properly build clock tree in the design

- Checklist after CTS:

	1)Skew Report

	2)Clock Tree Report

	3)Timing Reports for setup and hold

	4)Power and Area Report

</details>

	

<details>

<summary>Lab 21 </summary>


>![image](https://user-images.githubusercontent.com/118953939/218029209-7f232a28-a274-46f6-9ea7-bb8f5a7083d9.png)

>![image](https://user-images.githubusercontent.com/118953939/218029300-60e3ea40-a1ec-4692-a23e-51d53b1d92d9.png)

>![image](https://user-images.githubusercontent.com/118953939/218029339-1e0f32e8-af43-4e89-a805-6086a95793db.png)

>![image](https://user-images.githubusercontent.com/118953939/218029395-a27116bd-5aba-46dd-a2de-4749f1b7280c.png)

>![image](https://user-images.githubusercontent.com/118953939/218029443-ff6d8ea2-7e65-4981-924f-bd7f2928f58b.png)

>![image](https://user-images.githubusercontent.com/118953939/218029560-bb0199f2-e987-44b6-a0e2-40b2ad2028e8.png)


</details>


## Day 22
  
### Topic - Analysis labs  
<details>	
<summary>Theory and Lab </summary>

**What is CTS?**
It is a technique for distributing the clock equally among all sequential parts of a VLSI design

**What happens when we distribute the clockequally?**
Balancing the delays to all clock input pins

**What is the goal of CTS?**
The goal of clock tree synthesis (CTS) is to minimize skew and insertion delay.

**H-tree algorithm**

1.Find out all the flops present

2.Find out the center of all the flops

3.Trace clock port ot the center point

4.Now divide the core into two parts, trace both the parts and reach to each center.

5.Then form this center again divide the area into two and again trace till center at both the end6.Repeat this algo till the time we reach the flop clock pin.

![image](https://user-images.githubusercontent.com/118953939/218038539-08b01921-9042-422a-994c-565706a10b7f.png)

**Various CTS checks**

1.Skew check

2.Pulse  width check

3.Duty cycle check

4.Latency check

5.Power check

6.Crosstalk Quality check

7.Delta Delay Quality check

8.Glitch Quality check

```
Check Legality = to check if the placement done input is perfect 
set_clock_tree_options = to edit those default constraints
set cts_use_debug_mode true = to debug mode
compile_clock_tree = to compile all the constraints.
report_clock_timing -type -summary/-skew = Reports actual, relevant skew, latency, interclock latency etc. for paths that are related. 
Clock_opt = which performs clock tree synthesis and incremental physical optimization. 
	1. Performs clock tree power optimization 
	2. Synthesizes(Re-Synthesizes) the clock trees
	3.Optimizes the clock trees
	4.Adjusts the I/O timing
	5.Performs RC extraction of the clock nets and computes accurate clock arrival times
	6.Performs placement and timing optimization
```
>![image](https://user-images.githubusercontent.com/118953939/218044378-994b3ecf-f505-481a-b741-8cf224cf438d.png)

>![image](https://user-images.githubusercontent.com/118953939/218044450-96693895-8a80-4d07-aea6-e5e01fdb8958.png)

>![image](https://user-images.githubusercontent.com/118953939/218044509-66f37f59-5b4f-49c0-96e5-f577e8d82dc7.png)

>![image](https://user-images.githubusercontent.com/118953939/218044549-5cf6eca9-2485-4eaa-8dc2-deab17a9cce3.png)

>![image](https://user-images.githubusercontent.com/118953939/218044593-1abe0d8c-0b5e-4093-9c6d-49458d0d7d9c.png)
</details>


## Day 23
  
### Topic - Clock Gating Technique 
<details>	
<summary>Clock Gating Techniques</summary>

Generally, there are two different techniques of implementing clock gating.

- Intent based Clock gating – This type of clock gating is introduced into the design as part of functionality through RTL.

- Tool generated clock gating – This type of clock gating is introduced by tools during synthesis by identifying all the Flip Flops sharing same control logic and enabling all those FFs when needed.

- There is a digital circuit with a lot of clocks, now just imagine designing clock tree, which will be so huge, with so many buffers etc.

- The whole chip is sectioned into smaller versions and then each section will have its own clock tree, and then finally a complete routed tree.

>![image](https://user-images.githubusercontent.com/118953939/218403880-b3c99d24-cc65-47fd-a107-fb8ed84c2b07.png)

**Clock Gating technique using AND,OR Universal NAND gate**

- It has been found that 50% of the dynamic power originates from clock-related circuits. - source: low power vlsi design, AJIT PAL(this answers why CG?)

![image](https://user-images.githubusercontent.com/118953939/218405572-b372314d-f71e-4414-b845-3a72ba3e9339.png)

**Where/When is clock gating done ?**
Inserted synthesis stage and optimized in the implementation stage(Physical Design stage).

3 Types of Routing 
```
1)P/G routing 
2)clock routing 
3)signal routing 
	
```
>![image](https://user-images.githubusercontent.com/118953939/218407492-808f32d7-3d8a-45c1-aceb-271d918e1a80.png)

</details>
	
<details>	
<summary>Lab </summary>

Clock Routing 
```
place_opt is used to place and optimize the current design

clock_opt is used to synthesize and route the clocks, and then further optimize the design based on the propagated clock latencies

route_auto is used to run global routing, trace assignment, and detailed routing at once/automatically
```
>![image](https://user-images.githubusercontent.com/118953939/218408320-5b1abdc8-6e13-456e-9cdb-e89924dd67d1.png)

>![image](https://user-images.githubusercontent.com/118953939/218409226-2cd60df2-5ea4-4673-9ec1-05d3429f701e.png)

</details>
	
## Day 24
  
### Topic - ECO Timing 
<details>	
<summary>ECO Timing </summary>

**What is ECO ?**
Engineering Change Order or ECO is how you incorporate last minute changes in your design. So typically we do ECO on the gate level netlist. Designer need to edit the gate-level netlist, make the same changes in RTL. Then pass all verifications before it is passed on to layout. Make sure the ECO pass formal and functional verification before you start editing your layout.

**ECO strategies in a nutshell**

1.Investigate the problem using the recent database

2.ECO generation to address the problem

3.ECO implementation with the recent database

4.After implementing and fixing the problem, save it in the database for future.

**How to Improve Timing ?**

- Upsizing the size to improve the timing.
- So if the sizing  increase the delay will be reduce .  
	
>![image](https://user-images.githubusercontent.com/118953939/218633057-02c0e252-4f21-4361-af3d-7f8d59cdc1a6.png)

>![image](https://user-images.githubusercontent.com/118953939/218633094-0d987d13-9839-46cb-a6cf-16015633552b.png)

```
- size_cell core/U6 sky130_fd_sc_hd__nand2_4
- size_cell core/U546 sky130_fd_sc_hd__a22o_4
- size_cell core/U561 sky130_fd_sc_hd__a21oi_4
- size_cell core/U207 sky130_fd_sc_hd__inv_4
- size_cell core/U67 sky130_fd_sc_hd__nand2_8
- size_cell core/U579 sky130_fd_sc_hd__a21oi_4
- report_timing -from  core/CPU_is_add_a3_reg  -to core/CPU_Xreg_value_a4_reg[24][31]
```
>![image](https://user-images.githubusercontent.com/118953939/218668099-5eb4e1bf-f521-4a9c-ae79-187e54ac0c64.png)

>![image](https://user-images.githubusercontent.com/118953939/218697964-8a2e867e-64f3-4141-9403-c944cccaa16f.png)

>![image](https://user-images.githubusercontent.com/118953939/218697996-132993f2-1ac2-48bf-bfca-33c2b947021c.png)
	
>![image](https://user-images.githubusercontent.com/118953939/218705666-fdefb161-54c5-4cfc-a194-9ddfbbb02b7f.png)

>![image](https://user-images.githubusercontent.com/118953939/218698061-5ef23f62-4289-42df-bfba-73aa14a9fbaa.png)

</details>

## Day 25
  
### Topic - RISC-v core RTL2GDS flow 
<details>	
<summary>Theory </summary>
Covered in previous topic 
</details>



## Day 26
  
### Topic - Introduction to mixed signal 
<details>	
<summary>Theory </summary>

**What is Mixed Signal?**

Mixed-signal ICs are integrated circuits that contain both analog and digital circuitry on one chip. An analog signal is a continuous time-varying signal, and a digital signal is a noncontinuous signal that takes on only a finite number of values

**Analog mixed signal flow**
>![image](https://user-images.githubusercontent.com/118953939/219291389-bacfd1b5-870d-46e9-9471-8303c309e2fe.png)
>![image](https://user-images.githubusercontent.com/118953939/219292443-43522d48-0ec8-456b-a3f7-18559935b1eb.png)

*source : https://www.vlsisystemdesign.com/*

**Explore the example of VSDBabySoc**
1)RVMYTH processor : digital block
2)PLL analog block
3)DAC - analog block(for digital to analog conversion)

**Introduction to various file**

1)Library Exchange Format (LEF) :  representation of the abstract of the standard cells. LEF file contains all the physical information of the cells (Technology and Macro cells) and nets.Physical properties such as width and height.

2)LIBerty file :representation of timing and power parameter associated with cells inside the standard cell library of a particular technology node.

3)GDS ( Graphical Design System or Graphical Data System) :Binary file used in VLSI Design to represent the IC layout

4)Open Artwork System Interchange Standard (OASIS) :Binary file format used by computers to represent and express an electronic pattern for an integrated circuit during its design.

5)What the different between GDS and OASIS : OASIS data represents numerical values with variable byte lengths, whereas the GDS format uses fixed byte lengths.

>![image](https://user-images.githubusercontent.com/118953939/219294310-ac4cc75d-3a6c-4222-90eb-37ccdb58017e.png)

*Source : https://teamvlsi.com/2020/08/inputs-for-physical-design-physical-design-input-files.html*

**What is PnR**
placing the cells and connecting them to meet the design power, performance, and area (PPA) goals.
	
>![image](https://user-images.githubusercontent.com/118953939/219295159-0fe31e4a-e844-4035-9f53-390de28678f4.png)

**Discovering are IP cores**
- An IP core consists of a block of logic or data that is used in a semiconductor chip.
- There are two type of IP cores 
	1) Hard IP cores : can be customized during the physical design phase and mapped to any process technology.
	2) Soft IP cores : That has the logic implementation and the physical implementation.the physicallayout of a hard macro-IP is finished and fixed in a 	particular process technology.
	
*Source :https://www.slideshare.net/vlsisyst/vlsi-physical-design-flow*

</details>



## Day 27
  
### Topic - Crosstalk 
<details>	
<summary>Introduction to crosstalk </summary>

**What is Signal Intergrity and Crosstalk ?**
- Signal integrity and crosstalk are the quality checks of the clock routes.
- Signal intgrity is the baility of an electrical signal to carry information reliably and resist the effects of high frequency electromagnetic interference from nearby signals.
- Crosstalk is the undesirable electrical interaction between two or more physically adjacent nets due to capacitave cross-coupling.
- Crosstalk is a type of noise that corrupts the actual signal while transimission through the communication medium.

**Aggressor and Victim  nets**
- A net that receives undersirable cross-coupling effects from a nearby net is called a victim net.
- A net that causes these effects in a victim net is called an aggressor net.

**Crosstalk-Glitch**
- When one net is switching and another net is constant then switching signal may cause spikes on other net because of which coupling capacitance (Cc) occurs between two nets,this is called as crosstalk noise.
- Type of glitches --> Rise,Fall,Overshoot,Undershoot 
>![image](https://user-images.githubusercontent.com/118953939/220120136-773d3b9b-a063-430a-ad51-d51162fea36e.png) 

*source : https://www.vlsisystemdesign.com/*

**Performing crosstalk delay analysis**
- Enable PrimeTime SI --> set_app_varsi_enable_analysis true
- Back-annotate the design with ross -coupling capacitance information in a SPEFor GPD file
	- read_parasitics-keep_capacitive_couplingfile_name.spf

**Using check_timing**
- Type to checking specific to crosstalk analysis 
	- no_driving_cell
	- ideal_clocks
	- partial_input_delay
	- unexpandable_clocks
- Timing reports 
	- report_timing
	- crosstalk_delta
	- report_si_bottleneck
	- report_delay_calculation–crosstalk
	- report_si_double_switching
	- report_noise
- Viewing the Cross talk Analysis Report  
	- report_timing-transition_time-crosstalk_delta\-input_pins-significant_digits4
- Bottleneck Reports 
	- report_si_bottleneck
	- report_bottleneck
	- delta_delay
	- delta_delay_ratio
	- total_victim_delay_bump
	- delay_bump_per_aggressor
	- report_delay_calculation–crosstalk
	- To get a list of all the victim nets with a delay violation or within 2.0 time units of a violation,listed in order of delta delay 
		- report_si_bottleneck-cost_typedelta_delay\-slack_lesser_than2.0
	- size_cell
	- set_coupling_separation
	-include_clock_nets
	-minimum_active_aggressor•
	- In the following example command,the bottleneck command reports nets where three or more active aggressors are affecting the net
		- report_si_bottleneck-cost_typedelta_delay\-minimum_active_aggressors 3

- Crosstalk Net Delay Calculation 
	- report_delay_calculation-crosstalk\-from[get_pinsg1/Z]-to[get_pinsg2/A]
	
- Reporting Crosstalk Settings 
	- To check your crosstalk settings
		- report_si_delay_analysis
		- report_si_noise_analysis
		- report_si_aggressor_exclusion
</details>

<details>	
<summary>Why and How Crosstalk Occurs in a chip</summary>

- First reason crosstalk noise was high routing Density 
- Reason Crosstalk noise occur because the high routing Density and large number of standard cells.
- The cicuit on left figure smaller than the right figure because the different number of cell.For example,if we have two mobile phone.One mobile phone only use for message and call but other one use for running many application.So the number of cell is needed in the chip was different.The chip in the mobile phone that use for running application more complex.
- When the number of standard cell increase  the  routing also increase and it will  close each other .So,it will give some issue .

>![image](https://user-images.githubusercontent.com/118953939/219590600-a5af8972-98b8-4800-9ca4-a23211ccf66b.png)

*source : https://www.vlsisystemdesign.com/*

- Second reason,increase in number of metal layers resulting in increase in lateral capacitance.
- Basically, there are 2 kinds of capacitance.
- Interlayer capacitance: capacitors that is placed between 2 consecutive different layers.
- Lateral capacitance: capacitors that is placed between 2 wires at the same level and metal layer.
- Increase in number of metal layers resulting in increase in  lateral capacitance.
- The overlap area for every metal layer increase because the number of cell increase.
- So, any switching activity happening will immediately affect an activity on the others metal layer because it was close for each other.

>![image](https://user-images.githubusercontent.com/118953939/219592671-92303813-22cf-4a95-ac6f-9a19da47a65a.png)

*source : https://www.vlsisystemdesign.com/*

- Noise margin 
- As we know the inverter logic output will opposite from its input.For example if the input 1 the output will be 0
- So, when we graph it ,we can see that the slope was infinite.
- But,In practical devices the slope will not infinite because have some resistance and capacitance.
- When we see  between 0 and input low voltage(Vil) ,all the output will be treated as logic 1 which is between Vdd and Voh.
- Input between Vil and Vih the output will be  between Voh and Vol.
- But between input high voltage (Vih and Vdd ),the output will be treated as output low voltage (Vol).Vol is the value less than Vil.
- Noise margin define the input voltage range and the output voltage.Basically varied input voltage.
- Noise margin : Any voltage on between range of Vh and Vih will be detected as logic 1.There should be put under the input or the outputs of the circuit.
- Any voltage level in NML range will be detected as logic 0.
- Noise could be easily eliminated or can be ignored at this margin.

>![image](https://user-images.githubusercontent.com/118953939/219594316-30b1d14c-717f-47d8-9431-56cdbf371af8.png)

*source : https://www.vlsisystemdesign.com/*

- We were given 2.5V ont the 0.25um and have two noise margin which is High noise margin and low noise margin.
- This margin was use  to check whether the voltage lies on the High region,undefined region or low margin .It because in the pratical it imposibble to get a steady signal or degrade signal 0 .
- Lower Supply Voltage leading to lesser noise margin.
- When reduce the supply voltage the noise margin also will be reduce.
- For example, anything below to 200millivolt on the left margin will be consider as low margin but on the right the noise margin will be below 100milivolt.


>![image](https://user-images.githubusercontent.com/118953939/219594602-9ff8c128-abe5-4dfd-ba13-9e271342b0c3.png)

*source : https://www.vlsisystemdesign.com/*

</details>

<details>	
<summary>Glitch Example and factor affecting the glitch height</summary>

- As we can see from this picture, the two net was present on 2 connecting inverter which is aggressor net and victim net.
- Between this 2 different net the coupling capacitance was connected called Cm or lateral capacitor.
- The 2 grounded capacitor also connected.Basically whenever this capacitance charge to logic 1 the output of the inverter will be detected as logic 1 but if the capacitor is discharging the inverter will detect logic 0.
- So, this is scenario when we called the aggressor and victim 
- For example, if we take 1 case the aggressor driver input is switching from 1 to 0.The victim driver input is at steady state 1.
- When the input of driver logic 1 the output will be 0,so it means the capacitor will be discharged.If we try to draw the waveform, we can see the straight line.This is the scenario for victim site.
- Now let try to see what happen when we provide an aggregate of driver input  that switching from logic 1 to logic 0.
- When aggressor driver input was logic 1 the aggressor output was logic 0.When the aggressor input start switching from 1 to 0  and after some finite delay the output of aggressor also start to switching from logic 0 to 1.Finally when the aggressor at logic 0 the output will change to 1.
- When the switching from logic 0 to 1  at the output of aggressor,the capacitor will be leak at effect the at victim net whioh charging the other capacitor.
- So can we can see from the waveform the voltage on this capacitor rises from 0 to final level and return back to 0.
- There are two things we need to observe over here,first we need determine whether this  glitch is harmful glitch or how defects this glitch.As previous lecture we have study about the noise margin which we can detect whether the output was on the  logic 0,undefined margin or logic 1 margin.
- Second thing that we need consider was what is that thing the bringing the violation down to zero which is inverter that  bringing it  down to zero.

>![image](https://user-images.githubusercontent.com/118953939/219873895-067c2eda-3ce7-433e-ad0e-503013a2c345.png)

*source : https://www.vlsisystemdesign.com/*

- So, there are two things we have t try understand from this point  which is this particular glitch is tolerable or its lying somewhere between the noise margin that we have learn on the previous lecture.
-The second thing that we have to understand, how come this particular glitch return back to zero.
- When we open the inverter we can see the pmos on the top and nmos at bottom.
- we have got the logic 1 on this particular inverter,so the pmos will off and nmos will on.
>![image](https://user-images.githubusercontent.com/118953939/219873929-0050b67b-7bf2-479b-954d-e8ca1d18513e.png)

*source : https://www.vlsisystemdesign.com/*

- So we replace all the  ‘ON’ transistor by open switch  and the off transistor by ‘OFF’ switch that is the save way to model it.So there is one thing that can we observe here.
- We have discharge part on this load, it means what ever the output which is present overhere,it will charge to potential which is V and then discharge through the nmos transistor .So its completely discharge to 0.
- So we try to do this scenario again by switching the input driver from one to zero and see what happens to this particular inverter.
- We have logic 1 on the input of driver aggressor and the output of driver was logic 0.The another output of the inverter which is on victim net was discharged to logic 0 because of the transistor as discuss on the previous .
- Next, when the input was switching from logic 1 to 0 the output will be moving from the logic 0 to 1 and because of the glitch (cause by leak on Cm) so the two capacitor try to be charge. Because the transistor are not big enough to avoid this glitch so the violation occur.
- Then because the non switching activity on  the aggressor net, the deciding factor was happen which the glitch became the logic 1,undefine or 0 region.If the transistor strong enough which is have low resistance and have bigger size.So if the transistor strong it will try to avoid the overcharge and become logic 0,so the output on the next inverter will be 1.The same situation occur when the transistor not strong enough to overcome the overcharge.We can say that the deciding factor depend on the transistor.
- Functionality failure if the transistor not strong enough to overcome the overcharge  and it will be logic 1 and the next inverter output was logic 0.

>![image](https://user-images.githubusercontent.com/118953939/219874010-a201a492-74a3-4f86-894d-830875440d16.png)

*source : https://www.vlsisystemdesign.com/*

- In second case,the aggressor driver input is switching from 0 to 1 and the victim driver input is at steady state 0.So the output of the inverter at victim net will be 1 
- The particular capacitor completely charge full voltage.
- Now the switching happen from logic 0 to logic 1 and the output of driver aggressor switching was logic 1 to 0.So all the capacitor discharge on this node.
- Let assume this coupling capacitor have the reverse bucket with the hole which is in reverse direction.
- The victim complete charge the logic 1 and get discharge to the leaky Cm and iverter.
- So the falling glitch occur.
- Two thing we need to consider overhere,what is the particular tolerable glitch over here  and how this charge come back to 1.

>![image](https://user-images.githubusercontent.com/118953939/219873938-3cff98f3-191b-4e6f-9185-7a8280e0d6b1.png)

- As we can see the pmos on the top and the bottom have nmos.If we give the logic 0 the pmos will be on and nmos will be off.
- Same situation we replace the on transistor with the closed switch and off transistor with the open switch.
- When the aggressor output was on the logic 0,the gltich we be decide whenever it go to logic 1 or logic 0.It will decided by the transistor by pmos transistor.The lower resistance the higher size of the transistor and chance from the glitch combe back to 1 was higher.Because the transitor resistance low the VDD can maintain to supply the charge and it will avoid the glitch come to logic 0.

>![image](https://user-images.githubusercontent.com/118953939/219874052-e04cd297-2547-4ca7-ac4f-2f122c9e545a.png)

*source : https://www.vlsisystemdesign.com/*

- Factor affecting the glitch height 
- We discuss about the glitch height because we need to determine the tolerable and safe height glitch. We also need to understand if the glitch is to height what the action needed to bring down the height glitch.
- There are few factors that affecting the height glitch :
- Coupling Capacitance Cm.Lets see how the Cm can affecting glitch height 
- We have aggressor and victim  that connected with the Coupling capacitor. If we bring the aggressor and victim close each other the overlap area will be increase and the distance between them will be decrease.
- By bringing both of this closing each other it will increasing the hole of bucket(example of leak capacitor) which is lot of charger will be flow through the leaking capacitor.in other word more charger get discharged during the switching through the aggressor driver.
- In conclusion closer the distance between nets “A” and “V” greater the coupling cap Cm and the glitch larger(more dip more bad).

>![image](https://user-images.githubusercontent.com/118953939/219953867-d462f934-8096-4fa7-9d15-cfc49c9aab12.png)

*source : https://www.vlsisystemdesign.com/*

- Another factor was aggressor drive strength.
- As we can see the gate that connected at the end was driver and the gate was following it was load.
- If we go to the gate, we can know the pmos on top and nmos on the bottom.
- If the input was logic 0,the pmos will be turn on and nmos will be turn off.
- We replace the circuit with closed switched on the pmos and open switch on nmos.
- The drive strength is dependent on the value of the resistance.
- When the area was small the resistance will be huge.Only certain of value will pass this high resistor.
- So, we can say that the smaller have high resistance and the time taken to charge the capacitor  will high but for low area the resistance will be lower, and the - time taken to charge the capacitor  will be high.
- Low drive strength  = more time taken needed to charge capacitance.
- High drive strength = less time taken to charge capacitance.
- For example, if we have the low resistance transistor at the inverter  (higher drive strength).
- So, the amount of  time to charge the capacitor was short and the glitch will be height.
>![image](https://user-images.githubusercontent.com/118953939/219953932-f9a77d63-7fc6-4bb2-a513-0877ed955f67.png)

*source : https://www.vlsisystemdesign.com/*

- From the previous video will understood how does aggressor  drive strength affecting the glitch height 
- Now we understand how the victim drive strength affecting the glitch height.
- From this figure,we have the same circuit as previous and now we try to open up the victim drive strength.
- When we open up that inverter we can see the pmos on the top and nmos on bottom 
- When we apply logic 0 the pmos turn ON and nmos turn OFF.Then we replace the transistor with open and closed switch.
- As previous the value of the resistance we be decide by the value of transistor which is low or high .
- We need to use the low resistance transistor to make the output of drive strength was logic 1.Lower resistance transistor  help to charge the capacitor  fast.
- For example, the high R,time to  current flow through the transistor was high because the resistance was high.In other word it take some time to charge the resistor.
- So the supply voltage loose hand on the victim capacitance and glitch more dip.
- Then when we try to increase the pmos transistor area, so the time taken to charge capacitor a little bit faster than before and the supply voltage tightly holding the victim capacitance and the dip glitch reduce.
- If we reduce R from before we can reduce the glitch because the resistance of transistor is lowerst.So this huge area will make the supply voltage tightly hold the capacitance  and can bring the glitch to logic 1.
- In conclusion low resistance highest chance to bring back the glitch to logic 1.
![image](https://user-images.githubusercontent.com/118953939/219953985-66f6fe4a-f398-4bd6-b42b-6d0f84b07263.png)

*source : https://www.vlsisystemdesign.com/*

- Summarizing 
- First ,The strength  aggressor drive strength will make higher glitch(become the logic 1 will make functionality failure)  and week victim drive strength make the glitch unpredictable (we not know it become 0 or 1).
- Second if we try to increase the victim strength position or lower down the resistance transistor of the victim you might get the glitch low from the previous.In this case it might come back to 0.Then if we try to reduce strength aggressor drivers you have chance to less the amount of charge store in the capacitance,so the glitch lower than previous and tolerable to comeback to logic 0.
- third point or the best way to fix the glitch was by increasing the drive strength of the victim to the high level(lower resistance ).Time taken to charge short and chance glitch to come back to 0 was high.Then we reduce the drive strength of the aggressor ,the amount of current that can flow very low,as the result glitch reduce.
- So the third ways the best one that we have to fix the glitch.

>![image](https://user-images.githubusercontent.com/118953939/219954016-d905be7b-7c8a-4de3-a463-5c843f744b90.png)

*source : https://www.vlsisystemdesign.com/*

</details>
<details>	
<summary>LAB </summary>

- To start this lab we need to invoke pt _shell and set the target  and link library using command below :
```
- Invoke pt_shell
- Set target library and set link library  
- set target_library [list /nfs/png/disks/png_mip_gen6p9ddr_0032/SyahrulNazri/ICC2/ICC2project/VSDBabySoC/src/run_top/sky130_fd_sc_hd__tt_025C_1v80.db /nfs/png/disks/png_mip_gen6p9ddr_0032/SyahrulNazri/ICC2/ICC2project/VSDBabySoC/src/run_top/avsdpll.db /nfs/png/disks/png_mip_gen6p9ddr_0032/SyahrulNazri/ICC2/ICC2project/VSDBabySoC/src/run_top/avsddac.db]    
- set link_library [list /nfs/png/disks/png_mip_gen6p9ddr_0032/SyahrulNazri/ICC2/ICC2project/VSDBabySoC/src/run_top/sky130_fd_sc_hd__tt_025C_1v80.db /nfs/png/disks/png_mip_gen6p9ddr_0032/SyahrulNazri/ICC2/ICC2project/VSDBabySoC/src/run_top/avsdpll.db /nfs/png/disks/png_mip_gen6p9ddr_0032/SyahrulNazri/ICC2/ICC2project/VSDBabySoC/src/run_top/avsddac.db]  
````
>![image](https://user-images.githubusercontent.com/118953939/221392700-b49869c3-749a-4736-b587-da992397e288.png)

- read Verilog file that generated from the previous run in icc2.
- This zip file need to be extract first.
- Link design and check the current design 

```
- read_verilog write_data_dir/vsdbabysoc/vsdbabysoc.pt.v
-gzip -d /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/write_data_dir/vsdbabysoc/vsdbabysoc.pt.v.gz --> before run command the file need to unzip 
- link_design
- current_design
```
>![image](https://user-images.githubusercontent.com/118953939/221392718-4d4eae81-1744-4128-9ffd-4bd9cf73a237.png)

- read parasitic file from the previous run on the icc2
- Check the timing and 5 ports with parastici with no driving cell was showed.
- Read constraint file .

```
- read_parasitics -keep_capacitive_coupling <spef file>
- check timing 
- read_sdc func1.sdc --> this sdc file need to unzip from the previous run at icc2_shell
```
>![image](https://user-images.githubusercontent.com/118953939/221392880-dbfca6e7-78a3-427e-82ae-14b9f77101c6.png)


- report_si_bottle_neck - this command reports the nets that have the largest corsstalk effects that constribute to timing violation 
-  PTE-076 (Information) Setting %s to TRUE and updating timing.
-  XTALK-019  (information) report_si_bottleneck found zero net to report.You received this error message because the  report_si_bottleneck  command has filter out all the candidate nets.

```
- report_si_bottleneck 
- report_si_bottleneck -cost_type delta_delay
- report_si_bottleneck -slack_lesser_than 2.0
- report_si_bottleneck -slack_lesser_than 1.0
- report_si_delay_analysis --> report of multiple min/max delay violation 
- report_si_aggressor_exclusion 
- report_si_noise_analysis 
```
>![image](https://user-images.githubusercontent.com/118953939/221392907-64498d83-649b-4903-851a-bbac7896751f.png)
>![image](https://user-images.githubusercontent.com/118953939/221392916-4ddcb5d7-38f0-4033-b29a-ad0213bcad64.png)
</details>


## Day 28 & 29
  
### Topic - Introduction to DRC/LVS


<details>

<summary>Introduction to SkyWater SKY130 and Open-Source EDA tools </summary>
	
**Skywater PDK**
	
- Skywater Open source PDK is a joint project between Google and Skywater Technology Foundary.It provides a fully open source Process Design kit(PDK) and its related resources.
- SkyWater open PDK public respository contains documentation,PDK library and files.

**Open-Source EDA Tools**
- Open_PDKs is a make file based installer that takes files from the SkyWater PDKs and reformats them for a number of open source EDA tools.
- Tools currently supported 
	- Magic 
	- Klayout 
	- Openlane 
	- Xschem 
	- Netgen 
	- Ngspice 
	- Iverilog 
	- qflow 
	- IRSIM 
	- xcircuit
- To install SKY130 PDKs,we must clone the respository and specify the process to compile and install.
- Can use command below
	```
	- git clone https://github.com/RTimothyEdwards/open_pdks
	- cd open_pdks
	- configure --enable-sky130-pdk
	- make  --> grabs the SKY130 repository and submodules,as well as a few third party repositories to use in the install. 
	- sudo make install
	```
- The libraries supported by oepn_pdks are :
	- Digit standard cells 
	- Primitive devices/analog 
	- I/O cells 
	- 3rd party libraries
- Open_PDKs uses a common installed filesystem structure :
	- SkyWater PDKs are placed under the directory /usr/share//usr/share/pdk/sky130A/.
	- Under this main SK130 PDK directory, are 2 subdirectories .
		- libs.tech = contains all subdirectories for the open source tool setups 
		- libs.ref = contains the reference libraries in various formats.
</details>

<details>

<summary>Physical Verification and Designs Flows</summary>

- check if the voltage,signals and timings match the specification;
	- Physical verification is to check whether you have a mask layout that matches what you think the circuit should be.The figure below shows the design flow for physical verification.
	>![image](https://user-images.githubusercontent.com/118953939/220269232-bccad20c-60c1-420c-a65a-7181357f4a6b.png)
- Two major steps in physical verification 
	- Design Rule Checking = to ensure that your layout matches all the rules provided by the foundy for that specific process.
	- Layout Vs Schematic = ensure that your layout netlist matches with your schematic netlist.

</details>

<details>

<summary>(Day 1)Lab-Checking Tool Installations</summary>
 
- **magic** --> birngs up a layout window and a console window that is a stock tcl  interpreter used to run commands for layout actions.
- **magic -noconsole** --> Can get the tcl interpreter in the terminal itseld instead of the seperate console window.
- **magic -dnull -noconsole** --> can be run without the graphics layout window.
- **magic -dnull -noconsole filename.tcl** --> to run magic in bactch mode.
- **netgen** --> completely command driven and has no graphics interface. Its console window is a stock tcl interpreter like magic as well. 
- **netgen -noconsole** --> can get tcl interpreter in the terminal itself instead of the seperate console window.
- **netgen -batch source filename.tcl** --> run netgen in batch mode 
- **xschem** --> bring up a schematic window.Unlike other this has no seperate console window and uses the native command line terminal for tcl commands.
- **xschem --tcl filename.tcl -q** --> can be run in batch mode with the command.
- **ngspice** --> has its own prompt and runs its own set of interpreter commands that aren't based on tcl 
- **ngspice-b** --> can be run batch mode

>![image](https://user-images.githubusercontent.com/118953939/220299272-ea709ef6-ae7b-4516-a3c6-5742e9d75ccd.png)

We create directory for the design and initialise subdirectories  for each of the open source tools that we will be using.Then we must set up each directory for its respective tool to run properly with the Skywater PDKs.Using  **ln -s /filepath** we can creating a symbolic link between the inititalised subdirectories and SKY130 submodules with the open_pdks installer.After thaht lets run **xschem** to brings up the display .
	
>![image](https://user-images.githubusercontent.com/118953939/220501678-f5be8ba9-5942-4681-bdb6-d43aecf3c9f9.png)

>![image](https://user-images.githubusercontent.com/118953939/220502712-e4124d4e-5b7e-4681-adfd-eeb8615fba62.png)

</details>

<details>

<summary>(DAY1)Creating Sky130 device layout in magic</summary>
- Use command **magic -d XR** and it will bring up the 2 magic windows with the layout window displaying **Technology :sky130A**.
- We can create some device by clicking the device 1 and set the width tp 2um,length 0.5um and fingers 3 .This should result as below.
- Then change the device type to sky130_fd_pr_nfet_g5v0d10v5
	
>![image](https://user-images.githubusercontent.com/118953939/220510012-52329fb6-7864-4c53-a5bf-c7368de82efb.png)
>![image](https://user-images.githubusercontent.com/118953939/220511716-e932e3bb-dd86-433a-87dd-4d02645f9903.png)

</details>

	

<details>

<summary>(DAY1)Creating an inverter design </summary>

- run xschem and create new file 
- To add component press **insert** and search fd_pr library.
- Select nfet and pfet window and place it anywhere in the schematic 
- As pins are not PDK specific,it can be found in library and choose ipin.sym,opin.sym and iopin.sym.
- Then press W to wire all the connection and press Q to edit the parameter(as shows in the figure).
- After finish it we save in our directory and and click menu to select **Make symbol from schematic"
- Now we can create a testbench schematic using the new schematic option and insert the generated symbol from the local directory using the lns key.

	
>![image](https://user-images.githubusercontent.com/118953939/220539214-694fade0-675f-45c1-9714-4c97a2301bd4.png)

>![image](https://user-images.githubusercontent.com/118953939/220840328-91d5cf42-5177-4ffc-9585-cde2ee0429da.png)

- For pfet the source via coverage set to +40 and top guard ring via coverage to 100
- The drain via coverage also change to -40
- For nfet the Bottom guard ring via coverage to 100, while the source and drain via coverages are set to +40 and -40, respectively, like the pfet
- 

>![image](https://user-images.githubusercontent.com/118953939/220840480-761c1171-f4f6-468a-ade4-29eef5fc7c69.png)

- Cd ../mag/
- Magic  -d  XR
- Import inverter.spice file
- Drawing the routing design 


>![image](https://user-images.githubusercontent.com/118953939/220840576-2f8e0b78-fed5-4011-a527-48d137722233.png)

- Rm *ext --> clear unwanted rm *ext
- Checking the LVS and the result is not match.Need to recheck the layout and modified the design to make sure it is match  

>![image](https://user-images.githubusercontent.com/118953939/220840801-ed1f6673-6d7b-4a6a-b135-1edeb4e056f4.png)

- Open **magic –d XR** and run command below
- extract do local 
- extract all
- ext2spice lvs 
- ext2spice cthresh 0 --> tells magic to add all parasitic capacitance in the inverter.spice
- ext2spice


>![image](https://user-images.githubusercontent.com/118953939/220843308-fc73d1ab-0b50-45e3-90d2-936eb6e866cd.png)

- Before do  ngspice inverter_tb.spice 
- The output waveform not same need to check again the design. 

>![image](https://user-images.githubusercontent.com/118953939/220840881-bf6d42c2-0d29-4325-b829-ccb0c88381e5.png)
	
</details>

<details>
<summary>(DAY2) Design Rule Checks and Layout Vs. Simulation</summary>

</details>

<details>
<summary>(DAY2) GDS read and input styles </summary>

- Create project directory and set it up for running a magic environment 

>![image](https://user-images.githubusercontent.com/118953939/220921029-ed6e2dc8-81b3-4566-8f42-5bcfac87a538.png)

- cif listall istyle  =   To view the possible styles
- cif list istyle  = we can also see the current style .
- Cif istyle rng =  check the sky130 style 

>![image](https://user-images.githubusercontent.com/118953939/220921170-8ac764ee-a216-40ed-9858-c69427263d74.png)

- Lets read the GDS files from the PDK using the command gds read **/usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/gds/sky130_fd_sc_hd.gds**
- To see all available top level cells,we can run command **cellname top**

>![image](https://user-images.githubusercontent.com/118953939/220921365-340f9772-bb39-411c-931e-6b38c69c37a9.png)

- List of all cell top name 

>![image](https://user-images.githubusercontent.com/118953939/220921753-cda8a597-0f2f-421c-a187-be9eafc14988.png)

- Go to menu  option and click cell manager and pick 1 of the cell sky130_fd_sc_hd_and2_1

>![image](https://user-images.githubusercontent.com/118953939/220922091-e34d06bf-5c9b-4fd0-9df1-f1c1589b9485.png)

- Cif istyle sky130(vendor) = the current file will be overwritten and no more yellow markes treat as regylar text.
- Gds noduplicates true =  If you do not want to automatically overwrite existing cells when reading from gds,

>![image](https://user-images.githubusercontent.com/118953939/220922386-5d67f7e9-4c67-42a8-a3ec-214e5c38391b.png)

</details>

<details>
<summary>(DAY2)Port</summary>
	
- Port index = select port and use this command to know the port.
- command port first to find the index of the first port and to inquire about the port use 
- Port 1 name 
- Port 1 class 
- Port 1 use 

>![image](https://user-images.githubusercontent.com/118953939/220924988-e95b29d0-f749-45e9-824e-245e63edff14.png)

- The cell definition shows the first port to be port A,the gds read of the file in magic shows the first port as VPWR.
- However port numbering is considered metadata and is not included in the gds file.
- To add medata to gds we read from lef file by using this command ** lef read /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/lef/sky130_fd_sc_hd.lef**
- After that run the port inquires like previous 

>![image](https://user-images.githubusercontent.com/118953939/220924008-2de91785-476e-4976-b984-b1bc05cf7e96.png)

- To read port from spice file we can use this comman **readspice /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/spice/sky130_fd_sc_hd.spice** 
	
>![image](https://user-images.githubusercontent.com/118953939/220924383-e6ef6194-e719-4ec5-aa23-1a5f8e149f80.png)
</details>

<details>
<summary>(DAY2)Labs Abstract views</summary>

- Open new magic and read lef library  **lef read /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/lef/sky130_fd_sc_hd.lef**
- Load sky130_fd_sc_hd_and2_1
- The result as below   

>![image](https://user-images.githubusercontent.com/118953939/220962178-c2d44c38-3975-40ad-93eb-345d0141be58.png)

- If we check port information,we can see that port order metadata isn’t present in the lef file

>![image](https://user-images.githubusercontent.com/118953939/220962349-39e74493-e3c5-4784-8ddb-5397295bbec7.png)

- Read spice as before readspice /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/spice/sky130_fd_sc_hd.spice

- Write port 1 and port 3 to know the name. 

>![image](https://user-images.githubusercontent.com/118953939/220962526-bfbfc02c-e965-4df6-a232-5eba762bcfb0.png)

- Using load test to create new layout 
- Then instantiate the AND cell using **getcell sky130_fd_sc_hd__and2_1**
- Press **X** button to get full view of cell.
- It will brings up the abstract view

>![image](https://user-images.githubusercontent.com/118953939/220962708-935a6303-4d38-498e-b28f-13abc7a17ac0.png)

- If we try write gds we got following error 
>![image](https://user-images.githubusercontent.com/118953939/220962896-d398a095-7f3f-44d9-9f07-6f275e0f6990.png)

- If we try read gds file back,we get new layout
- The loaded gds looks different because Magic is not supposed to write abstraction views to gds.
- Save the test file and load it.

>![image](https://user-images.githubusercontent.com/118953939/220963088-d7b1f637-5702-4c32-99b4-d6d941d612cf.png)

- After loaded it back to new session of magic

>![image](https://user-images.githubusercontent.com/118953939/220963256-b222a1c9-b8bf-4971-b505-1c93f2413aa8.png)

-As we have done a save test and not write all,only the cell that was currently being edited gets saved and not any subcells. As the cell currently being edited was from the SkyWater PDKs ,it found the standard cell content from the library path,using **path** command.

>![image](https://user-images.githubusercontent.com/118953939/220963379-01da269d-26aa-4f73-a2ee-2ef4b2769211.png)

- Write **gds write test** and we would get a valid gds file.
- If we go deeper into this and2_1 cell we will observe that a magic  is referencing the metadata from a file .
- It can be checked by selecting the cell  by pressing “I” button and press “>” button and type property.

>![image](https://user-images.githubusercontent.com/118953939/220963500-3534a50d-7f0b-4c68-bd3b-702835ff3514.png)

- If we were to make the cell writeable and paint a layer of local interconnect over the cell 
- Then a new gds file would remain unchanged without the painted layer.

>![image](https://user-images.githubusercontent.com/118953939/220963668-804b71df-6af3-4476-9b95-e70dada535cc.png)

```
Gds readonly true
Gds rescale false
Gds read /usr/share/pdk/sky130A/libs.ref/sky130_fd_sc_hd/gds/sky130_fd_sc_hd.gds
Load sky130_fd_sc_hd__and2-1
Property 
```
>![image](https://user-images.githubusercontent.com/118953939/220963875-949cc74a-f4ea-4bef-a42c-36773eeb1b9f.png)
	
</details>

<details>
<summary>(DAY2)Labs Basic Extraction </summary>

- Load sky130_fd_sc_hd_and2_1
- Extract all 
- Ext2spice lvs 
- Ext2spice 

>![image](https://user-images.githubusercontent.com/118953939/221136209-b66bc0d0-7257-4165-b5b6-d37b3b4f88b9.png)

- vi sky130_fd_sc_hd__and2_1.spice
- Ext2spic cthresh 0 = to add parasitic 
- Reopen spice file again
- The ext2spice cthresh 0.01 
- Ext2spice 
- Reopen spice file again 

>![image](https://user-images.githubusercontent.com/118953939/221191801-5402bfe6-2997-46ff-9e8b-6f20c8fad27c.png)
	
- To run full R-C extraction can use command below 
- Ext2 sim labels on 
- Extresist tolerance 10
- Extresist 
- This shows the number of resistor nets found usable and creates a .res.ext file which holds information to modify the existing .ext file for R parasitics.

>![image](https://user-images.githubusercontent.com/118953939/221193369-6c03f4d9-5083-4c2d-b855-00e9c4f1b65b.png)

</details>
	
<details>
<summary>(DAY2) Setup DRC </summary>

- As we can see,there are DRC errors in the vendor .mag file for the and2_1 subcell since the standard cell layouts do not have internal connections to the well and substrate to save room .
- The reason we does not have seen this error in magic because it run DRC check,while the default drc style in magic was fast DRC.
- If we change DRC style to full, and force a DRC check, we can see DRC errors present in the standard cell.

>![image](https://user-images.githubusercontent.com/118953939/221194336-139136d6-9920-499f-9838-72a7fe5938fd.png)

>![image](https://user-images.githubusercontent.com/118953939/221194497-62c2119a-f88d-4eac-974c-428127eadbb7.png)

- In this picture we can see the error are when dow a drc find 

>![image](https://user-images.githubusercontent.com/118953939/221194554-4f718168-a547-4737-adc9-fa52febb084f.png)

-  add and align a cell in the existing layout by getcell sky_fd_sc_hd__tapvpwrvgnd_1 , we see that there are no more DRC errors in the top level.
- If we descend into the and2_1 cell layer though, the DRC errors are still present. But in the top level layout, these errors get fixed.
>![image](https://user-images.githubusercontent.com/118953939/221194619-6705a082-54fb-4fa2-b9d3-1d5ef85968e5.png)

</details>
	
<details>
<summary>(DAY2) Setup LVS </summary>

- Extract and quit
- make new directory and copy setup.tcl file 

>![image](https://user-images.githubusercontent.com/118953939/221195180-a917ca1f-ba57-4a55-a5c8-d198da935075.png)

- When executing we get the following result that showing the netlist match .

>![image](https://user-images.githubusercontent.com/118953939/221195217-123d5cb9-cd15-47b1-a12d-b446c8e7a27c.png)

</details>
	
<details>
<summary>(DAY2) Setup XOR </summary>

-  When executing we get the following result that showing the netlist match .
- As we can see the result just contain  the small layer of polysilicon that was erased.

>![image](https://user-images.githubusercontent.com/118953939/221195736-dbfd71fe-1216-449a-907c-2baa0f20d7ac.png)

</details>
	
<details>
<summary>(DAY3)Lab - Width and Spacing Rules </summary>


- git clone https://github.com/RTimothyEdwards/vsd_drc_lab.git
- After git clone use magic to see exercise_1.mag
- Zoom and select the area and go to menu DRC report.

>![image](https://user-images.githubusercontent.com/118953939/221224148-265cf27c-0ab1-40f7-b830-20fbc035a14a.png)

- Increase width of metal layer and paint using the command bpx width 0.14um and pain m2

>![image](https://user-images.githubusercontent.com/118953939/221224503-31eb130c-3c0b-4cda-81c4-b2df06762988.png)

- Report_drc on spacing rule.The  white dots indicate 1 error meaning magic count this apcing error as 2 DRC errors.

>![image](https://user-images.githubusercontent.com/118953939/221224901-8d1fbef9-9a20-4b6d-aab7-c6469b606538.png)

- By moving using move e 0.14um or numpad keys 4 and 6

>![image](https://user-images.githubusercontent.com/118953939/221225018-9915dd94-592b-44c1-962b-42b7eb81ce87.png)
	
</details>

<details>
<summary>(DAY3)Lab-spacing notch rules </summary>

- For exercise 1c we have  2 error when run DRC report
- The first is a regular spacing error for the smaller rectangle, and the second shows a wide spacing error for the larger rectangle.

>![image](https://user-images.githubusercontent.com/118953939/221225593-bc723b6a-20ad-4baa-b316-a8bc47611478.png)

- Have two error report and after select the box half and press 4 and 6 to move it.
>![image](https://user-images.githubusercontent.com/118953939/221225776-238d0f23-65ed-4ff3-8290-d31d1066b44f.png)

</details>
	
<details>
<summary>(DAY3)Lab-Contact cuts(via) and its DRC error </summary>
	
![image](https://user-images.githubusercontent.com/118953939/221226120-e290f0e4-e441-40b8-bf62-9cf63c033ae6.png)

- Have 1 overlap error
![image](https://user-images.githubusercontent.com/118953939/221226193-3f63109e-3fea-4af6-9657-37ebddac8a2b.png)

- Still have overlap error.Can fix by box grow   

>![image](https://user-images.githubusercontent.com/118953939/221226379-a80a0a11-0966-4f04-be95-b55809f64cc5.png)

- After box grow error was missing 

>![image](https://user-images.githubusercontent.com/118953939/221226410-c68d53a5-39bc-418d-837b-9cbb62612eda.png)

- Use wiring tool  we can draw wires.By clicking SHIFT+left we can move up a metal layer until we reach the top most metal 5 layer.Move down layer by SHIFT + right 

>![image](https://user-images.githubusercontent.com/118953939/221227151-49bfc01b-60f0-40df-8fc1-bd4f681e9b49.png)

</details>

<details>
<summary>(DAY3)Lab- Minimum Area and Minimum Hole Rule</summary>

- Load in example3.mag. Make box at 3a and run DRC error

>![image](https://user-images.githubusercontent.com/118953939/221227705-c90d03b1-aba0-43c1-bfc9-bf3911dc1e7e.png)

- Select the metal and press B key, we see that the current area is 0.2um.

>![image](https://user-images.githubusercontent.com/118953939/221227994-8bfe3187-718e-4522-9bf7-903ccb339fe5.png)

- To fix  select area and stretch the layer to meet the requirement

>![image](https://user-images.githubusercontent.com/118953939/221228141-fb2a707d-a275-493a-b6f4-5be92d595007.png)

- By utilising the wiring tool, wire paths nearly usually fulfil the minimum area rules. 
When jumping up by two or more levels, it is possible to violate this rule, as seen below, because there isn't enough metal 1 to meet the minimum area rule, among other violations.

>![image](https://user-images.githubusercontent.com/118953939/221228265-3a876e7d-6fe2-4c3c-ab31-789911cb4f6d.png)

- click DRC then click DRC mode to see this DRC error. 
- Then click DRC complete . 
- Next we must tell Magic to update the DRC count, and then run a DRC report.
	
>![image](https://user-images.githubusercontent.com/118953939/221228351-6a2a22d6-6056-4f8c-8d73-8d16bdb88851.png)

- Set the cursor box to the size of the hole manually , we see it is 0.07um2 which is smaller than allowed.  
- To fix this we must manually erase sections of the metal till the hole is big enough to pass DRC.
	
>![image](https://user-images.githubusercontent.com/118953939/221228615-0c7ac80b-4fe2-4be9-b8aa-3445902faa1f.png)

</details>

<details>
<summary>(DAY3) Lab For Wells And Deep N-Well</summary>
- Load exercise4.mag 
- There is  wells and taps, do the DRC check. 
- Example 4a have a basic well error, since the wells do not have taps. 
- The n-well shows an error as it is currently floating, though the "p-well" does not since this process doesn't actually consider p-wells unless they are in deep n-wells, and are instead counted as p-substrates.

- Need to paint a layer of n type material into the n well. The layer is called nsubstratendiff. (Problem still not fix)
- The tap should be connected to a layer of local interconnect.
- Adjust the layers using what we have learnt till now by growing, stretching and adding in local interconnect, until get no DRC errors.

>![image](https://user-images.githubusercontent.com/118953939/221406605-971802ec-e699-457b-b65d-6222be2acd5c.png)

>![image](https://user-images.githubusercontent.com/118953939/221406648-fb0b80b1-d4be-407a-8637-ad1a3fec05ed.png)

</details>



<details>
<summary>(DAY3)Lab For Derived Layers</summary>

- Here we can check the layers with the what command as before.

>![image](https://user-images.githubusercontent.com/118953939/221406821-96608938-5ecf-4c96-b8c1-894c3be01207.png)

- Magic regards this as a nmos, rather than a nmoslvt as previously. Based on the directions in the tech file, we must specifically paint in a layer of nmoslvt to get a layer of nmoslvt. We've already discussed Magic's implant layers and how they're employed for autogeneration. Let us visualise these implant layers using the commands below.

![image](https://user-images.githubusercontent.com/118953939/221406911-73091fcb-4807-4103-b22b-8c186812b4dc.png)


</details>

<details>
<summary>(DAY3)Lab For Paramterized And PDK Devices</summary>

>![image](https://user-images.githubusercontent.com/118953939/221406931-10d41eaa-1e07-4222-8fbb-3e4ed8bdf797.png)

- If we descend into the subcell with this key “>”,we can see DRC error does exist and it have been fixed 

>![image](https://user-images.githubusercontent.com/118953939/221406943-c4daf7a9-0655-488b-a67c-de87fc39c7fb.png)

- We know the cellname and location of the cell
- So we need to relocate this cell

>![image](https://user-images.githubusercontent.com/118953939/221406971-cb398f71-60be-4545-9d67-1b9d6ae099f6.png)

- Descend into cell by press button “>” and save it.can confirm that cell still point to a valid gds file with property command

>![image](https://user-images.githubusercontent.com/118953939/221406987-292c795b-67a8-4293-8286-ab78cdcf7736.png)

- Fix drc error by erase poly command 
>![image](https://user-images.githubusercontent.com/118953939/221407019-61bebed1-f9f2-4df6-9831-8a3bdad71918.png)

>![image](https://user-images.githubusercontent.com/118953939/221407047-d07afd7c-2388-4fa2-9152-c3790019759b.png)

</details>


<details>
<summary>(DAY3)Lab For Angle Error And Overlap Rule</summary>
>![image](https://user-images.githubusercontent.com/118953939/221407056-3a7ed15a-0109-4496-9c98-a406f9811126.png)

- To fix this angle error using press s button and press scroll button on the mouse to paint it.
>![image](https://user-images.githubusercontent.com/118953939/221407073-200994f1-1b53-4d62-ac3d-ab5a39b602fd.png)

- To fix this error just click the error scroll button with cursor on the poly.

>![image](https://user-images.githubusercontent.com/118953939/221407114-630853b4-888c-4ea3-a67e-a5ecdf6a44d5.png)

- To fix this use command below 
>![image](https://user-images.githubusercontent.com/118953939/221407128-96951bf8-f9b0-4eaf-ab60-e0df79314919.png)

- We can see the  overlap error because the poly have different rules.to fix we can flatten it by copy DRC.

>![image](https://user-images.githubusercontent.com/118953939/221407143-265fe000-40c4-49f8-9c95-4be1fa57c99b.png)

- To fix this we can easily select one of them and move them horizontally 
>![image](https://user-images.githubusercontent.com/118953939/221407154-4ff98b13-f6de-4af1-ab2c-4b00dd57fd97.png)

</details>


<details>
<summary>(DAY3)Lab For Unimplemented Rules</summary>

- Seal rings are just layers that have no electrical meaning, and are just a physical barrier between the chip and the outside world. These seal ring layers break multiple design rules, and are not worth the effort to include in the tech file

>![image](https://user-images.githubusercontent.com/118953939/221407188-136e4c8d-8524-4e38-aaec-b7cfb66f04d5.png)

- So the SkyWater PDK actually has a seal ring generator that can generate gds correct seal rings, though these cannot be imported into Magic unless as abstract views. We can use the seal ring generator with the command below.This should create a .mag and .gds file 

>![image](https://user-images.githubusercontent.com/118953939/221407210-0f6a22a3-2975-4c2c-9396-c0b4f5ebbff0.png)

- Run magic again and load advSeal_6um_gen and use this corner created complete seal ring 

>![image](https://user-images.githubusercontent.com/118953939/221407223-5296fbb4-d939-46e7-ac00-ee08b681ff68.png)

- open up the magic console and use the command addpath <created_directory>, and then open up the seal ring file with load <file_name>.
- Now, we can run a script launch for magic that runs magic with the appropriate tech file to view the seal ring, with the command ./gds_magic. Now we load the gds file with gds read seal_test/adv_6um_gen to see the seal ring.

>![image](https://user-images.githubusercontent.com/118953939/221407235-7c098ba6-538d-44be-9b13-04f30d850295.png)

</details>

<details>
<summary>(DAY3)Lab for Latch-up And Antenna Rule</summary>
 
- In exercise9.mag, we have a layout with standard cells that violates some of the basic rules.

>![image](https://user-images.githubusercontent.com/118953939/221407514-52c626ba-df83-4182-878c-8a49eb81f25b.png)

>![image](https://user-images.githubusercontent.com/118953939/221407540-a4544e6b-f222-4bfd-8121-b3691e01a75e.png)

- Now we can look at ERC which have a few standard cell layout with very long route between them.
> ![image](https://user-images.githubusercontent.com/118953939/221407576-107b5f5b-571b-4c82-8505-737e74c9afc5.png)

- To get knowledge of the circuit, the circuit needs to be extracted. We can extract the layout as follows.


>![image](https://user-images.githubusercontent.com/118953939/221407583-9d193692-fbe6-4b18-aa09-189a291a609e.png)

- The antenna check show up as feedback on the layout and we can use feedback why for some more information and detail also can use command antennacheck debug 

>![image](https://user-images.githubusercontent.com/118953939/221407613-4c2a9478-9b56-419b-8e95-09f340b85060.png)
>![image](https://user-images.githubusercontent.com/118953939/221407641-647df3c6-53bc-4096-998b-48e2bb9e86ac.png)


</details>
<details>
<summary>(DAY3)Lab For Density Rules</summary>

- The metal1 layer is just a thin section going around the layout, which depicts under-density for that metal layer. Then metal2 covers pretty much the entire layout, leading to over-density for the metal2 layer.So, to check for density coverage, we use the following commands.

>![image](https://user-images.githubusercontent.com/118953939/221407672-af9c3d92-347f-4d20-9b00-f206262fd6db.png)

- The metal1 layer is just a thin section going around the layout that depicts the metal layer's under-density. Similarly, metal2 covers almost the entire layout, resulting in metal2 layer over-density. The following commands are used to check for density coverage.So to do this gds write exercise11

>![image](https://user-images.githubusercontent.com/118953939/221407684-0dc5558e-475c-4348-b03e-85d758c23b90.png)

To fix we use this command below 

>![image](https://user-images.githubusercontent.com/118953939/221407701-ab86c8cd-562a-4b68-ad94-0ec40436dac3.png)

>![image](https://user-images.githubusercontent.com/118953939/221407716-679cee98-ee3c-4f79-abb4-91466338d0ef.png)

- Read gds file.to see only specific layer we can use all command in this Picture 
>![image](https://user-images.githubusercontent.com/118953939/221407722-fd8869c8-8aff-49f5-85b8-e399766e8800.png)

- we load the exercise_11.mag file again. We need to make  sure that  the position of both the layout and fill patterns align properly. To do this, we follow the command steps below.

>![image](https://user-images.githubusercontent.com/118953939/221407736-451cd3b5-0a0a-4066-a87b-48bedb4d845b.png)

- We can see that fill were align and now we can check for density coverage again by setting the cif output style to density 
>![image](https://user-images.githubusercontent.com/118953939/221407751-d5489e81-2bdc-4b61-8d01-a947d61c9c3e.png)

</details>

