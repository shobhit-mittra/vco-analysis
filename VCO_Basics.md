# VCO Basics :

Oscillators are used in various applications, including laptop and smartphone processors for generating clock signals, radio, and mobile receivers for generating local carrier frequencies, and signal generators in labs to test circuits. Oscillators generates periodic AC signals of varying frequencies when given a DC voltage and the output can be either sinusoidal or non-sinusoidal. The main concept of oscillator revolves around the fact that they do not require an active input for operation. The block diagram of oscillators can be examined in the fig1. An oscillator consists of an amplifier and a positive feedback circuit, where the feedback takes the amplified circuit to another input of the circuit, forming a closed loop. The feedback signal determines the stability of sustainable oscillations. Thermal noise provided by every circuit gives an initial boost to the amplified output, leading to the establishment of oscillations at the output. The loop gain Aβ and phase shift are crucial factors for sustained oscillations, and their relationship is mathematically proven.

![Fig.1 Oscillator Block Diagram](/images/theory/Oscillator_Block.png)

- Fig.1 Oscillator Block Diagram

The VCO is an oscillator whose frequency can be controlled by an external voltage. This makes it easier and more convenient to tune compared to conventional oscillators that require manual adjustment of passive components like resistors, capacitors, and inductors. The pitfalls of using passive components like R,L,C are countered by VCO. The passive components contribute to greater area in the overall circuit that affects the overall performance of the design. A VCO can be used in various applications, such as communication systems, modulation and demodulation circuits, phase-locked loops(PLLs), frequency synthesisers, and function generators. <br/>

VCOs are of mainly two types: <b>Harmonic Type-Oscillators </b> (RC, LC and Crystal Oscillators) and <b>Relaxation type-Oscillators</b>. Harmonic oscillators generate sinusoidal signals, while relaxation oscillators generate either a square, triangular, or sawtooth wave. Any Harmonic Oscillator can be converted into VCO by replacing the resistance or capacitance with a voltage-controlled element, like a varactor diode. Varactor diode is an electronic component that can vary its capacitance by varying the applied voltage across the component. The frequency of an RC or LC oscillator is proportional to 1/√C, and for the varactor diode as we increase the voltage, the capacitance of the diode will reduce. Mathematically, the square root relationship in the equation (eq. 1) explains how changing the reverse voltage across a varactor diode affects its capacitance. As the reverse voltage increases, the capacitance decreases, and as the reverse voltage decreases, the capacitance increases, making varactor diodes useful in applications where voltage-controlled capacitance is required.
<br/>

$C(v)=  C_0⁄((1+(V/V_0 )^m )     (1)$
<br/>

Where, $C(V)$ is the capacitance at voltage V. $C0$ is the zero-bias capacitance (capacitance at V = 0). $V0$ is the built-in potential, a constant for the diode. $m$ is an empirical exponent typically between 1/2 and 1. Hence, the increase in the control voltage leads to the frequency of oscillation to increase too, as shown in the graph as under. 

 ![Fig2. Graph depicting voltage vs freq for Ahrmonic oscillator](/images/theory/graph_fvV.png)

 Mathematically, the frequency of oscillation can be given by equation (eq 2.),
 <br/>
 
$f(t) = f0 + K Vc(t)	  (2)$
<br/>

Where, $f0$ is the nominal frequency of oscillation, $Vc$ is the control voltage and $K$ is known as the tuning gain. The tuning gain or tuning sensitivity of the VCO defines the amount by which the frequency of oscillation will change when the control voltage is varied by 1V, and it is defined by the unit of Hz/V.
<br/>

Relaxation type VCOs involve varying the charging current of the capacitance in oscillator to tune the frequency. The figure below shows a simple block for relaxation based-vco. In these types of oscillators the charging current is directly proportional to the tuning voltage i.e $Iref ∝ Vtune$

![Fig. 3 Block for Relaxation VCO](/images/theory/relax_osc.png)

<br/>
The specification of VCO involves the tuning range, tuning sensitivity, supply pushing, load pulling, and spectral purity are important specifications to consider when selecting a VCO for specific applications. The frequency of a VCO can be tuned over a certain range by changing the control voltage, and its output frequency can be affected by changes in both supply voltage and load. VCOs with a high Q-factor can minimise these effects. Phase noise is a measure of the purity of the output signal of a VCO. VCOs with lower phase noise, have a purer output signal, are used for modulation and demodulation in communication systems. The phase noise is measured with respect to the carrier power at certain offsets from the carrier frequency and is represented in the unit of dBc / Hz.


