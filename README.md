# PROJECT 1 
## Short Description
As part of our studies in the fifth semester of Electrotechnical Ingineering, we were tasked with designing a fully-discrete **Series Voltage Regulator** and preparing the PCB layout for manufacturing.

Key design targets were:
- Open-loop Gain (AOL) of at least 100
- Over-current protection
- Low output voltage thermal coefficient, preferably under 2mV/degree Celsius
- Variable output voltage between 9V and 14.4V, with minimal output voltage droop at a maximum load of 900 Ohms

More information about the design considerations, the safety margins and cosniderations can be found in the full report on the project, available <a href="https://github.com/Riggstadt/PROIECT_1_ETTI/blob/main/DOCUMENTATION/DOCUMENTATIE_P1_SERS_N18_RONCEA_TEODOR_VIRGIL_431C.pdf">here</a>

I choose a simple, yet robust topology for my voltage regulator circuit. The regulator is centered on a simple error amplifier, built upon a differential pair, with current mirror load and emitter degeneration. As control element, a high-power DPAK Bipolar Transistor was used, in conjuction with the resistive feedback network. The reference voltage source of the regulator is provided by a self-biased voltage reference.

<br>
  <p align="center">
    <img height = "550" src = "SIMULATIONS/LDO_OP.jpg">
    <br>
    <br>
    <a><b>Circuit schematic of the finalized Voltage Regulator, with corrections and improvements depicted</b></a>
</p>
<br>


The (to me) most interesting part of the whole circuit is the voltage reference block, a type of self-biased reference, with its design inspired by a similar subcircuit presented on Ken Sheriff's <a href="https://www.righto.com/2020/09/how-to-multiply-currents-inside.html">blog</a>, see Note #12 at the bottom of the article. The voltage reference is simplified to conform to the constraints on component numbers, but it still remains a stable reference, with low temeprature dependance and high ripple rejection.

The over-current protection network takes the form of a simple current limiter, with all components used having been confirmed to resist the maximum possible dissipated power.

