# **Hands On Overview**
In LPBAM Handson we will implement the following scenario making use of **two queues**.

We will use **ADC4** and **LPTIM1** which are peripherals available in **Stop2** into Smart Run Domain.

- **ADC4** conversion will be triggered by **LPTIM1** at 256Hz for 1s.
- **ADC4** converts data samples that are transferred to **SRAM4** by **LPDMA ch1** in STOP2 mode
- After 1s we change the **LPTIM** frequency to trigger 64Hz conversion rate for 1s
- **LPDMA ch1** will be used for peripheral to memory transfer and **LPDMA ch0** for **LPTIM** reconfiguration keeping MCU in **Stop2**
- Wakeup will happen on **DMA TC IT** triggered by ADC4 when 320 half words are acquired

<ainfo>
Same application can also run on a single queue. 
Our purpose it to show how to handle multiple LPDMA channels and how complexity is reduced thanks to LPBAM tool configurator integrated into STM32CubeMx
</ainfo>


[sourcecode nomal speed ](https://github.com/manu19901991/SITGES2022/blob/main/lpbam/LPBAM_normal_speed.bin)

---

[sourcecode 10xspeed ](https://github.com/manu19901991/SITGES2022/blob/main/lpbam/LPBAM_10x_speed.bin)


---

![Cubemx start](./img/0001.png)

# Queue 1

![Cubemx start](./img/0002.png)
 

 # Queue 2
 ![Cubemx start](./img/0003.png)


 
