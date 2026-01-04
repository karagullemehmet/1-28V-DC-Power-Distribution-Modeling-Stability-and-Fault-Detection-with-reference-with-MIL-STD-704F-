28V DC Power Distribution Modeling and Fault Detection

MATLAB / Simulink – Model-Based Design

Project Overview

This repository contains a model-based simulation of a 28 V DC power distribution system developed in MATLAB/Simulink.
The project focuses on analyzing voltage stability, current behavior, and fault response of the DC bus under different operating and fault conditions.

The model is intended for system-level analysis and validation prior to real hardware testing.

System Description

The electrical system is modeled using Simscape Electrical and includes:

28 V DC power source

Source resistance and line inductance

Normal and heavy load conditions

Fault paths for short circuit, open circuit, and ground fault

Voltage and current sensing blocks

The architecture represents a simplified aircraft or heavy-duty DC power distribution system.

Fault Scenarios

The following scenarios are simulated and evaluated:

Normal operation

Heavy load condition

Short circuit fault

Open circuit fault

Ground fault condition

Each scenario is activated based on a predefined time schedule to observe both transient and steady-state responses.

Measurement Chain Modeling

A realistic ECU-side voltage measurement chain is implemented, including:

Voltage divider

ADC quantization

Noise injection

Low-pass filtering

This structure allows evaluation of how measurement imperfections affect fault detection reliability.

Voltage Fault Detection Logic

A voltage fault detection algorithm is implemented with:

Undervoltage threshold: 22 V

Overvoltage threshold: 29 V

Hysteresis to prevent fault chattering

Debounce timers to avoid false triggering due to transients and noise

The threshold values are selected according to MIL-STD-704F normal operating limits.

Fault Classification and Management

Faults are classified using combined voltage and current information to distinguish between:

Short circuit

Open circuit

Ground fault

Normal operation

A Stateflow-based fault manager is used to manage fault priorities, timing, and recovery behavior.

Simulation Results

Simulation results include:

DC bus voltage and current under all scenarios

Measured voltage compared with MIL-STD-704F limits

UV and OV fault flags

Fault classification output

The results confirm stable fault detection behavior and correct classification under dynamic conditions.
