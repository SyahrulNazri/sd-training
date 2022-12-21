
# Syahrul Nazri-Intel SD Training 

## Table of contents
* [ Day 0 - System/Tool Setup Check. GitHub ID creation ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-0)
* [ Day 1 - Labs using iverilog and gtkwave ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-1)
* [ Day 2 - Timing libs,hierarchical vs flatsynthesis and effecient flop coding styles ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-2)
* [ Day 3 -Combinational and Sequential Optimizations](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day3)
* [ Day 4 -GLS,Blocking vs Non-blocking and Synthesis-Simulation mismatch]( https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#topic---glsblocking-vs-non-blocking-and-synthesis-simulation-mismatch)
* [ Day 5 -Design of Testability](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day5)
* [ Day 6 -Introduction Logic Synthesis](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-6)
* [ Day 7 -Basic of Static Timing Analysis(STA)](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-7)
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
*Can see all the attributes such as area on lib_cell and cell,capacitance on the port and pin,fucntion also shows the on the cell and port.
>>![image](https://user-images.githubusercontent.com/118953939/208856456-967d75f7-c334-44ab-b9f6-4787ff5f08fd.png)

