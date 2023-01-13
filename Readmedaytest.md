
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
  
 **Routing**
  
 - The process of implementing the interconnect using the available metal layers.
 - Metals is tracks from a routing grid and this routing grid is huge.So,devide and conquere approach.
    - Global Routing :Generating routing guides 
    - Detailed Routing :Using routing guides to implement the actual wiring.
>![image](https://user-images.githubusercontent.com/118953939/212286543-ea5ea5c5-516a-48c7-a418-a818235bd70e.png)
  
 **Sign Off** 
 
 Final layout 
 -Physical Verifications 
    - Design Rules Checking (DRC) -to maek sure the fnal layout follow all the design rules. 
    - Layout vs Schematic (LVS) - Ensuring the final layout matches the gate level netlist of th design 
 - Timing Verification
    - Static Timing Analysis (STA) -To make sure all the timing constraints are met and the circuit will run at designated clock frequencies.
  </details>
