# 010 — Simulation Methodology and History

## Purpose
This document records how THERMA simulation work should be interpreted, how the development generations evolved, and which results are screening assumptions versus evidence.

## 1. Why simulation exists
Simulation is used to compare architectures before expensive fabrication. It can reveal energy-balance violations, impossible operating points, sensitivity to losses and control failures.

## 2. Simulation is not experiment
A simulation produces consequences of its equations and assumptions. It cannot certify the properties of untested materials, validate a manufactured pressure boundary or prove an exact acoustic field without appropriate model fidelity and validation.

## 3. Evidence levels
The project uses A for established external evidence, B for calculations, C for THERMA screening/design hypotheses and D for hardware-only facts.

## 4. Model hierarchy
Use a staged hierarchy: first-law energy balance, lumped heat-load model, reduced acoustic network, linear thermoacoustic analysis, exact-geometry solver, nonlinear loss model, and finally coupled prototype correlation.

## 5. Input definition
Every simulation should explicitly define source temperature, sink temperature, cold/hot target, flow rate, gas, pressure, geometry, loss model and duration.

## 6. Output definition
Outputs should include cooling or heating power, source thermal power, acoustic/electrical work, COP under a named convention, temperatures, pressures, stability state and uncertainty.

## 7. Boundary conditions
Poorly defined boundaries can make a model appear more efficient than reality. Thermal losses, ambient heat leak and finite exchanger approaches must be included where they matter.

## 8. Model fidelity
A simple model can be useful for screening but should not be presented as exact. Fidelity level should appear next to every major result.

## 9. Historical simplified COP
Earlier project discussions used assumed COP factors, including a historical heating COP of 2.1 in the 20→80 C water example. This remains a conditional calculation only.

## 10. COP ambiguity
Cooling COP may be defined per electrical/acoustic work or per thermal driving heat in heat-driven refrigeration. Heating COP may similarly use different input boundaries. Mixing these is an audit error.

## 11. 1.6 L screening result
The 1.6 L source-water ratio came from 69.8 Wh heat delivery, COPH 2.1, and source water dropping 20→0 C. It is not an experimental THERMA ratio.

## 12. Rapid cooling model
Rapid 0–3 C cooling must start with the load energy. A machine cannot pull down a large warm mass in minutes unless its average cooling power is correspondingly high.

## 13. 15-minute example
For 500 kg water-equivalent product from 25 C to 3 C, about 12.8 kWh sensible heat removal is required. Over 15 minutes this is about 51 kW average cold-side power before losses.

## 14. 30 kg example
A 30 kg water-equivalent load over the same 25→3 C range requires about 0.77 kWh sensible removal. Minutes-scale cooling is more plausible if several kW of rapid capacity are actually available.

## 15. 100 kg example
The same target for 100 kg requires about 2.56 kWh sensible removal. The simulation should distinguish load scale from machine temperature capability.

## 16. Ambient variation
A realistic cold room model should vary ambient temperature across the day and season. Wall heat transfer and infiltration change with ambient conditions.

## 17. Door events
Door openings add warm air and latent/sensible load. They should be treated as discrete events, not hidden in a single average leakage number.

## 18. Warm product entries
Product entry can dominate cooling demand. The simulation should track mass, entry temperature, specific heat, entry timing and target temperature.

## 19. Night/day variation
A 24-hour scenario should include source availability, ambient temperature, occupancy and load schedule. One nominal operating point is not a representative day.

## 20. Heat-source interruption
If the source disappears, THERMA cooling capacity should fall unless stored thermal or acoustic energy is available. The control system should enter degraded or safe state rather than pretending output remains constant.

## 21. Startup
Startup includes thermal ramp, acoustic onset, stabilization and initial pull-down. Startup time is not the same as steady-state response time.

## 22. Shutdown
Shutdown should reduce source input and acoustic activity while maintaining safe pressure and thermal states. A model should include the thermal inertia after the command.

## 23. Maintenance state
A maintenance scenario should model reduced capacity, module isolation and service intervals. Long-life analysis should not assume a perfect machine forever.

