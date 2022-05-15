# FPGA

![k](https://user-images.githubusercontent.com/87826618/167341735-a77a3543-019a-481c-9b0c-6b2cadf6f9f9.jpg)


# Content
- [Introduction](https://github.com/mahmo-gh/SandBox/blob/main/README.md#introduction)
- [The difference between FPGA and ASIC](https://github.com/mahmo-gh/SandBox/blob/main/README.md#the-difference-between-fpga-and-asic)
- [Why use an FPGA (advantages)](https://github.com/mahmo-gh/SandBox/blob/main/README.md#why-use-an-fpga-)
- [Architecture](https://github.com/mahmo-gh/SandBox/blob/main/README.md#why-architecture-)
- [FPGA Programming](https://github.com/mahmo-gh/SandBox/blob/main/README.md#why-fpga-programming-)




## Introduction

A field-programmable gate array, or "FPGA" for short is an integrated circuit designed to be re-programmable using a hardware description language such as VHDL and Verilog to customize a certain digital logic. An FPGA is an extremely flexible and sophisticated device that can be programmed to function as other specific devices hence reducing the amount of hardware needed as well as the cost and power consumption.

![ezgif-3-52cfe67754](https://user-images.githubusercontent.com/87826618/167336217-320a2811-4e47-49c3-8fff-2dee72d2ceed.gif)


## The difference between FPGA and ASIC

1. The fact that FPGAs are programmable distinguishes them from **A**plication **S**pecific **I**ntegrated **C**ircuits , or ASIC.
Here's an analogy to help demonstrate the difference between them, imagine a blank page on a digital painting program, that page could be re-drawn over and over again with different shapes but that is not the case with a physical blank canvas once it gets painted, it can't be redesigned and a new canvas is needed. The same goes for the difference between FPGAs and ASICs, an FPGA can be reprogrammed an infinite number of times to function as as a microprocessor, or as an encryption unit, or graphics card, or even all these three at once while that's not possible for an ASIC as they're designed for one sole purpose and they function the same their whole operating life. For example, the CPU inside a smart phone is an ASIC. It is meant to function as a CPU for its whole life.

 ASIC            |  FPGA
:-------------------------:|:-------------------------:
![7VW](https://user-images.githubusercontent.com/87826618/167341044-fee34dd0-b42c-44f1-838c-0c3dbe7842f3.gif)  |  ![giphy](https://user-images.githubusercontent.com/87826618/167341046-6cdcb762-be01-4b5b-adec-21f414c881b8.gif) 

2. The gif below demonstrates the previous point showing the FPGA gets reprogrammed over end over again while the ASIC remains the same.

![Kickstarter_Logitraxx_Xilinx_FPGA_Powered_Tracked_Robot](https://user-images.githubusercontent.com/87826618/167510882-756276e8-0055-4327-9ff7-6c0d0cdfe56f.gif)

3. It's far cheaper to get started with FPGA development it can cost as low as $30. On the other hand, ASICs have a very high-cost barrier that reaches millions of dollars to start ASIC development from scratch.  The photo below shows that the total cost for ASICs starts very high owing to the NRE cost (Non-recurring engineering cost refers to the one-time cost to research, design, develop and test a new product), but its slope is flatter. That is, prototyping ASICs in small quantities is very costly, but in large volumes, the cost per volume becomes very less. In the case of FPGAs, the slope is much higher, so in large volumes, it becomes costly in comparison to ASICs. as a result, when it comes to high-volume mass production, ASICs are the way to go.


![Screenshot 2022-05-10 010137](https://user-images.githubusercontent.com/87826618/167512356-a1acdec0-cea5-4244-a411-2e0f940d5278.jpg)

4. Analog design is another advantage of ASICs over FPGAs. Although FPGAs may contain specific analog hardware such as PLLs, ADC, etc, they are not much flexible as ASICs.


5. FPGAs are limited in their operating frequency compared to ASICs as The routing and configurable logic eats up timing margin in FPGAs while ASICs are optimized for their specific function so they can operate at a much higher frequency.


6. For the same function, ASICs are more power-efficient than FPGAs.

**The image below summarizes the comparison between FPGAs and ASICs**

 ![Screenshot 2022-05-10 013554](https://user-images.githubusercontent.com/87826618/167515806-ce52d23c-701f-4c30-ab6f-d9ed54b2ce64.jpg)
 
 ## Why use an FPGA ?
 
 - **Prototyping** : To verify digital hardware designs without the upfront cost of ASIC manufacture. Many ASICs are prototyped using FPGAs themselves!
 
 
 - **Acceleration** : FPGAs are highly suited for applications where the current design might need to be upgraded to use a better algorithm or to a better design that of course impossible to achieve with ASICs.
 
 
 - **Fast time to market** : ASIC design flow is a more involved process and takes longer. Therefore, some people may opt for ready-made FPGA chips so they can move to market faster.


 - **parallelism** : This is one of the huge advantages of FPGA is in the main one of the main reasons why you would choose them over a microcontroller for certain projects because if you take your basic microcontroller it's effectively a bottleneck everything has to run through that processor call in sequence while with FPGAs you can achieve parallelism because this all this logic block or all the logic blocks are completely configurable and separate so you can be processing different pins and outputting something at the exact instant.


## FPGA Programming
![image](https://user-images.githubusercontent.com/66218339/168486711-4cf240f5-3c22-444e-bfe5-81602bdc0bd0.png)

FPGAs bridge the gap between programming software and programming hardware via their physical attributes that can be manipulated through the Hardware Description Languages (HDLs).

The process is the same as writing a code, where this code is turned into a binary file and then loaded on the FPGA, but instead of running it via software sequentially, the outcome is physical changes to the hardware. Whatever you’re writing will eventually end up as a physical circuit.

The binary file describes how an FPGA has to be configured, and how to connect the gates, flip-flops, and the other circuit components included in the FPGA.

An inbuilt configuration circuit inside the FPGA reads this binary file via a flash memory and configures the FPGA accordingly. It can also be achieved by another FPGA or microcontroller in charge of the configuration and boot-up process.

Hardware Description Languages that are commonly used to program FPGAs are Verilog, VHDL (Very high -speed integrated circuits Hardware Description Language), and SystemVerilog.

### FPGA-programming building units:
- **Compiling**:Compilation of Hardware Description Language (HDL) into register transfer logic (RTL). As the name implies, data is transferred to registers. The compiler is said to produce bits to control fixed-gate patterns (registers, arithmetic logic unit, and so on). 
Then synthesizing, the synthesizer defines gate patterns described by the program logic. Meaning your program logic gets synthesized into logical gates, not into instructions.
The output is an Electronic Design Interchange Format (EDIF) file. 

- **Linking**:Either you must be linked to the operating system or other programs existing in libraries.
The place and route operation in FPGA places the synthesized EDIF and makes connections to produce HEX files that can be loaded into the FPGA.
This bitstream will end up controlling the logic gates and filling registers and memories.

- **Loading**:Finally, FPGA programs - compiled, synthesized, placed, and routed ones- must be loaded in the physical FPGAs so as to implement the gates of the system.

