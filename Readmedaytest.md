
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
  
  ## Get Familiar to open-source EDA tools
  
    
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
  
>![image](https://user-images.githubusercontent.com/118953939/212477652-28d008bf-8fba-4010-8613-040fe6dc7f40.png)

  
 </details>
  
 <Details>
 <summary>Step to Charactize Synthesis Result</summary>
  
  >![image](https://user-images.githubusercontent.com/118953939/212477695-57335e78-d3a5-41c7-b3d5-e8873ed7ee36.png)

  >![image](https://user-images.githubusercontent.com/118953939/212477701-86f4be2d-7a4f-4d96-a265-6e612bf60a0b.png)

  >![image](https://user-images.githubusercontent.com/118953939/212477707-ffba286b-f772-4589-90c8-24de0dd48cbd.png)

  </details>
  
  
