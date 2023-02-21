
## Day 28
  
### Topic -  Introduction to DRC/LVS


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

**Physical Verification and Designs Flows**

- check if the voltage,signals and timings match the specification;
	- Physical verification is to check whether you have a mask layout that matches what you think the circuit should be.The figure below shows the design flow for physical verification.
	>![image](https://user-images.githubusercontent.com/118953939/220269232-bccad20c-60c1-420c-a65a-7181357f4a6b.png)
- Two major steps in physical verification 
	- Design Rule Checking = to ensure that your layout matches all the rules provided by the foundy for that specific process.
	- Layout Vs Schematic = ensure that your layout netlist matches with your schematic netlist.

**Lab-Checking Tool Installations**
	
	- can be run using command *magic* --> birngs up a layout window and a console window that is a stock tcl  interpreter used to run commands for layout actions.
	- *magic -noconsole* --> Can get the tcl interpreter in the terminal itseld instead of the seperate console window.
	- *magic -dnull -noconsole* --> can be run without the graphics layout window.
	- *magic -dnull -noconsole filename.tcl* --> to run magic in bactch mode.
	
	
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
