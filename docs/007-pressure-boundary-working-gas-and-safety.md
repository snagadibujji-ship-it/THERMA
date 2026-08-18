# 007 — Pressure Boundary, Working Gas, and Safety

## Purpose
This document defines the pressure-containing and gas-handling architecture for the fixed THERMA core. It focuses on pressure integrity, gas management, relief, leak detection, thermal protection and safe commissioning.

## 1. Pressure-system status
If the working gas is maintained above atmospheric pressure, the THERMA core becomes a pressure system. Final design must follow the applicable code and jurisdiction.

## 2. Pressure boundary
The pressure boundary includes the resonator shell, chambers, ports, closures, heat-exchanger interfaces and any other component containing the working gas.

## 3. Design pressure
Design pressure must be chosen from the intended mean operating pressure, maximum transient, relief setting, test pressure and code rules. A conversational screening value is not a fabrication specification.

## 4. Mean pressure
Mean pressure influences gas density and acoustic power density. Higher pressure can shrink the required machine volume for a target power but raises engineering risk and cost.

## 5. Pressure cycling
Acoustic operation imposes cyclic pressure variation on top of mean pressure. Pressure amplitude and cycle count can drive fatigue requirements.

## 6. Fatigue
Pressure-vessel fatigue design must account for repeated cycles, thermal gradients, stress concentrations and weld details. Prototype qualification needs a defined cycle spectrum.

## 7. Wall stress
Basic pressure-vessel relationships can provide first estimates of membrane stress, but final geometry requires code-based analysis that includes openings, heads, nozzles and local loads.

## 8. Welds
Pressure-wetted welds require qualified procedures and inspection. The allowable quality depends on the governing code and service.

## 9. Ports and nozzles
Ports for fill, measurement, relief and thermal interfaces create stress concentrations. Their geometry must be included in final analysis.

## 10. Closures
Any removable closure must maintain pressure integrity and repeated thermal-cycle performance. Bolted covers require defined gasket or seal systems.

## 11. Seals
Seals must be compatible with working gas, temperature, pressure and cycling. If the design can avoid unnecessary dynamic seals, that can reduce leakage risk.

## 12. No mechanical-moving core
The pressure boundary encloses an acoustic field and stationary solid components. No piston or crank mechanism is required in the core architecture.

## 13. Helium candidate
Helium is a recurring candidate because published thermoacoustic systems use it successfully, but helium is prone to leakage through small imperfections because of its low molecular size.

## 14. Gas charging
Charging should use a controlled regulator, verified hoses, isolation valves and measured pressure rise. The exact charging pressure must come from the qualified design.

## 15. Gas purity
Contamination and moisture can alter thermal and acoustic properties. Controlled gas handling is required for repeatable prototype results.

## 16. Leak detection
Leak tests should be performed before operation and after thermal cycling. Helium-specific detection methods may be used where appropriate.

## 17. Isolation
At minimum, the system should have means to isolate the pressure boundary from charging equipment and downstream service interfaces.

## 18. Relief
A pressure relief device independent of software should protect against overpressure. Set pressure and capacity must be selected by qualified engineering.

## 19. Venting
Controlled venting must consider gas handling, pressure, temperature, personnel protection and local rules.

## 20. Instrumentation
Pressure transducers should cover the expected operating and trip range. Redundant measurement is desirable for critical shutdown functions.

## 21. Independent protection
The main control system should not be the only safety layer. Mechanical relief and hardwired or independent trip functions should remain available.

## 22. Thermal protection
The source side must be conditioned so that the core sees only its qualified temperature. Overtemperature should cause isolation, bypass or shutdown.

## 23. Extreme source event
A 1500 C industrial stream is not a normal THERMA input. It must be captured by the source interface, diverted or processed through a high-temperature recovery stage before the secondary loop reaches the core.

## 24. Thermal shock
Rapid temperature changes can stress heat exchangers, pressure walls, welds and seals. The commissioning sequence should ramp heat input rather than apply an unexplained step.

