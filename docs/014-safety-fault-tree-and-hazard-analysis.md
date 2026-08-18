# 014 — Safety Fault Tree and Hazard Analysis

## Purpose
This document defines a structured hazard-analysis approach for THERMA and turns major failure discussions into testable safety requirements.

## 1. Safety objective
The system should fail toward a controlled thermal and pressure state rather than toward uncontrolled heating, overpressure or loss of containment.

## 2. Hazard categories
Primary hazards are overpressure, overheating, thermal shock, leakage, hot surfaces, cold surfaces, fluid release, electrical fault, loss of rejection, control failure and human error.

## 3. No-moving-core safety
The fixed thermoacoustic core eliminates a conventional mechanical compressor drivetrain, piston, crankshaft and flywheel failure modes. This does not eliminate pressure, thermal or acoustic hazards.

## 4. Overpressure top event
Potential causes include excessive mean pressure, thermal expansion, blocked relief, control failure, wrong gas charge, accidental source input or abnormal acoustic conditions.

## 5. Overpressure prevention
Use correct design pressure, qualified relief devices, pressure instrumentation, controlled charging and independent shutdown logic.

## 6. Overpressure detection
A pressure sensor provides monitoring; it is not a substitute for a relief device.

## 7. Relief device
The relief path must discharge safely and have capacity for the qualified worst-case scenario.

## 8. Thermal runaway top event
Causes include loss of cooling, source overshoot, pump failure, fan failure, exchanger blockage or controller failure.

## 9. Thermal prevention
Condition source heat, enforce temperature limits, monitor flow, and provide physical bypass.

## 10. Thermal detection
Use independent hot-side temperature measurement and a hard trip threshold.

## 11. Low-flow event
Insufficient flow can cause local temperature rise and heat-exchanger damage. The control system should reduce source input or shut down.

## 12. Rejection failure
If the heat sink cannot remove rejected heat, the hot side can exceed its limit. Detect sink temperature and rejector performance.

## 13. Fan failure
Air-cooled rejection systems need fan-status monitoring and a safe derating/shutdown path.

## 14. Pump failure
External-loop pump loss can be detected with flow and pressure. The controller must not continue full heat input without sufficient circulation.

## 15. Valve failure
Critical isolation valves should have defined fail positions. Redundant means may be needed for high-consequence isolation.

## 16. Sensor failure
Sensor failure modes include open circuit, short circuit, drift, stuck value, saturation and implausible rate of change.

## 17. Sensor diagnostics
Plausibility checks, redundancy and cross-correlation can detect many sensor failures.

## 18. Controller failure
A controller can crash, lose communication or command an invalid state. Independent hardware safety layers must remain active.

## 19. Power loss
Loss of electrical power should move valves and pumps to predefined safe states while mechanical pressure relief remains functional.

## 20. Emergency stop
An emergency stop should remove hazardous energy sources and leave pressure protection and necessary monitoring active.

## 21. 1500 C event
A raw 1500 C industrial stream must never directly enter the THERMA core. The safety system should isolate or divert the source before the controlled secondary loop exceeds its design envelope.

## 22. High-temperature recovery stage
If an industrial stream is extremely hot, a separately qualified recovery exchanger may recover useful heat before the secondary THERMA interface. Its own materials and protection are a separate engineering problem.

## 23. Thermal shock
Fast temperature changes can create large gradients. Source ramps and startup procedures should limit dT/dt where necessary.

## 24. Pressure thermal coupling
Heating pressurized gas changes density and may alter acoustic conditions. Thermal control and pressure monitoring therefore interact.

## 25. Helium leak
Helium leakage can reduce operating pressure and change acoustic behavior. It should be detected before performance degrades dangerously.

## 26. Leak consequence
Leak risk is both a performance issue and, depending on enclosure and pressure, a safety issue. Fill and vent arrangements must be controlled.

## 27. Material failure
Candidate materials must be checked for temperature, pressure, fatigue, corrosion and compatibility.

## 28. Fatigue failure
Repeated pressure and thermal cycles can accumulate damage even with average stresses below a simple yield limit.

## 29. Weld failure
Pressure-wetted welds require qualified fabrication and inspection. Visual appearance is not sufficient evidence.

## 30. Heat-exchanger rupture
A failure could mix working gas and process fluid if the boundary is breached. Detection and isolation need to be part of the architecture.

## 31. Fluid compatibility
Water chemistry, oils, thermal fluids and industrial contaminants can attack materials or seals. The selected secondary fluid must be defined.

## 32. Hot-surface hazard
External hot piping and exchangers require guards, insulation and warning labels according to application.

## 33. Cold-surface hazard
Below-freezing or near-freezing surfaces may create condensation, frost and slip hazards. Insulation and drainage matter.

## 34. Electrical hazard
Instrumentation and controls require appropriate electrical protection, grounding and enclosure design.

## 35. Fire hazard
If the upstream heat source uses combustion, THERMA must be segregated from direct flame and protected against credible fire exposure.

## 36. Control-state fault tree
A safe state can be represented as NORMAL → FAULT → DEGRADED/NEUTRAL → ISOLATE → SAFE SHUTDOWN, depending on severity.

## 37. Independent layers
Use process control, alarm logic, hard trip, mechanical relief and physical isolation as layers rather than a single defense.

## 38. Safety integrity concept
The exact safety-integrity level depends on hazard analysis and application. This document does not assign a formal SIL rating.

## 39. Human factors
Operators need clear status, alarms, manual isolation controls, test procedures and recovery instructions.

## 40. Maintenance safety
Before service, the pressure boundary must be isolated, depressurized, verified safe and locked out as required.

## 41. Commissioning hazard
The first high-power run is one of the highest-risk moments because unknown design behavior remains. Remote monitoring and physical shielding are appropriate.

## 42. Test shielding
Pressure or thermal tests may require barriers and exclusion zones according to the qualified test plan.

## 43. Fault injection
Controlled fault injection should test sensors, flow loss, source interruption, rejection loss and communication failure without creating an unsafe real thermal event.

## 44. Fire/explosion separation
The working gas and process water should remain separate from combustion systems. If combustible gases are used upstream, zoning and isolation depend on the installation.

## 45. Alarm philosophy
Alarm levels should distinguish advisory, warning, degraded operation and trip states to avoid alarm overload.

## 46. Event logging
Every safety trip should record timestamps, pressure, temperatures, flows, acoustic state and control state for later root-cause analysis.

## 47. Root-cause analysis
After a fault, separate primary cause, contributing conditions, missed detection and inadequate protection. Do not simply reset and continue.

## 48. Requalification
After a pressure or thermal event, requalification may require inspection, leak testing, sensor checks and possibly pressure testing before restart.

## 49. Safety acceptance gate
No prototype can be considered ready for aggressive operation without an explicit fault-response test demonstrating protective behavior.

## 50. Closing principle
THERMA safety must be embodied in hardware, not inferred from a successful simulation. The architecture should make severe failures difficult to create and easy to isolate when they appear.
