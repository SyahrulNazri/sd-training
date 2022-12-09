## Day3
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

------------------------------------------------------------------------------------------------------------------
### Topic - Lab Combinational Logic Optimizations 
**(1) Opt_check1**
*2 input AND Gate*
>![Slide1](https://user-images.githubusercontent.com/118953939/206689873-b8e86a1f-e66a-4c10-904a-a50ab3e9d769.PNG)

**(2) Opt_check2**
*2 input OR gate *
>![Slide2](https://user-images.githubusercontent.com/118953939/206689955-32c36f1f-8215-4708-8e4b-c1d7051748d5.PNG)


**(3) Opt_check3**
*3 Input AND gate *
>![Slide3](https://user-images.githubusercontent.com/118953939/206690007-a17ffa59-252f-4257-ba51-8eb385b0d286.PNG)


**(4) Opt_check4**
*2 Input XNOR gate *
>![Slide4](https://user-images.githubusercontent.com/118953939/206690056-148a4ab9-d103-4588-aeae-21fca31f72dd.PNG)

**(5) Multiple_module_opt**
>![Slide5](https://user-images.githubusercontent.com/118953939/206690095-f491284c-f166-47fd-b5f3-36b26137c951.PNG)


**(6) Multiple_module_opt2**
*sub_module1= AND gate*
![Slide7](https://user-images.githubusercontent.com/118953939/206690176-c9a91b7a-470a-44cd-860a-0e868a9313f0.PNG)


----------------------------------------------------------------------------------------------------------------------

### Topic-Sequential logic Optimizations 
**(1) dff_const1**
*If reset was high the output  q will below and it turn back to high on next positive clock edge  if reset was high . 
>![Slide9](https://user-images.githubusercontent.com/118953939/206690244-091b663e-df84-41a1-9370-8e94b9818a28.PNG)
>
>![Slide10](https://user-images.githubusercontent.com/118953939/206690269-a5bece2b-aacf-487c-adc1-4b3186157d23.PNG)

**(2) dff_const2**

*If reset  was high the q will high  and even the reset was low the q will not change.In conlusion, q was not make anychanges even the reset high or low.
>![Slide11](https://user-images.githubusercontent.com/118953939/206690312-275c4f63-d8b1-4ee9-8a24-375597a077a6.PNG)

>![Slide12](https://user-images.githubusercontent.com/118953939/206690337-c23f42d8-c99f-4d35-ac4e-4160e244cac8.PNG)

**(3) dff_const3**

*There are 2 flip flop and the output q1 will be low iff the reset high and it will change high if the reset low.But for q it will be always high except for 1 clock cycle.More detail on the diagram below.*

>![Slide13](https://user-images.githubusercontent.com/118953939/206690372-bb6be053-8b96-4fc9-b02a-972d1144b775.PNG)

>![Slide14](https://user-images.githubusercontent.com/118953939/206690390-0ad7490a-f646-4119-a261-c89c7569a44b.PNG)

**(4) dff_const4**
*Q and q1 always 1.No change.*
>![Slide16](https://user-images.githubusercontent.com/118953939/206690461-33493517-0871-4884-b0fa-cdfbb9c82717.PNG)

>![Slide17](https://user-images.githubusercontent.com/118953939/206690488-05203fbd-ebd7-40b2-9fae-00da4ae7f4c1.PNG)

**(5) dff_const5**
>![Slide18](https://user-images.githubusercontent.com/118953939/206690708-ccd514aa-3b1d-4635-9650-bafa10013800.PNG)

>![Slide19](https://user-images.githubusercontent.com/118953939/206690778-97266468-2031-492a-9ea8-31448921a71d.PNG)

## Topic-Unused Output Optimization
**(1) counter_opt**
>![Slide20](https://user-images.githubusercontent.com/118953939/206690918-cc3ca693-9820-48e0-99db-bf249d3aef41.PNG)

*Modified count[0] --->count [2:0]
>![Slide21](https://user-images.githubusercontent.com/118953939/206691124-b0f49c40-3c05-4513-a687-de992698f429.PNG)

>![Slide22](https://user-images.githubusercontent.com/118953939/206691179-ebe9a1c3-103d-40e1-8f31-3b99133080db.PNG)

>![Slide23](https://user-images.githubusercontent.com/118953939/206691206-f51ae6c0-b816-4425-9454-1638620e7326.PNG)

>![Slide24](https://user-images.githubusercontent.com/118953939/206691243-45d3d9d1-ad1f-4714-a4f6-cee85253c430.PNG)






