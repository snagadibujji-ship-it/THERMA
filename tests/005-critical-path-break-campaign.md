# THERMA 3.5 — Critical-Path Break Campaign

## Purpose

This test campaign attacks the exact-geometry baseline instead of assuming success. The objective is to determine whether a fixed-hardware thermoacoustic architecture can preserve a useful operating window after geometry, regenerator, heat-exchanger, temperature-head, acoustic-power, fatigue, and control constraints are coupled.

## Locked baseline under attack

- Working gas: helium
- Mean pressure: 1.0 MPa
- Nominal frequency: 100 Hz
- Resonator cross-sectional diameter: 50 mm
- First-order quarter-wave reference length: about 2.55 m before end corrections and impedance-network changes
- Regenerator length: 100 mm
- Nominal regenerator gap: 0.50 mm
- Hot heat-exchanger length: 120 mm
- Cold heat-exchanger length: 120 mm
- Nominal drive ratio: 5%
- Source temperature: 100 °C
- Sink temperature: 35 °C
- Cold target: 3 °C

These are screening assumptions, not validated THERMA specifications.

## Test family A — acoustic geometry

### A1 Resonator length perturbation
Vary reference length by -20%, -10%, -5%, nominal, +5%, +10%, +20%. Record frequency shift, impedance mismatch risk, and estimated acoustic-power sensitivity.

### A2 Cross-section perturbation
Vary resonator area by 0.5x, 0.75x, 1x, 1.25x, 1.5x. Track acoustic velocity, pressure amplitude, viscous loss tendency, and packaging implications.

### A3 Junction-loss stress
Insert hypothetical area steps and bend sections. Treat each as added acoustic impedance. The system fails the screening gate if small routing changes cause large power collapse.

### A4 End-correction uncertainty
Apply plausible end corrections to the quarter-wave reference. Do not treat the simple c/(4f) length as a final geometry.

### A5 Temperature-dependent sound speed
Recompute resonance over the expected gas-temperature envelope. The machine must either tolerate detuning or provide a control/tuning mechanism.

## Test family B — regenerator

### B1 Gap sweep
Sweep thermal gap from 0.25 to 2.0 mm. Compare thermal coupling tendency, viscous loss tendency, and manufacturability.

### B2 Porosity sweep
Sweep porosity across a realistic matrix range. Identify pressure-drop and heat-capacity tradeoffs.

### B3 Length sweep
Sweep regenerator length from 50 to 200 mm. Look for a broad optimum instead of a knife-edge point.

### B4 Conductivity sweep
Vary effective matrix conductivity from low to high. Flag thermal-short-circuit risk when conduction erodes the imposed gradient.

### B5 Degradation case
Reduce effective heat-transfer coefficient by 10%, 25%, 40%, 60%. Determine whether the architecture gracefully degrades or abruptly loses operation.

## Test family C — oscillatory heat exchangers

### C1 Area reduction
Reduce hot and cold HX transfer area by 10%, 25%, 50%. Track thermal-span collapse and acoustic penalty.

### C2 Approach-temperature stress
Increase both HX approach temperatures. Determine when the required source/sink head becomes impossible for the target output.

### C3 Fouling stress
Model effective conductance reduction at 10%, 20%, 30%, 50%.

### C4 Flow restriction
Increase secondary-loop pressure drop. Check auxiliary-power and temperature-lift penalties.

### C5 Asymmetry
Degrade only the hot HX or only the cold HX. Determine which side is the dominant bottleneck.

## Test family D — temperature head

### D1 Source sweep
Evaluate 60, 70, 80, 90, 100, 120, 150, 200 °C.

### D2 Sink sweep
Evaluate sinks from 25 to 55 °C.

### D3 Cold-target sweep
Evaluate 0, 3, 5, 10 °C.

### D4 Combined unfavorable case
Use low source, high sink, and low cold target simultaneously. This is a primary break test.

## Test family E — acoustic power density

### E1 Drive-ratio sweep
Sweep 1%, 2%, 3%, 5%, 7%, 10%. Treat the resulting pressure amplitude and power estimates as screening only.

### E2 Mean-pressure sweep
Sweep 0.5, 1, 2, 3 MPa. Record higher power-density benefits against pressure-system burden.

