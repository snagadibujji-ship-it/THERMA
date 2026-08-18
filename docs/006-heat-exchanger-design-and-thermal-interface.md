# 006 — Heat Exchanger Design and Thermal Interface

## Purpose
This document defines the hot, cold and rejection heat-exchanger problem in THERMA and the relationship between oscillating gas, fixed thermal hardware and external secondary fluid loops.

## 1. Function
Heat exchangers convert the internal thermoacoustic thermal nodes into useful external thermal interfaces. They determine how much heat can actually enter or leave the acoustic core.

## 2. Boundary separation
The working gas should remain sealed from process water. A metal wall, plate, tube or other qualified thermal boundary separates the acoustic domain from the secondary loop.

## 3. Hot exchanger
The hot exchanger transfers energy between the source-conditioning loop and the hot thermal node. Its task is not simply to maximize conductance; it must also minimize acoustic and pressure losses.

## 4. Cold exchanger
The cold exchanger removes the refrigeration load from the cold-side loop and transfers the heat into the thermoacoustic cycle.

## 5. Rejection exchanger
The rejection exchanger exports heat to ambient air, water, a process sink or another useful thermal load.

## 6. Oscillatory flow
Acoustic gas motion reverses direction every cycle. This produces different boundary-layer behavior from steady pipe flow.

## 7. Correlation limitation
Steady-flow heat-transfer correlations should not be assumed valid without checking their applicability to the selected oscillatory geometry.

## 8. Geometry variables
Important variables include channel hydraulic diameter, length, plate spacing, fin spacing, porosity, area density, wall thickness, manifold volume and pressure loss.

## 9. Heat-transfer coefficient
The effective coefficient depends on gas properties, oscillation amplitude, frequency, geometry, temperature and surface condition. A constant coefficient used in a screening model must be labeled as an assumption.

## 10. Approach temperature
A finite temperature difference between gas and external fluid is required. Reducing approach temperature generally increases required exchanger area and cost.

## 11. Effectiveness
Effectiveness represents how closely the exchanger approaches an ideal limit under its chosen flow arrangement. It is not independent of flow rate and capacity ratio.

## 12. Counterflow
Counterflow arrangements can improve temperature approach and are often attractive for water loops. The actual design must still account for oscillatory gas-side behavior.

## 13. Crossflow
Crossflow can simplify packaging and air-side rejection but may require fan power and careful thermal distribution.

## 14. Plate exchangers
Brazed or gasketed plate structures provide high surface-area density but bring pressure, thermal-expansion and service considerations.

## 15. Shell-and-tube
Shell-and-tube exchangers are familiar industrial components and can tolerate demanding conditions, but their size and pressure drop may be significant.

## 16. Microchannel option
Microchannels can provide high area density but demand careful manufacturing, fouling control and pressure-drop management.

## 17. Material choice
Copper, stainless steels, high-temperature alloys and other materials may be considered depending on temperature and compatibility. The final choice requires material qualification.

## 18. Thermal expansion
Differential thermal expansion between plates, tubes, shells, frames and supports can produce stress and leakage paths.

## 19. Brazing
Brazed structures require qualified processes and inspection because a thermal or pressure failure can compromise the sealed acoustic boundary.

## 20. Welding
Pressure-containing welds require qualified procedures, inspection and code compliance appropriate to the final product.

## 21. Manifolds
Manifolds must distribute flow evenly. Poor distribution can create hot or cold spots and reduce exchanger utilization.

## 22. Acoustic reflection
Sudden changes in area or dense exchanger structures can reflect acoustic energy. The exchanger should be represented as part of the acoustic impedance network.

## 23. Acoustic resistance
The exchanger adds resistive loss. The best thermal exchanger is not necessarily the one with the highest raw conductance if it destroys acoustic power.

## 24. Pressure drop
Both acoustic and mean-flow pressure losses must be quantified. Pumps and pressure boundaries must be sized accordingly.

## 25. Heat leak
Exchanger supports and manifolds can conduct heat around the intended thermal path. These parasitic leaks matter especially at low temperature lift.

