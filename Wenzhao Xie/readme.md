Weekly Report 2020/2/12

  Completed the mini Davinci DLA control logic package(native interface, not AXI).
  
  Finished 2 conv testcases:
  
  1.Test Cases 0				
  
      input: 114x114		output: 58x58			pad size: 1		  	ksize: 3  		stride: 1		pool size: 2			pool mode: average	
      length_0: 32 			length_1: 24			length_2: 32			length_3: 24								
      heigth_0: 32			height_1: 32			height_2: 24			height_3: 24			input layer number: 32		
      length_num_0: 3	  length_num_1: 3		length_num_2: 3		length_num_3: 1		output layer number: 32	
      
      Actual time: 300836 cycles
      Idea time:   112*112*9*32*32/512 = 225792 cycles
      Efficincy:   75%
      
   2.Test Cases 1				
  
      input: 224x224		output: 113x113	  pad size: 1		  	ksize: 3  		stride: 1		pool size: 2			pool mode: max	
      length_0: 32 			length_1: 14			length_2: 32			length_3: 14								
      heigth_0: 32			height_1: 32			height_2: 14			height_3: 14			input layer number: 3		
      length_num_0: 7	  length_num_1: 7		length_num_2: 7		length_num_3: 1		output layer number: 16
      
      Actual time: 232399 cycles
      Idea time:   222*222*9*3*16/512 = 41583 cycles
      Efficiency:  17.89%

  Next week plan: complete other two testcases, then combine these cases together to a simple convolution network, test it.
  
  All the test files needed for simulation and the DLA code have been uploaded, it can be run without bug in vivado2018.2(only in simulation).
  
-----------------------------------------
Weekly Report 1.9-1.15 
  
  Generated random ifmap, weights data and corresponding golden ofmap using python. 
  
  Dump the input data into bram and run loop C using random data, compared the DLA output and golden output.
  
  Debug the stupid loop C and found some deeply hidden bugs, fixed it, now the DLA output is perfectly matched with the golden output.
  
    Bug example:
  
    reg signed [15:0] a;
  
    reg signed [15:0] b;
  
    wire signed [16:0] c;
  
    a <=  6666;
  
    b <= -6662;
  
    assign c = a + b;
  
    c will be a negative number.
  
----------------------------------------
Weekly Report 11.20-11.26

  1.Finished part of the DLA loop test;
  
  2.Moved on my DLA RTL code writing;
  
  2.Continued writing document for DLA;
  
  3.Reconsidered my DLA architecture and design details.
  
----------------------------------------
Weekly Report 11.13-11.19

    Continued writing documents and RTL codes for my graduation project.
----------------------------------------
Weekly Report 11.6-11.12

  Finished a pretty weird and boring report last Friday.
  Made the opening report for my graduation project.
  Working on my graduation project, basically optimized some module and write some testcases and document.
  
----------------------------------------
Weekly Report 10.18-10.23
  
  Report to Prof.Shi about my graduation project.
  wrote a little code for my graduation project.
  
-----------------------------------------
Weekly Report 7.4-10.17

  期间主要是去复旦微电子实习了，在公司组里调研了不少公司的加速器产品。这个工作持续时间大概是从7月中下旬到9月初。
  然后9月到现在差不多是在找工作和构思毕设，这两天写好schedule发给史老师过目，如果觉得OK就可以正式开题了。后面在公司也是做这个毕设的题目，会在组会上不时汇报一下进度，请大家提点意见。
  
  没做啥实事，还是浪费了一些时间。
  
------------------------------------------
Weekly Report 6.28-7.4

  Finished all the final projects and reports, read sevaral papers about sparse accelerator.
  Next week I will ask for one week holidays.

------------------------------------------
Weekly Report 6.20-6.27

  Continued preparing for the final examination and the final projects. Nearly finished.

------------------------------------------
Weekly Report 6.14-6.19

  Prepared for the final examinations and presentations.

------------------------------------------
Weekly Report 6.7-6.13

  Designed an asynchronous FIFO and a syncchronous FIFO, for verilog practicing and part of one of my final project. Read several papers, which are mainly about Globally Asynchronous Locally Synchronous System.
  Next week is about to prepare for my final examinations and projects.
  The verilog code I wrote has been uploaded.
  
------------------------------------------
Weekly Report 5.10-5.25
  
  I designed a video realtime display system using OV5640 with SCCB interface, the main codes are already finished, now configuring the camera configuration registers(the display effect is not good, the picture size, fps and color remain to be optimized). 
  The codes and schemetic are uploaded. 
  
------------------------------------------
Weekly Report 4.26-5.9

  Finished the whole IIC EEPROM project, including RTL coding and testing, the verilog files have beed updated.
  Now doing some reaerch on using OV7670. Finished the SCCB control module writing, now working on configuring registers of OV7670.
  Read several papers about Global Asynchronous and Local Synchronous, it's part of a school course project.
  
------------------------------------------
Weekly Report 4.19-4.25

  This week I finished writing the verilog module EEPROM using IIC, and finished some basic test on behavior simulation(write data to certain space area and read it). Now I'm writing a more complete testbench to test it.
  The code files are uploaded already.
  
------------------------------------------
Weekly Report 4.12-4.18

  This week I did some research on IIC BUS and now I'm trying to write a IIC EEPROM Verilog module for practice. This module has three parts: IIC control logic, EEPROM and a testbench which acts as CPU.
  
------------------------------------------
Weekliy Report 4.5-4.11

  I have been working on Linux device driver writing. An AXI device is created and used in the hardware design, a device driver is needed for this AXI device. I wrote a driver and packaged it as a .ko file in order to install the driver into the Linux kernel.However some "Invalid format module" error shows. I think it's because the kernel edition that the .ko file uses is different from the Linux kernel edition. Haven't find the solution yet.
  
------------------------------------------
Weekly Report 3.29-4.4

1.Did some research about writing device driver in embedded Linux. Inserting custom IP into hardware design and running it on Linux in FPGA requires a device driver for it and it looks pretty difficult. Now I'm trying to make a simple AXI-lite device driver. I'm not sure whether I can make it.

2.Script language Perl learning, Verilog HDL learning.

------------------------------------------
Weekly Report 3.21-3.28

1.Verilog HDL learning . Now writing a Parallel_to_Serial module to practice HDL coding. Next step is to write a IIC module to continue the practice. 

2.Embedded Linux system built on FPGA documentation writing, to record the workflow, and ensure the workflow is suitable to most hardware designs.


Plan for next week:
1.Continue the HDL learning.
2.Going to learning some script language.
3.Paper reading.
