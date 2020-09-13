# vsdcomparator
This repository contains a structural as well as functional description of a comparator with 3.3v analog voltage. This repository will maintain simulation files and other relevant files on the pre-mentioned design block worked on in the Online VSD IP Design Research Internship program 2020.

*Note: Circuit requires further optimization to improve performance. Design yet to be modified.*


Table of contents
=================
<!--ts-->
   * [A Glance at the Comparator IP](#a-glance-at-the-comparator-ip)
        * [Block Diagram of the Comparator IP](#block-diagram-of-the-comparator-ip)
        * [Internal Block Diagram of the Comparator IP](#internal-block-diagram-of-the-comparator-ip)    
   * [Circuit Diagram of the Comparator IP](#circuit-diagram-of-the-comparator-ip)
        * [Circuit Diagram of each sub-block](#circuit-diagram-of-each-sub--block)
   * [Running the Simulation](#running-the-simulation)
   * [Pre-Layout Simulation result](#pre-layout-simulation-result)Pre-Layout Simulation result for each block
        * [Pre-Layout Simulation result for each block](#pre-layout-simulation-result-for-each-block)
   * [Layout](#layout)
      * [Layout of Complete Comparator](#layout-of-complete-comparator)
      * [Layout of Inverter Block](#layout-of-inverter-block)
      * [Layout of CMOS OR Logic Block](#layout-of-cmos-or-logic-block)
      * [Layout of Differential Pair with En pin and single i/p applied to NMOS along with biasing circuit](#layout-of-differential-pair-with-en-pin-and-single-i/p-applied-to-nmos-along-with-biasing-circuit)
      * [Layout of Differential Pair with 2 i/ps applied to NMOS where the En is the o/p of the single i/p differential block](#layout-of-differential-pair-with-2-i/ps-applied-to-nmos-where-the-en-is-the-o/p-of-the-single-i/p-differential-block)
      * [Layout of Differential Pair with 2 i/ps applied to PMOS where the En is the o/p of the single i/p differential block](#layout-of-differential-pair-with-2-i/ps-applied-to-pmos-where-the-en-is-the-o/p-of-the-single-i/p-differential-block)
   * [Post-Layout Simulation of Complete Comparator IP](#post-layout-simulation-of-complete-comparator-ip)
   * [Issues | Improvements | Future Work](#issues--improvements--future-work)
   * [Open-Source VLSI Tools](#open-source-vlsi-tools)
       * [About Ngspice](#about-ngspice)
   * [Acknowledgments](#acknowledgments)
   * [Contact Information](#contact-information)
<!--te-->

## A Glance at the Comparator IP

The  Design Specifications of the Comparator IP can be found [here](/Documentations/specs.pdf).

### Block Diagram of the Comparator IP

 <p align="center">
  <img width="850" height="550" src="/Images/vsd_comp.PNG">
</p>


### Internal Block Diagram of the Comparator IP

The Comparator IP is built using 5 important circuit sub-components:
1. Biasing Circuit
2. Differential Pair with level shifter where i/p is applied to NMOS
3. Differential Pair with level shifter where i/p is applied to PMOS
4. CMOS Inverter circuit
5. CMOS OR Logic circuit

 <p align="center">
  <img width="900" height="550" src="/Images/comp_int.PNG">
</p>


## Comparator Performance Parameters 

| Parameter| Description| min | typ | max | Unit | Condition |
| :---:  | :-: | :-: | :-: | :---:  | :-: | :-: |
|VDD|Digital supply voltage||3.3||V|T=-40C to 85C|
|VIO|Input offset voltage||0.5||mV|T=27C|
|IBN|Bias current||0.05||mA|T=-40C to 85C|
|Rise TPD|Rise propagation delay||1||ns|T=27C, IBN=0.05mA|
|Fall TPD|Fall propagation delay||1.7||ns|T=27C, IBN=0.05mA|
|CL|Load Capacitance||10||pF||
|IDD|Supply current||0.1||mA|T=27C, EN=1, IBN=0.05mA|


## Circuit Diagram of the Comparator IP


 <p align="center">
  <img width="850" height="500" src="/Images/comp_ckt.PNG">
</p>


## Subcircuits within the Comparator IP


## Differential Pair with En pin and single i/p applied to NMOS

<p align="center">
  <img width="850" height="550" src="/Images/blk1.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b1.PNG">
</p>


## CMOS Inverter block 

<p align="center">
  <img width="350" height="550" src="/Images/blk2.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b2.PNG">
</p>


## Differential Pair with 2 i/ps applied to NMOS where the En is the o/p of the 1st differential single i/p block 

<p align="center">
  <img width="850" height="550" src="/Images/blk3.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b3.PNG">
</p>


## Differential Pair with 2 i/ps applied to PMOS where the En is the o/p of the 1st differential single i/p block 

<p align="center">
  <img width="850" height="550" src="/Images/blk4.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b4.PNG">
</p>


## CMOS OR Logic block

<p align="center">
  <img width="850" height="550" src="/Images/blk5.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b5.PNG">
</p>


## A list of transistor dimention I've used 

|     Transistor    |   W (um)  |   L (um)  |
| :---:  | :-: | :-: |
|   M5, M21, M31   |   6   |   0.2   |
|rest all the transistors used|   2   |   0.2   |
|  M10, M12, M14, M23, M25, M34, M36, M39, M40, M42  |   1   |   0.2   |



```
You can take w=10u for M13 and w=5u for M14 also, performance will not be affected that much here. I've changed those according to the above list to meet the dimension spec.
```


## Running the Simulation


To enter the Ngspice Shell, open the terminal & type:
```
$ ngspice
```
To simulate a netlist, type:
```
ngspice 1 ->  <filename>.cir
```

You can exit from the Ngspice Shell by typing:
```
ngspice 1 ->  exit
```
 <p align="center"> or </p>
 
```
ngspice 1 ->  quit
```

## Pre-Layout Simulation

To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/mou3ananya/ComparatorIP
$  cd ComparatorIP/simulation/preLayout/
```
### Waveform Analysis of Comparator circuit 

```
Open the comparator.cir file. Here the difference between 2 i/p signals which that IP can detect is 0.5mV. You can take any other combinations for i/p voltages also by entering the i/p signals as shown in the image below.

```

 <p align="center">
  <img width="550" height="250" src="/Images/input.PNG">
</p>

Run the netlist file using the following command.

```
$  ngspice comparator.cir
```

Observe the corresponding waveforms

### Inverting (v_n) and Non-inverting (v_p) i/p waveforms

<p align="center">
  <img width="1000" height="600" src="/Images/w_comp1.PNG">
</p>

### En (Enable Active High) i/p waveform

<p align="center">
  <img width="1000" height="600" src="/Images/w_comp3.PNG">
</p>

### Comparator o/p waveform

<p align="center">
  <img width="1000" height="600" src="/Images/w_comp2.PNG">
</p>

```
When En='1'[3.3v], o/p[OUT] follows the Non-inverting i/p[v_p]  
If En='0' then whole IP becomes off 
During OFF state o/p remains at logic '0'

```

## Pre-Layout Simulation result for each block

## Differential Pair with 2 i/ps applied to NMOS where the En is the o/p of the single i/p differential block 

To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/mou3ananya/ComparatorIP
$  cd ComparatorIP/simulation/preLayout/
```
```
Open the compN.cir file. Here the difference between 2 i/p signals which that IP can detect is 6mV. You can take any other combinations for i/p voltages also by entering the i/p signals as shown in the image below.
```

 <p align="center">
  <img width="550" height="250" src="/Images/inputN.PNG">
</p>

Run the netlist file using the following command.

```
$  ngspice compN.cir
```

Observe the corresponding waveforms

### Inverting (v_n) and Non-inverting (v_p) i/p waveforms

<p align="center">
  <img width="1000" height="600" src="/Images/w_compN.PNG">
</p>

### En (Enable Active High) signal and o/p waveform

<p align="center">
  <img width="1000" height="600" src="/Images/w_compN1.PNG">
</p>


```
This sub-block itself acts as a comparator. 
```


## Issues | Improvements

 
1.  An important issue what I've met during simulation is the accuracy problem for the very small i/p voltage range i.e. for [0-0.4v] this range this comparator can't detect 
   the very small difference between inverting and non-inverting i/p.
   
 ```
                    Ex. If we apply '0'v to one i/p and 0.2v to another then it can't detect this even 0.2v large gap also.
                        If we even take 0.3v instead of 0.2v that will give the o/p but with a huge delay.
                        But if we apply 1v and 1.2v, the comparator can generate right result. 
                        Infact if we apply 1 and 1.006v then also it can produce the right o/p with very high accuracy.
 ```
                    
2. This lower range issue will create a huge problem for some other circuits also like for a good 10 bit SAR ADC we can't use this comparator specially in those circuits where   
   the supply is very low.
   
3. So I've developed another comparator where we're feeding the i/ps at the PMOS part in place of NMOS. 

4. Why I've taken this as a hope because the differential part is playing the major role in that issue. In that NMOS type comparator we're applying the i/ps to the gate terminal 
   of NMOS of the differential pair and we know that the Vth for NMOS is [~0.2-0.3]. So for lower values of i/p which are below or near about this range that comparator can't 
   operate in a right way.
5. But if we apply those i/ps to the PMOS gate then this problem will not be there since the 
                                Vth(PMOS) < Vth(NMOS)

6.So I've made the New comparator where in the differential block we'll apply the i/ps to the gate of PMOS  


 ## Differential Pair with 2 i/ps applied to PMOS where the En is the o/p of the single i/p differential block 

To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/mou3ananya/ComparatorIP
$  cd ComparatorIP/simulation/preLayout/
```


```
Open the compP.cir file. Here the difference between 2 i/p signals which that IP can detect is 8mV. You can take any other combinations for i/p voltages also by entering the i/p signals as shown in the image below.

```

 <p align="center">
  <img width="550" height="250" src="/Images/inputP.PNG">
</p>

Run the netlist file using the following command.

```
$  ngspice compP.cir
```

Observe the corresponding waveforms

### Inverting (v_n) and Non-inverting (v_p) i/p waveforms

<p align="center">
  <img width="1000" height="600" src="/Images/w_compP.PNG">
</p>

### En (Enable Active High) signal and o/p waveform

<p align="center">
  <img width="1000" height="600" src="/Images/w_compP1.PNG">
</p>


```
This sub-block itself acts as a comparator. 
```


## Issues | Improvements

 
1.  An important issue what I've met during simulation is the accuracy problem for the large i/p voltage range i.e. for [ > 2v] this range that comparator can't detect 
   the very small difference between inverting and non-inverting i/p.
   
 ```
                    Ex. If we apply 3v to one i/p and 3.08v to another then it can't detect this even 80mv large gap also.
                        But if we apply 0v and 0.08v, the comparator can generate right result that means it can detect that 80mv difference only when the applied i/p signal 
                        value is in very small range.
 ```
                    
2. This higher range issue will create a huge problem for some other circuits also for an example in a good 10 bit SAR ADC we can't use this comparator specially in those circuits where the supply is large enogh.  
    
3. So I've developed the final comparator shown in the 1st section of this repository where I've merged both the above mentioned comparators with some other circuitry where I've 
   managed the below functional logic:     
   
```
           If i/p voltage range is < 0.5v then PMOS type comparator will be active
                                   > 0.5v then NMOS type comparator will be active
```                                   
           

## CMOS Inverter block 
To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/mou3ananya/ComparatorIP
$  cd ComparatorIP/simulation/preLayout/
```


```
Open the inverter.cir file.You can take any other values for i/p voltage by entering the i/p signal as shown in the image below.

```

 <p align="center">
  <img width="550" height="250" src="/Images/inputINV.PNG">
</p>

Run the netlist file using the following command.

```
$  ngspice inverter.cir
```

Observe the corresponding waveform

### i/p - o/p waveforms

<p align="center">
  <img width="1000" height="600" src="/Images/w_inverter.PNG">
</p>


## CMOS OR Logic block
To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/mou3ananya/ComparatorIP
$  cd ComparatorIP/simulation/preLayout/
```


```
Open the OR.cir file.You can take any other combinations for i/p voltages by entering the i/p signals as shown in the image below.

```

 <p align="center">
  <img width="550" height="250" src="/Images/inputOR.PNG">
</p>

Run the netlist file using the following command.

```
$  ngspice OR.cir
```

Observe the corresponding waveform

### i/p - o/p waveforms

<p align="center">
  <img width="1000" height="600" src="/Images/w_or.PNG">
</p>


## Layout

### Layout of Complete Comparator IP

 <p align="center">
  <img width="1200" height="600" src="/Images/comp_lay.PNG">
</p>


### Layout of Inverter Block

 <p align="center">
  <img width="550" height="950" src="/Images/blk2_L.PNG">
</p>


### Layout of CMOS OR Logic Block
 <p align="center">
  <img width="1200" height="600" src="/Images/blk3_L.PNG">
</p>


### Layout of Differential Pair with En pin and single i/p applied to NMOS along with biasing circuit
 <p align="center">
  <img width="1200" height="600" src="/Images/blk4_L.PNG">
</p>


### Layout of Differential Pair with En pin and single i/p applied to PMOS along with biasing circuit
 <p align="center">
  <img width="1200" height="600" src="/Images/blk5_L.PNG">
</p>


### Post Layout Simulation

To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/mou3ananya/ComparatorIP
$  cd ComparatorIP/simulation/postlayout/
```

Open the mag file using the following command to get the layout.


```
$  magic -T SCN6M_SUBM.10.tech comparatoR.mag
```


Open the comparatoR.spice file.You can take any other combinations for i/p voltages by entering the i/p signals as shown in the image below.


 <p align="center">
  <img width="550" height="250" src="/Images/inputL.PNG">
</p>

Run the netlist file using the following command.

```
$  ngspice comparatoR.spice
```

Observe the corresponding waveforms

<p align="center">
  <img width="1000" height="600" src="/Images/w_compL1.PNG">
</p>



<p align="center">
  <img width="1000" height="600" src="/Images/w_compL2.PNG">
</p>














## Open-Source VLSI Tools


<img align="left" width="60" height="50" src=/Images/ng_logo.PNG>

## About Ngspice 
Ngspice is an open source mixed-signal circuit simulator.

### Installing Ngspice

#### For Ubuntu

Open your terminal and type the following to install Ngspice
```
$  sudo apt-get install -y ngspice
```

<img align="left" width="70" height="50" src=/Images/magic.PNG>

## Magic
 
 Magic is a VLSI layout tool. 

Type the following to install Magic in Ubuntu
```
$  wget http://opencircuitdesign.com/magic/archive/magic-8.3.54.tgz
$  tar xvfz magic-8.3.54.tgz
$  cd magic-8.3.54
$  ./configure
$  sudo make
$  sudo make install
```

## Issues | Improvements | Future Work
1. After layout the precision is not that high as in the case of prelayout. I've to take care of the layout part to get the more accuracy in operation.
2. I've designed this comparator for a fixed bias current and for that biasing purpose I've used 50k resistor. I'll try to replace that by a small resistor to reduce the power 
   consumption of the circuit as well as to increase the speed of response.
   

## Contributors 

- **Ananya Ghorai**
- **Kunal Ghosh** 


## Acknowledgments

- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
- Philipp Gühring, Software Architect, LibreSilicon Assocation
- Sheryl Serrao, Undergraduate Student, Mumbai University 
- Shalini Priya, M.Tech Embedded System, NIT Jamshedpur 
- Uday Vempalli, Undergraduate Student,Siddhartha Institute Of Technology


## Contact Information

- Ananya Ghorai, Pursuing M.Tech in VLSI Design, IIT(ISM) Dhanbad, ananyaghorai.2012@gmail.com
- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com
- Philipp Gühring, Software Architect, LibreSilicon Assocation pg@futureware.at











