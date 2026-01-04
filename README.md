⚡ 28V DC Power Distribution Modeling and Fault Detection

Model-Based Design using MATLAB/Simulink

📌 Project Overview

This project presents a model-based analysis of a 28V DC power distribution system using MATLAB/Simulink.
The model is developed to evaluate voltage stability, current behavior, and fault responses under both normal and faulty operating conditions.

The study follows an aerospace-oriented design approach, aligned with MIL-STD-704F voltage limits, and demonstrates how power distribution faults can be detected and classified before real hardware testing.

🧩 System Description

The electrical system is modeled using Simscape Electrical and includes:

28V DC voltage source with internal impedance

Source resistance and line inductance

Normal and heavy load conditions

Fault injection blocks for:

Short circuit

Open circuit

Ground fault

Both bus voltage and bus current behaviors are monitored throughout the simulation.

⚠️ Fault Injection Scenarios

The following operating scenarios are simulated using predefined time schedules:

Normal operation

Heavy load condition

Short circuit fault

Open circuit fault

Ground fault condition

Each scenario is applied dynamically to observe transient and steady-state responses.

🔍 Sensor and Measurement Chain Modeling

A realistic voltage measurement chain is implemented to represent ECU-side sensing:

Measurement Components

Voltage divider

ADC quantization (finite resolution)

Noise and EMI injection

Low-pass filtering (signal conditioning)

This structure allows evaluation of how measurement imperfections affect fault detection accuracy.

🚨 Voltage Fault Detection Logic

A voltage fault detection algorithm is implemented using a MATLAB Function block with:

Undervoltage (UV) threshold: 22 V

Overvoltage (OV) threshold: 29 V

Hysteresis to prevent chattering

Debounce logic to avoid false triggering due to noise

Thresholds are selected according to MIL-STD-704F normal operating limits.

🧠 Fault Classification Logic

Faults are classified using voltage and current characteristics:

Fault Type	Voltage Behavior	Current Behavior
Short Circuit	Voltage collapse	High current
Open Circuit	Voltage rise	Near-zero current
Ground Fault	Voltage drop	Moderate current

This logic enables clear differentiation between fault types.

🔄 Fault Manager (Stateflow)

A Stateflow-based fault manager is designed to:

Handle fault priority

Manage detection timing

Control recovery behavior

Prevent conflicting fault states

This structure mimics ECU-level fault handling logic used in real systems.

📊 Simulation Results

Simulation results include:

DC bus voltage and current responses

Measured voltage compared with MIL-STD-704F limits

UV and OV detection flags

Fault classification output

Results confirm correct fault detection and classification under dynamic conditions.

UV and OV fault flags

Fault classification output

The results confirm stable fault detection behavior and correct classification under dynamic conditions.
