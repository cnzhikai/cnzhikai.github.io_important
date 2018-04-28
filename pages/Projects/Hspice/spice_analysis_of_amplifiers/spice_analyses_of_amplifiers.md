---
title: Spice Analysis of Amplifiers
audience: 
tags: 
keywords: 
last_updated: Apr 28, 2018
sidebar: spice_sidebar
permalink: spice_analyses_of_amplifiers.html
folder: courses
---

# 1 CS Stage with diode-connected load

## 1.1 Theoretical Analysis

![](/pages/Projects/Hspice/spice_analysis_of_amplifiers/A1_1.eps)

![](/pages/Projects/Hspice/spice_analysis_of_amplifiers/A1_Page_01.jpg)

<div align="center"><img width="65" height="75" src=""/pages/Projects/Hspice/spice_analysis_of_amplifiers/A1_1.eps></div>

Assume the threshold voltage of NMOS and PMOS is 500mV. Because the gain of this amplifier is small, the input voltage defines the range of input that makes both two transistors works at saturation region, and the output range can be obtained from the input range.

To make both NMOS and PMOS saturate, the input voltage should satisfy these conditions,

<center>
![](https://latex.codecogs.com/gif.latex?%24%24V_%7Bin%7D%3EV_%7Bth%2Cn%7D%24%24%5C%5C%20%24%24V_%7Bin%7D%3CV_%7Bth%2Cn%7D&plus;V_%7Bout%7D%24%24)
</center>

We can easily get the range of input and output through the simulation result.

With the following equation,

<center>
![](https://latex.codecogs.com/gif.latex?A_%7Bv%7D%3D-%5Csqrt%5Cfrac%7B%5Cmu_%7Bn%7D%28W/L%29_%7Bn%7D%7D%7B%5Cmu_%7Bp%7D%28W/L%29_%7Bp%7D%7D)
</center>

We can get estimated Av=-4.18.

And the optimist bias voltage can be set in the place where the gradient of the input-output curve is the biggest.

## 1.2 Netlist and Simulation Result

The netlist is as follows.

    Q1 CS Stage with diode-connected load
    
    **Netlist of devices
    .PARAM VGS=0.6
    
    M1 VOUT VOUT VDD VDD P18 W=2U L=0.18U
    M2 VOUT VIN 0 0 N18 W=10U L=0.18U
    CLOAD VOUT 0 10P
    
    **Stimulate sources
    VIN VIN 0 VGS
    VDD VDD 0 1.8
    
    **Analysis statements
    .OP
    .DC VIN 0 1.8 0.001
    
    **Output all node voltages and branch currents
    .PRINT
    
    **simulator options
    .OPTION LIST NODE BRIEF=1 runlvl=0
    
    .lib 'D:\HSPICE\model\model\model\ms018_v1p7.lib' TT
    
	.END

And the simulation result is shown below,

    **** mosfets
    
    
     subckt
     element  0:m1   0:m2  
     model0:p18  0:n18 
     region Saturati   Saturati
      id  -205.0224u  205.0224u
      ibs  1.233e-20  -1.074e-19
      ibd2.4291a   -1.6885f
      vgs   -1.2070   600.0000m
      vds   -1.2070   592.9524m
      vbs0. 0. 
      vth -478.3759m  482.0270m
      vdsat   -575.3755m  123.7686m
      vod -728.6717m  117.9730m
      beta 987.0615u   22.4507m
      gam eff  604.4742m  772.6493m
      gm   429.9220u2.2780m
      gds   25.8695u   68.8587u
      gmb  134.5588u  570.1076u
      cdtot  2.2470f   10.7345f
      cgtot  3.4856f   17.7014f
      cstot  4.8418f   22.7629f
      cbtot  4.1049f   19.6719f
      cgs2.5835f   12.4977f
      cgd  786.1125a3.5786f
    
## 1.3 Answering Questions

### 1.3.1 DC Analysis

<div align="center"><img width="65" height="75" src=""/pages/Projects/Hspice/spice_analysis_of_amplifiers/a2.jpg></div>


