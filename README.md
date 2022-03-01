
### Implementation Of 2:1 MUX using CMOS 


This repository presents the design of 2:1 Multiplexer implemented using Synopsis Custom Compiler on 28nm CMOS Technology.


##  Table Of Content
   * [Abstract](#Abstract)
   * [Detailed Explanation](#Detailed-Explanation)
   * [Reference Circuit](#Reference-Circuit)
   * [Tools Used](#Tools-Used)
   * [CMOS 2:1 Multiplexer](#CMOS-2:1_MUX)
   * [Simulations](#Simulations)
   * [Netlist](#Netlist)
   * [Acknowledgements](#Acknowledgements)
   * [References](#References)
 





## Abstract
Implementation of 2:1 Mux is being designed using CMOS. A multiplexer is a logic circuit that accepts several data inputs and allows only one of them at a time to get through the output. The routing of the desired data input to the output is controlled by select inputs. 



## Detailed Explanation
There are two types of multiplexing- Time multiplexing and Frequency multiplexing. In Time multiplexing each device is given a specific time interval to use the line. In Frequency multiplexing, several devices share a common line by transmitting at different frequencies. Here we are going to implement 2 input MUX, which has a single output based on single select line input. The reference circuit and the reference waveforms obtained while implementing this circuit is given. 

 CIRCUIT DETAILS : 
  BASIC 2-INPUT MULTIPLEXER: 
      The logic circuitry of 2 input multiplexer with data inputs A and B, and data select line S. It connects two 1-bit sources to a common destination. It has two input lines and one output line. The logic level applied to s input determines which AND gate is enabled, so that its input passes through OR gate to the output. The output Y=AS’+BS. 

  A. Implementation of 2:1 MUX using CMOS:
  
   CMOS consists the combination of NMOS and PMOS.PMOS is called as pull-up transistor and NMOS is called as pull-down transistor. For AND operation NMOS are connected in series and PMOS are connected in parallel. Whereas for OR operation NMOS are connected in parallel and PMOS are connected in series. The fixed structure of CMOS implementation is pull-up (PMOS) network is always connected to VDD source, and pull-down (NMOS) network is connected to GND. The output of the CMOS circuit isdriven between PMOS and NMOS. 

   The 2:1 mux can be implemented as the equation of output is Y=AS’+BS. As AS’ and BS have the AND operation 
   therefore PMOS is connected in series so we use 2 PMOS transistors for implementing AS’ and 2 PMOS transistors for implementing BS, and both are connected in parallel as there is a OR operation between them. Similarly, 2 NMOS are connected in series for implementation of AS’ and 2 NMOS are connected in series for implementation of BS. Both AS’and BS NMOS are connected in parallel for OR operation. The output is driven between the PMOS and NMOS. From that output, CMOS inverter is connected and the output of inverter is the output of 2:1 mux. 
   
   If the select line is 0 output Y will be A and if the select line 1 then output Y will be B. In the reference waveform the output Y will have same clock pulse as A when S will be 0 and it will have the same clock pulse sequence as B when S will be 1. 


## Reference Circuit
  Reference Circuit and Waveforms 
<p align="center">
<img width="600"
     height="500"
  src="![reference_schematic](https://user-images.githubusercontent.com/64627151/156127630-1e286c4a-2691-4e1d-9a12-c35d2075086f.jpeg)"><br />
  REFERENCE CIRCUIT<br />
</p>
<p align="center">
<img width="600"
     height="500"
  src="![reference_waveform](https://user-images.githubusercontent.com/64627151/156127169-48510ace-981a-4b50-94a6-0644b7929f40.jpeg)"><br />
  REFERENCE WAVEFORM<br />
</p>


## Tools Used

- Synopsys Custom Compiler:  The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design.Custom Compiler provides design entry, simulation results and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.
- Synopsys Primewave:  PrimeWave™ Design is a environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helps in various types of simulations. 
- Synopsys 28nm PDK:  The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above designed circuit.


## CMOS 2:1 Multiplexer


<p align="center">
<img width="800"
     height="600"
  src="![Schematic_circuit](https://user-images.githubusercontent.com/64627151/156128358-65fb74f7-8e33-4efe-9880-111c6785c47f.png)"><br />
 2:1_Mux using CMOS Circuit <br />
</p>


<p align="center">
<img width="800"
     height="600"
  src="![Circuit_symbol](https://user-images.githubusercontent.com/64627151/156128569-d176bdf8-ca92-4520-beef-802a497229ac.png)"><br />
 2:1_Mux using CMOS Circuit Symbol <br />
</p>

 
<p align="center">
<img width="800"
     height="600"
  src="![Circuit_Schematic_tb](https://user-images.githubusercontent.com/64627151/156128771-9a699177-4aae-4a19-b7d6-1d319049ef19.png)"><br />
 2:1_Mux using CMOS Circuit_tb <br />
</p>


## Simulations Results

<p align="center">
<img width="800"
     height="600"
  src="![Waveforms](https://user-images.githubusercontent.com/64627151/156134244-a3f4d666-f2f1-4a34-9fbc-2d8180528e2d.png)"><br />
 2:1_Mux using CMOS Simulation_Waveforms <br />
</p>

Here first two waveforms are inputs A and B, and third waveform is Selection line. Output of the circuit is fourth waveform(Yellow colour).


# Netlist

Refer to the netlist of the circuits here:

*  Generated for: PrimeSim
*  Design library name: design_27
*  Design cell name: mux_2x1_0_tb
*  Design view name: schematic
.lib '/PDK/SAED_PDK32nm/hspice/saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Tue Mar  1 08:23:47 2022

.global gnd!
********************************************************************************
* Library          : design_27
* Cell             : mux_2x1_0
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt mux_2x1_0 a b gnd_1 s vout vdd
xm10 net51 s vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm9 vout net40 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm3 net14 b net40 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm2 vdd a net14 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm1 net40 s net14 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm0 net14 net51 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm11 net51 s gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm8 vout net40 gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm7 net29 a gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm6 gnd_1 b net26 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm5 net26 s net40 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm4 net40 net51 net29 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
.ends mux_2x1_0

********************************************************************************
* Library          : design_27
* Cell             : mux_2x1_0_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 net9 net7 gnd! net11 vout net13 mux_2x1_0
v3 net11 gnd! dc=0 pulse ( 0 1.05 0 0.001u 0.001u 50u 100u )
v2 net9 gnd! dc=0 pulse ( 0 1.05 0 0.001u 0.001u 50u 100u )
v1 net7 gnd! dc=0 pulse ( 1.05 0 0 0.001u 0.001u 100u 200u )
v4 net13 gnd! dc=1








.tran '10' '600n' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(net11) v(net7) v(net9) v(vout)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end



## Author

- Bemalkhed Akhilesh, BTech ECE, B.V.Raju Institute Of Technology, Narsapur-502313.


## Acknowledgements

 - [Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)
 - [Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')
 - [Synopsys India](https://www.synopsys.com/)
 - [Sameer Durgoji, NIT Karnataka](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)
 - [Chinmay panda, IIT Hyderabad](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)



## References

- https://www.electronics-tutorial.net/Digital-CMOSDesign/Pass-Transistor-Logic/2-1-MUX-using-transmissiongate/ 
- Sameer Durgoji, Kunal Ghosh, "VSD Intern - 10-bit DAC design using eSim and Sky130"
#� �I�m�p�l�e�m�e�n�t�a�t�i�o�n�-�O�f�-�2�-�1�-�M�U�X�-�u�s�i�n�g�-�C�M�O�S�-�
�
�#� �I�m�p�l�e�m�e�n�t�a�t�i�o�n�-�O�f�-�2�-�1�-�M�U�X�-�u�s�i�n�g�-�C�M�O�S�-�
�
�# Implementation-Of-2-1-MUX-using-CMOS-
