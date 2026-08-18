# 013 — Prototype Engineering and Measurement Plan

## Purpose
Define the first physical THERMA prototype as an experiment designed to falsify the model, not a miniature commercial product.

## 1. Prototype philosophy
Build the smallest fixed-hardware system that can demonstrate the core thermoacoustic mechanism with sufficient instrumentation to calculate thermal and acoustic performance.

## 2. Single-core strategy
The first prototype should use one core because a single instrumented unit is easier to understand, modify and correlate than a multi-core industrial machine.

## 3. Hardware boundary
The prototype includes pressure boundary, resonator, regenerator, heat exchangers, working gas system, secondary thermal loops, sensors, control and safety hardware.

## 4. No mechanical moving power train
No piston, crankshaft, flywheel, connecting rod, or reciprocating compressor belongs in the core. External pumps and valves may move process fluids.

## 5. Geometry freeze
Before fabrication, freeze resonator dimensions, chamber volumes, cross-sectional areas, regenerator geometry, exchanger geometry, ports, gas inventory and mounting interfaces.

## 6. Model-to-CAD traceability
Each manufactured dimension should trace to a model parameter, drawing revision and tolerance. Hand-edited or image-derived dimensions are not authoritative.

## 7. Working gas
Select gas and pressure from the validated model. Helium is a candidate, but final selection must consider power, leakage, cost and availability.

## 8. Pressure vessel
Pressure design must be done by a qualified engineer and follow the applicable pressure-vessel code path.

## 9. Heat source
Select a favorable heat source for the first proof-of-physics, preferably in the historical 80–120 C development band unless exact modeling demonstrates another point.

## 10. Heat-source conditioning
Use a secondary heat-transfer loop so the prototype sees a controlled temperature rather than an uncontrolled industrial stream.

## 11. Cold load
The first cooling test should use a controlled thermal load with known heat capacity and flow rather than an uncontrolled room.

## 12. Hot load
For heating mode, a controlled water loop can measure hot-side power with flow and temperature rise.

## 13. Heat rejection
Choose a stable sink, such as a controlled water loop, to minimize ambient uncertainty during initial tests.

## 14. Instrumentation list
Minimum channels: hot source temperature/flow, cold side temperature/flow, rejection temperature/flow, mean pressure, acoustic pressure, frequency, phase and electrical auxiliaries where applicable.

## 15. Sensor calibration
Every critical sensor should have a calibration record and uncertainty estimate.

## 16. DAQ architecture
Synchronize acoustic measurements with thermal and flow measurements. Slow thermal channels and fast acoustic channels can use different sampling rates if time alignment is preserved.

## 17. Safety sensors
Independent high-pressure, high-temperature and low-flow protection should be available before high-power testing.

## 18. Emergency bypass
The source loop must have a physical bypass or isolation route so heat can be removed from the core during abnormal conditions.

## 19. Pressure relief
Relief device sizing and set pressure belong to the qualified pressure design, not a casual simulation assumption.

## 20. Leak test
Before charging the working gas, perform a leak test appropriate to the pressure system and chosen gas.

## 21. Initial commissioning
Begin at low thermal input, verify temperature paths and pressure stability, then increase the gradient gradually.

## 22. Acoustic onset test
Identify whether the expected mode appears at the predicted frequency range. Record amplitude growth and stability.

## 23. Resonance mapping
Sweep frequency or operating condition while measuring acoustic amplitude, phase and delivered power where safe.

## 24. Mean pressure mapping
Test a controlled set of mean pressures if the design allows it. This helps identify the power-density tradeoff.

## 25. Thermal gradient mapping
Measure the hot and cold node temperatures across different source conditions to determine the practical onset and operating window.

## 26. Heat-engine test
Measure thermal input and acoustic power generated. This isolates the engine conversion before attaching a demanding refrigerator load.

## 27. Refrigerator test
Connect the acoustic power to the refrigeration section and measure cold-side heat removal and rejection heat.

## 28. Heating test
Use acoustic work to operate the heat-pump side and measure hot-water power, source-side heat extraction and any electrical input.

## 29. Reversible test
Demonstrate cooling → neutral → heating and the reverse while monitoring pressure, temperature, frequency and stability.

## 30. Rapid mode test
Use a defined thermal mass and measure actual pull-down time. Do not use an unbounded “room feels cold” criterion.

## 31. Steady-state test
After pull-down, measure maintenance power and temperature stability for an extended run.

## 32. Load step
Apply step changes in thermal load and record settling time, overshoot and recovery.

## 33. Source step
Change source temperature or thermal power within safe limits and measure response.

## 34. Sink step
Change heat-rejection conditions to understand how ambient or sink temperature affects performance.

## 35. Flow step
Change secondary-loop flow and measure heat-transfer response and pressure drop.

## 36. Acoustic drive step
For driven development configurations, vary acoustic drive and measure response without exceeding validated limits.

## 37. Loss accounting
Calculate source thermal input, acoustic work, useful thermal output and rejected heat. The difference reveals measured losses and uncertainty.

## 38. Instrument uncertainty
Propagate uncertainty from temperature sensors, flow meters, pressure sensors and power meters into thermal power and COP calculations.

## 39. Repeatability
Repeat each key operating point multiple times to separate random variation from systematic error.

## 40. Hysteresis
Run increasing and decreasing source-temperature or pressure sweeps to reveal hysteresis or thermal memory effects.

## 41. Endurance
Operate through repeated thermal and acoustic cycles to monitor drift, leaks, vibration and regenerator/exchanger degradation.

## 42. Inspection
After endurance, inspect pressure boundary, matrix, heat exchangers, seals, joints and instrumentation.

## 43. Failure injection
Where safe, test controlled low-risk faults such as sensor disagreement, reduced flow or source interruption to verify the control-state machine.

## 44. High-temperature fault test
Do not inject actual 1500 C fluid. Validate the protection architecture through a safe surrogate transient or instrumented shutdown test that demonstrates diversion logic.

## 45. Model correlation
Compare predicted frequency, pressure amplitude, temperatures, flow and thermal power with measurements using the same boundary definitions.

## 46. Error metrics
Use clearly defined relative or absolute error metrics. Predeclare acceptable correlation bands for each key variable.

## 47. Redesign trigger
If a critical measured variable falls outside the model envelope, determine whether the cause is geometry, material, loss, instrumentation or model deficiency.

## 48. Regression
After any redesign, repeat the canonical test matrix. A new version is not accepted because one metric improved if another safety or performance metric regressed.

## 49. Prototype gate
A successful gate requires containment, acoustic stability, useful thermal transfer, safe controls, repeatability and model correlation.

## 50. Closing principle
The first prototype should answer the most important unknowns with measurements. Every component and test exists to convert a model hypothesis into defensible engineering evidence.