### E3 Frequency sweep
Sweep around resonance ±30%. Measure how quickly estimated acoustic power collapses away from the optimum.

### E4 Nonlinear threshold
Increase drive ratio until the reduced-order model assumptions become questionable. Flag rather than extrapolate beyond model validity.

## Test family F — fatigue

### F1 Acoustic-cycle count
At 100 Hz, approximate cycles/year as 3.15 billion. Repeat for 75 and 125 Hz.

### F2 Pressure-amplitude scaling
Convert pressure amplitude assumptions into cyclic stress inputs for the pressure boundary. Do not claim material life without qualified geometry and S-N data.

### F3 Thermal cycling
Apply repeated source-temperature excursions. Examine thermal-strain mismatch at HX, weld and structural interfaces.

### F4 Combined fatigue
Combine pressure and thermal cycles conceptually. Flag the need for code-based fatigue assessment before prototype fabrication.

## Test family G — control faults

### G1 Temperature sensor bias
Apply ±2, ±5 and ±10 °C sensor error.

### G2 Pressure sensor bias
Apply plausible pressure-measurement offsets and delayed detection.

### G3 Flow sensor failure
Force lost, frozen and noisy readings.

### G4 Valve failure
Simulate stuck-open and stuck-closed external thermal valves.

### G5 Pump failure
Remove secondary-loop flow and verify that the safe-state logic isolates the core.

### G6 Simultaneous faults
Combine sensor bias, reduced HX conductance and elevated source temperature. This tests whether the controller is robust to imperfect information.

## Test family H — extreme inputs

### H1 Source overshoot
Apply source temperatures above the nominal design envelope and require upstream conditioning before the core.

### H2 1500 °C accidental stream
The raw stream must never contact the THERMA core. Pass condition is upstream isolation/diversion or a separately qualified high-temperature recovery exchanger.

### H3 Cold-start
Start with near-ambient working gas and secondary loops. Check for unstable transients and control lockout requirements.

### H4 Hot shutdown
Remove the source while the acoustic field is active. Check neutral-state and thermal-relaxation requirements.

## Test family I — scaling

### I1 Single-core to module array
Do not assume linear scaling. Account for shared headers, acoustic isolation, thermal rejection, controls and common-mode faults.

### I2 Ten-core array
Test the idea of modular fault tolerance: loss of one core should degrade capacity rather than cause uncontrolled failure.

### I3 Hundred-core conceptual scaling
Use only as an architecture stress case. No MW claim is accepted without measured module power density.

## Test family J — economics

### J1 Waste-heat source
Treat the thermal source as low marginal cost and compare only the remaining capital and auxiliary burdens.

### J2 Electric resistance source
Model electricity-to-heat-to-thermal conversion and compare against direct electric compression. This is expected to be a weak economic case.

### J3 Utilization factor
Stress annual utilization from very low duty cycles to near-continuous industrial operation.

### J4 Maintenance burden
Add replacement of service modules, helium service, HX refurbishment, instrumentation and downtime.

## Break criteria

The architecture is considered to have reached a fundamental weakness if any of the following occur consistently under credible assumptions:

1. No stable acoustic operating window remains after realistic geometry tolerances.
2. Regenerator losses eliminate useful temperature span.
3. Oscillatory HX losses dominate available acoustic power.
4. Source/sink temperature head is insufficient for the target mode.
5. Required acoustic pressure drives the pressure boundary into an unreasonable qualification regime.
6. Fatigue demand becomes incompatible with the intended service strategy.
7. Control faults cannot drive the system to a safe state.
8. Practical cooling/heating capacity is too low for the intended product class.
9. Scaling destroys the economics or thermal routing before useful capacity is achieved.

## Interpretation rule

A failed screening case does not prove that all thermoacoustic systems fail. It proves only that the tested THERMA assumptions are inadequate for that operating case.

## Required next step

If the baseline survives this campaign, the next stage is exact-geometry high-fidelity modeling using a reproducible acoustic/thermal model and a clearly documented geometry. If it fails, redesign only the parameter responsible for the failure and rerun the entire affected regression set.

## Final status

This document is a stress-test protocol and screening record. It is not a substitute for CFD, DeltaEC/SAGE-style exact-geometry modeling, structural FEA, pressure-vessel code calculations, material qualification, or physical testing.