## 24. Degradation
Possible degradation variables include regenerator effectiveness, exchanger fouling, leakage, sensor drift and acoustic loss growth.

## 25. Randomized screening
Monte Carlo or random sampling can explore uncertainty in those variables. The distributions must be documented because unrealistic distributions produce unrealistic confidence.

## 26. 10-million case statement
A 10-million-case campaign in a screening model means 10 million scenario evaluations. It does not mean 10 million independent CFD, finite-element or experimental validations.

## 27. Adversarial testing
Adversarial tests intentionally push the model toward source extremes, ambient extremes, high load, low load, sensor faults, valve faults and heat-rejection failures.

## 28. 1500 C event model
The extreme-source scenario is a safety test: the correct modeled behavior is upstream isolation/diversion and controlled thermal-interface protection, not direct core acceptance.

## 29. Fuel-source sweep
Potential sources include electric resistance, LPG, natural gas, diesel/engine heat, biomass, solar thermal, industrial waste heat, steam, geothermal, wastewater and hybrid sources.

## 30. Why source class is not enough
Fuel identity does not determine THERMA performance. The core sees a thermal interface characterized by temperature, flow, heat capacity and transient behavior.

## 31. 60 C source branch
At 60 C the thermal head can be small. A simulation must include sink temperature and exchanger approaches to judge feasibility.

## 32. 80–120 C branch
This is a historical first-prototype development range because it offers more thermal head and more realistic industrial waste-heat opportunities.

## 33. 120–200 C branch
Higher temperatures can increase driving potential but increase material and heat-exchanger constraints. The model should include source conditioning.

## 34. Cold-side target
3 C or 0–3 C identifies the thermal target, not the cooling capacity. Every result must pair the target temperature with Qc.

## 35. Heating-side target
20→80 C describes a useful water-temperature range. It must be paired with hot-water flow rate and Qh.

## 36. Annual simulation
A year model integrates hourly or smaller-step profiles over seasons, outages, service and source availability. Annual energy must be calculated by integration, not by multiplying a nominal COP by 8760 without qualification.

## 37. Economic simulation
Fuel, auxiliary power, capital recovery, maintenance, water treatment, piping and downtime should be included. Comparing only thermal input cost is incomplete.

## 38. Environmental simulation
Avoided CO2 can be estimated from displaced electricity or fuel if the emission factors are explicit. It is not a direct global-temperature prediction.

## 39. Network simulation
A factory-to-town model must include thermal pipe losses, pumping, distance, diversity, return temperature and local node demand.

## 40. Scaling
Do not scale kW or MW output by simply multiplying a small module without validating power density, thermal management, controls, pressure systems and balance-of-plant behavior.

## 41. Simulation audit
The project explicitly identified historical inconsistencies. These should be logged, not hidden.

## 42. Reproducibility
A reproducible run requires exact inputs, geometry version, code or model version, solver settings, loss parameters and output definitions.

## 43. Regression testing
Whenever a design changes, rerun the same canonical test set and compare with the previous accepted version.

## 44. Sensitivity
Sensitivity analysis identifies which uncertainty most influences output. This can guide prototype measurement priorities.

## 45. Uncertainty
Uncertainty should include input uncertainty, model discrepancy and numerical convergence where applicable.

## 46. False precision
A simulation reporting 6 decimal places does not imply 6-digit accuracy. Report significant figures consistent with inputs and model validity.

## 47. Failure classification
If a run fails because the architecture violates an energy or pressure constraint, redesign. If a run fails because the model lacks empirical data, report uncertainty and create a measurement plan.

## 48. Decision gate
Each generation should end with a decision: advance, redesign, hold pending data, or stop. “Green” alone is not sufficient.

## 49. Relationship to hardware
The final model should produce measurable predictions: frequency, pressure amplitude, source heat, cold-side duty, hot-side duty, rejection load and stability time.

## 50. Closing statement
THERMA simulation is most valuable as an evidence funnel: broad screening narrows candidates, exact-geometry models eliminate impossible designs, and prototype data establish what the machine actually does.
