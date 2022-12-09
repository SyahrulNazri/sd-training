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
>![Slide1](https://user-images.githubusercontent.com/118953939/206679156-00601a10-5579-4d70-b9e6-3e58f64357ea.JPG)

**(2) Opt_check2**
*2 input OR gate *
>![Slide2](https://user-images.githubusercontent.com/118953939/206679167-2910e5ea-457a-4a90-a2c7-2a57373c8cdb.JPG)

**(3) Opt_check3**
*3 Input AND gate *
>![Slide3](https://user-images.githubusercontent.com/118953939/206679196-adb40f20-ed26-491d-8e06-e44ff5e9ad72.JPG)

**(4) Opt_check4**
*2 Input XNOR gate *
>![Slide4](https://user-images.githubusercontent.com/118953939/206679203-b2411d3d-81ec-4404-a110-05ee80a39419.JPG)

**(5) Multiple_module_opt**


**(6) Multiple_module_opt2**
*sub_module1= AND gate*
![Slide7](https://user-images.githubusercontent.com/118953939/206680662-6a9745e4-0baa-4861-b46b-0e1a79b0fa3d.JPG)


----------------------------------------------------------------------------------------------------------------------

### Topic-Sequential logic Optimizations 
**(1) dff_const1**
>![Slide9](https://user-images.githubusercontent.com/118953939/206681957-8326375f-1566-455c-ac48-f67c658d6b35.JPG)

>![Slide10](https://user-images.githubusercontent.com/118953939/206681975-584743e3-2900-4360-bb01-288033e08a26.JPG)

**(2) dff_const2**
*If reset  was high the q will high  and even the reset was low the q will not change.In conlusion, q was not make anychanges even the reset high or low.
>![Slide11](https://user-images.githubusercontent.com/118953939/206682904-062ccec1-9b14-4d18-a307-e58bb8e12724.JPG)

>![Slide12](https://user-images.githubusercontent.com/118953939/206682929-0827199f-4214-44b1-bf48-2c969b00cafa.JPG)

**(3) dff_const3**
*There are 2 flip flop and the output q1 will be low iff the reset high and it will change high if the reset low.But for q it will be always high except for 1 clock cycle.More detail on the diagram below.*

>![Slide13](https://user-images.githubusercontent.com/118953939/206683896-76ebc3a8-2789-4508-ac45-19cb70454097.JPG)

>![Slide14](https://user-images.githubusercontent.com/118953939/206684800-de8e8ab6-000b-4e4a-aac2-f9e48609212d.JPG)