## 25. Cold shock
Cold-side transitions can also create differential expansion and condensation. The startup sequence should manage the temperature rate of change.

## 26. Fire exposure
If upstream combustion equipment is used, the THERMA pressure boundary must be separated from direct flame and protected against external fire exposure according to applicable codes.

## 27. Exhaust isolation
Combustion exhaust should not enter the working-gas domain. Any recovery from exhaust must use a dedicated rated heat exchanger.

## 28. Water separation
Process water and the acoustic working gas remain separate. A failure that mixes fluids must be detectable and isolated.

## 29. Relief discharge
The relief discharge path should direct released gas to a safe location and be sized for the selected worst-case scenario.

## 30. Test pressure
The proof or hydrostatic/pneumatic test method must follow the governing pressure-vessel code. Prototype testing should use qualified procedures rather than ad hoc overpressure.

## 31. Commissioning sequence
Commissioning should start with mechanical inspection, sensor check, low-pressure leak verification, controlled gas fill, pressure verification, thermal ramp, acoustic onset and finally load testing.

## 32. Emergency shutdown
A safe shutdown should stop the heat source or isolate the source loop, reduce acoustic operation, isolate thermal paths and leave pressure protection active.

## 33. Fail-safe valves
Critical thermal isolation valves should have a defined safe position on power loss. The exact selection depends on process hazards.

## 34. Pump failure
Loss of secondary-loop flow can cause local overheating or thermal degradation. Flow interlocks should inhibit operation when required circulation is absent.

## 35. Fan failure
An air-cooled rejection system can overheat if fans fail. The controller must detect loss of airflow and reduce or stop thermal input.

## 36. Sensor failure
Sensor diagnostics should detect open circuits, impossible values, drift and disagreement between redundant channels.

## 37. Pressure-sensor disagreement
Critical pressure trips should be cross-checked where practicable. A single faulty transducer should not disable independent mechanical protection.

## 38. Leak-growth detection
Pressure trend, gas inventory estimates and dedicated leak sensors can be combined to detect slow degradation before it becomes a functional failure.

## 39. Safe neutral state
The reversible architecture should support a state in which acoustic power is minimized while temperature and pressure remain within safe control bands.

## 40. Maintenance isolation
Serviceable modules require positive isolation, depressurization and lockout procedures before removal.

## 41. Pressure history
For a long-life platform, keep a record of pressure cycles, leak tests, repairs, inspections and relief events. This creates traceability for the pressure boundary.

## 42. Materials selection
Candidate 316L-class stainless steels or other qualified alloys may be suitable, but final material selection requires temperature, pressure, gas compatibility and fatigue analysis.

## 43. High-temperature alloys
Where hot-side temperatures demand them, nickel alloys or other high-temperature materials may be considered. This must be matched to fabrication capability and cost.

## 44. Corrosion
External process fluids can cause corrosion independently of the sealed acoustic gas. Water chemistry and condensation control therefore matter.

## 45. Acoustic-mechanical interaction
Even a fixed core can vibrate elastically. Structural modes may create stress or noise and should be separated from destructive resonance through analysis and testing.

## 46. Prototype safety gate
No full thermal test should begin until pressure/leak checks, relief verification, instrument calibration, and emergency bypass are complete.

## 47. Test documentation
Every safety test should record date, configuration, pressure, temperature, instrumentation, operator, result and corrective action.

## 48. Standards boundary
Applicable standards depend on final pressure, product type, jurisdiction and installation. The v1 dossier references ASME BPVC Section VIII Division 1 for pressure-vessel context, but final code selection must be made by a qualified engineer.

## 49. Certification boundary
A conceptual design cannot be called certified because a simulation or illustration looks technically complete. Certification requires design review, fabrication control, inspection, testing and conformity evidence.

## 50. Closing principle
A high-performance THERMA system is not safe because software says it is safe. Safety must be structural: qualified pressure boundary, independent relief, conditioned source, isolation, calibrated sensors and validated commissioning procedures.
