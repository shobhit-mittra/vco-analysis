# Inverter-Based VCO 

This section contains the idealogy, design and methodology behind the design of VCO using CMOS-based inverters as a ring oscillator.
<br/>

## Overview : 
The inverter-based Voltage-Controlled Oscillator (VCO) design uses a cascade of inverter stages, forming a ring-oscillator circuit. Feedback is established by looping the output of the final inverter back to the input of the initial inverter. VCO functionality is achieved by modulating the number of inverters in the cascade, which affects the charging time within the inverter module and propagation delay. An odd number of inverters is necessary in the ring-oscillator stage to sustain oscillation effectively, ensuring a phase shift of 180 degrees with each inverter. However, the design also has challenges, particularly concerning power consumption. As more stages are incorporated, switching activity increases, resulting in elevated power consumption. This is particularly important in battery-operated devices, where minimizing power consumption is crucial for battery life. Engineers must balance achieving desired oscillation characteristics with managing power dissipation.
<br/>

$P ∝ N*Vdd^2$
<br/>

This relationship underscores the direct proportionality between power dissipation and the square of the supply voltage, emphasizing the need for thoughtful design considerations to optimize the performance of inverter-based VCOs in various electronic applications.

## Circuit Design :

The circuit diagram of inverter based VCO in the LTspice environment is given as under :

![](/images/theory/vco_design.png)

## Methodology : 

The circuit consists of a five-inverters as a ring oscillator stage. Fout is the feedback to the initial inverter in the cascaded stage. The nmos and pmos present in the inverter are connected via an individual set of nmos-pmos pair respectively instead of directly providing a ground and Vdd respectively. The reason for this arrangement is firstly to increase the load of the Pull-up and pull-down network , and secondly to restrict the current flow across the inverters that further plays a role in varying the frequency. The input control voltage Vin is given to a CS-Amplifier stage that has a diode-connected PMOS load attached to improve the gain of the system. The second voltage source is the Vdd supply that defines the upper limit of the amplitude of the oscillations. The lower limit of the amplitude is defined by the common ground (Vss = 0V). Finally, there are buffer stages implemented as inverters after the output stage of cascaded inverters (Fout). This segment of the circuit acts as a wave-shaping stage as it alters the charging and discharging rates that results in an approximate rectangular wave.

