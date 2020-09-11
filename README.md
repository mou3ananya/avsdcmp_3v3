# ComparatorIP
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
  <img width="850" height="550" src="/Images/comp_blk.jpg">
</p>



### Internal Block Diagram of the Comparator IP

The Comparator IP is built using 5 important sub-blocks:
1. [Biasing Circuit](#biasing-circuit)
2. [Differential Pair with level shifter where i/p is applied to NMOS](#differential-pair-with-level-shifter-where-i/p-is-applied-to-nmos)
3. [Differential Pair with level shifter where i/p is applied to PMOS](#differential-pair-with-level-shifter-where-i/p-is-applied-to-pmos)
4. [CMOS Inverter circuit](#cmos-inverter-circuit)
5. [CMOS OR Logic circuit](#cmos-or-logic-circuit)




 <p align="center">
  <img width="900" height="550" src="/Images/comp_int.PNG">
</p>



## Circuit Diagram of the Comparator IP

 <p align="center">
  <img width="1200" height="500" src="/Images/NEW_C/cir_dac.png">
</p>

### Subcircuits within the Comparator IP

<p align="center">
  <img width="850" height="550" src="/Images/NEW_C/cir_comp.png">
</p>

## Running the Simulation


To enter the Ngspice Shell, open the terminal & type:
```
$ ngspice
```
To simulate a netlist, type:
```
ngspice 1 ->  source <filename>.cir
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
$  git clone https://github.com/ADC-TEAM2020/SAR_ADC
$  cd SAR_ADC/Simulation/PreLayout_v1.0/
```

<p align="center">
  <img width="1200" height="600" src="/Images/transfer.png">
</p>

### Pre-Layout Simulation result for each block





