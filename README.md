28V DC Power Distribution System Modeling and Fault Detection

MATLAB / Simulink – Model-Based Design

Overview

This project presents a model-based simulation of a 28V DC power distribution system commonly used in aircraft and heavy-duty electrical architectures.
The system is modeled and analyzed in MATLAB/Simulink using Simscape, focusing on voltage stability, current behavior, and fault handling under different operating conditions.

The model allows early verification of power integrity and fault detection logic before real hardware testing.

System Architecture

The simulated system includes:

28V DC power source

Source resistance and line inductance

Load branches (normal load, heavy load)

Fault injection paths (short circuit, open circuit, ground fault)

Return path resistance

Voltage and current sensors

The electrical network is implemented using Simscape Electrical, while measurement and logic blocks are implemented in Simulink.

Fault Injection Scenarios

The following fault conditions are simulated:

Normal operation

Heavy load condition

Short circuit fault

Open circuit fault

Ground fault

Each scenario is activated based on a time schedule, allowing clear observation of transient and steady-state responses.

Sensor and Measurement Chain

A realistic measurement chain is modeled to represent ECU-side sensing:

Voltage sensing using a voltage divider

ADC quantization (finite resolution)

Noise and ripple injection

Low-pass filtering for signal conditioning

This approach allows evaluation of how real measurement imperfections affect fault detection.

Voltage Fault Detection Logic

A voltage fault detection algorithm is implemented with:

Undervoltage (UV) threshold: 22 V

Overvoltage (OV) threshold: 29 V

Hysteresis to prevent chattering

Debounce timers to avoid false triggering due to transients and noise

The logic ensures stable and realistic fault detection behavior.

Fault Classification

Based on measured voltage and current characteristics, the system classifies faults into:

Normal operation

Short circuit

Open circuit

Ground fault

This classification logic represents a simplified ECU diagnostic strategy.

Stateflow Fault Manager

A Stateflow-based fault manager is implemented to:

Handle fault priorities

Control fault latching and recovery

Manage transitions between fault states

This structure reflects real-world embedded fault management architectures.

Simulation Results

Key results include:

DC bus voltage and current under each fault scenario

Measured voltage compared with MIL-STD-704F normal limits

ADC-level voltage behavior

UV and OV detection flags

Fault classification output over time

The results show that the system correctly detects and classifies faults while remaining stable under normal conditions.

Standards Reference

The voltage limits and evaluation approach are aligned with:

MIL-STD-704F (28V DC aircraft power systems)

This project focuses on behavioral compliance and system understanding, not formal certification.

Tools Used

MATLAB

Simulink

Simscape Electrical

Stateflow

Conclusion

This project demonstrates how model-based design can be used to analyze a 28V DC power distribution system, including fault behavior and diagnostic logic, before real hardware testing.

The developed model provides a strong foundation for:

ECU algorithm development

Fault diagnostic validation

Extension to Hardware-in-the-Loop (HIL) testing

Integration with real embedded controllers

Future Work

Possible extensions include:

Hardware-in-the-loop (HIL) implementation

Real ECU communication (CAN-based diagnostics)

Thermal effects and aging models

EMI/EMC-focused disturbance modeling