## 26. Insulation
Hot and cold sections should be insulated where uncontrolled heat exchange would degrade performance or create safety problems.

## 27. Condensation
A cold-side exchanger operating below dew point can accumulate condensate. Drainage, corrosion, electrical safety and contamination must be considered.

## 28. Fouling
Industrial fluids can foul heat-transfer surfaces. A commercial architecture must include service and cleaning strategy.

## 29. Air-side rejection
Air-cooled rejection requires finned surfaces and fans. Fan power is auxiliary electricity and must be included in system economics.

## 30. Water-side rejection
Water cooling can provide stronger heat rejection but may require water treatment and creates its own thermal discharge constraints.

## 31. Useful heat rejection
The rejection stream can sometimes become a useful process-water or space-heating stream rather than waste. This can improve system-level economics.

## 32. Secondary loop
A controlled secondary loop allows the source to be separated from the core. It also supports standard pumps, valves, sensors and reservoirs.

## 33. Thermal buffer
A buffer tank can smooth short-term source fluctuations or supply rapid transient cooling/heating power. It must not be confused with permanent “stored cold” that leaks away indefinitely.

## 34. Transient behavior
During startup, exchanger temperatures move toward steady state. Control logic must account for thermal inertia instead of treating setpoints as instantaneous.

## 35. Rapid cooling
For 0–3 C pull-down, exchanger capacity must be sufficient for the transient load. A low-capacity exchanger can make the entire rapid-cooling architecture fail even when the acoustic core has theoretical power.

## 36. Heating mode
For 20→80 C hot water, the hot exchanger must deliver useful heat while keeping the acoustic core within its qualified temperature envelope.

## 37. Source conditioning
Industrial waste heat may arrive as exhaust gas, hot liquid, steam or another form. A dedicated recovery exchanger converts it into a controllable secondary thermal stream.

## 38. Extreme source protection
A 1500 C accidental stream should trigger upstream isolation/diversion. The recovery stage must be independently rated and separated from the lower-temperature THERMA core interface.

## 39. Instrumentation
Each exchanger should have inlet and outlet temperature sensors, flow measurement and pressure measurement sufficient to calculate actual heat transfer and detect fouling or blockage.

## 40. Thermal power calculation
For a water loop, Qdot = m_dot cp (Tout-Tin). Measured flow and temperature differences determine actual thermal power.

## 41. Uncertainty
A small measured temperature difference can have a large relative uncertainty. Sensor calibration, placement and flow measurement quality therefore matter strongly.

## 42. Validation matrix
Test points should span minimum, nominal and maximum flow; several source/sink temperatures; and multiple acoustic conditions.

## 43. Exact geometry
The final exchanger drawing must include channel dimensions, tube/plate arrangement, wall thickness, ports, materials and mounting. Generated images are not authority for these dimensions.

## 44. CFD and reduced-order models
CFD can resolve local flow and heat transfer but is costly. Reduced-order models are valuable for optimization if they are anchored to experiments.

## 45. Published-data validation
Before selecting a new exchanger concept, reproduce a known published oscillatory-flow condition where possible. This helps expose model bias.

## 46. Failure modes
Possible failures include leaks, blockage, fouling, thermal fatigue, brazing defects, corrosion, fan failure, pump failure and sensor errors.

## 47. Serviceability
The design should provide access to removable exchanger cartridges, filters, drains, instrumentation and isolation valves where practical.

## 48. Safety
Hot and cold surfaces must be guarded. Pressure boundaries require relief devices. Any coolant or process fluid must be separated from the working gas.

## 49. Commercial sizing
Exchanger sizing must be based on required thermal power, flow rate, approach temperature, pressure drop and duty cycle, not just the desired outlet temperature.

## 50. Closing principle
THERMA performance will ultimately be constrained by the quality of its heat exchangers and thermal interfaces as much as by the acoustic core. The correct design is a coupled acoustic-thermal exchanger system, not an acoustic engine with generic plumbing.
