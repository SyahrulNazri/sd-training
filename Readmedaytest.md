
## Day 15 
### Topic Inception of Open-source EDA,OpenLANE and Sky130 PDK

<Details>
 <summary>How to Talk to computer</summary>
  
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
 
 Process of converting RISC-V architecture to layout 
 
  1) C++ codes will be compiled in RISC-V assembly language program.
  2) This assembly language will convert the code to the machine language which is binary language that containing logc 0 and logic .This binary language only              undertstood by the computer and it will be used to sketched in a layout by the computer program and we will get the required output.
  3) But another interface also played their role between architecture and layout of RISC-V which is Hardware Description LAnguage(HDL) where it used impmeneting the        specification of RISC-V
 >![image](https://user-images.githubusercontent.com/118953939/212260209-f2a32a5a-afc7-4dac-a3b5-8d1398282856.png)
  source :https://www.vlsisystemdesign.com/
   </details>
   
 ![image](https://user-images.githubusercontent.com/118953939/212260151-810c2458-81aa-472d-893d-bb41b7a284ee.png)
