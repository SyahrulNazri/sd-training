
## Day 21
  
### Topic - Placement and Route  


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

- Check list Befor CTS 

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
