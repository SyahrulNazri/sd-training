
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


</details>

 
 <details>
<summary>Crosstalk and clock net shielding</summary>
 
  
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

