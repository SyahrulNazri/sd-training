
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

  </details>
  
     
 <Details>
 <summary>ASIC Design Flow</summary>

 - ASIC Flow Objective :RTL to GDSII = Take Design from Resistor transfer level (RTL) to GDSII format for the final layout and it also called as Automated PnR and        Physical Implementation.
 - RTL to GDSII flow 
    - Synthesis --> Floor/Power Planing --> Placement --> Clock Tree Synthesis --> Routing --> Sign OFF 
 ![image](https://user-images.githubusercontent.com/118953939/212274137-89230947-0306-4e81-987d-dd887d607aac.png)

 **Synthesis**
 - Purpose of synthesis is to convert RTL to a circuit out of component from the stadndar cell library(SCL)
 - The result of circuit is described in HDL or in gate level netlist.
 - Standard cells have regular layout and each cell has different views or model which is Electrical,HDL,SPICE and Layout (Abstract and Detailed)
 
 >![image](https://user-images.githubusercontent.com/118953939/212276687-de4befaa-9a3e-457e-9827-c811e5e8bdb8.png)
