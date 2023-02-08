
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

</details>

	






