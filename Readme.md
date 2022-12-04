
# Syahrul Nazri-Intel SD Training 

## Table of contents
* [ Day 0 - System/Tool Setup Check. GitHub ID creation ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-0)
* [ Day 1 - Labs using iverilog and gtkwave ](https://github.com/SyahrulNazri/sd-training/blob/main/Readme.md#day-1)

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
### Topic - Labs using iverilog and gtkwave

1.Git clone from other directory.
**GitClone**= used to point to an existing repo and make a clone or copy of that repo at in a new directory.

2.Open Output File using GTKWAVE
Figure below shows the **gtkwave** for tb_godd_mux.vcd 
<img width="962" alt="lab2waveform" src="https://user-images.githubusercontent.com/118953939/205324453-9eb7165e-7d6f-47f8-905a-2bd511f4593b.PNG">

3.RTL code 
File structure for **tb_good_mux.v** and **good_mux.v**

<img width="382" alt="vimcode" src="https://user-images.githubusercontent.com/118953939/205324818-34a12188-1419-425f-88fd-ba0018f80a47.PNG">

<img width="449" alt="vimcode2" src="https://user-images.githubusercontent.com/118953939/205324920-6ad1c570-7f5a-4619-8cbf-c4a4fda100bf.PNG">
