# 009 — Control, Instrumentation, ATAPR and Data Acquisition

## Purpose
This document defines how THERMA observes and controls a fixed thermoacoustic core and its external thermal loops. It separates control optimization from independent safety protection.

## 1. Sensor philosophy
A THERMA prototype should be heavily instrumented because the primary unknowns are physical: acoustic amplitude, phase, thermal power, pressure stability, heat-exchanger behavior and leakage.

## 2. Minimum temperatures
Measure hot-source inlet/outlet, hot-core node, cold-core node, cold-load inlet/outlet, rejection inlet/outlet and relevant ambient or sink temperatures.

## 3. Pressure sensors
Measure mean working-gas pressure and, during development, acoustic pressure amplitude at strategically selected locations.

## 4. Flow sensors
Measure external source, cold, hot and rejection loop flow rates. Flow values are necessary for thermal-power calculation.

## 5. Acoustic sensors
Microphones are not automatically interchangeable with pressure transducers. The development setup should use an instrument appropriate to the pressure and frequency regime.

## 6. Phase measurement
At least two pressure or pressure/velocity reference signals may be needed to characterize phase relationships. Phase drift can indicate changes in the operating point.

## 7. Frequency tracking
The controller should track operating frequency and resonance. A fixed frequency assumption may fail as temperature and gas properties change.

## 8. Mean pressure control
Pressure should be monitored over long runs to identify leakage or gas-condition drift. Any active pressure adjustment requires a qualified subsystem.

## 9. Flow control
External pumps and valves can regulate thermal-loop flow. Their power must be included in auxiliary electricity.

## 10. ATAPR definition
ATAPR is a project label for adaptive acoustic/thermal routing and control. It is not an established external commercial technology.

## 11. State machine
The basic states are normal, economy, boost, degraded, neutral/transition and safe shutdown. State transitions should be defined by measurable conditions.

## 12. Normal state
Normal state runs the core near its selected validated operating point. The controller maintains temperature, flow, pressure and acoustic constraints.

## 13. Economy state
Economy state reduces thermal input or acoustic power when load is low. It should maintain minimum safe temperatures and pressures.

## 14. Boost state
Boost state provides higher transient thermal power when the source and rejection systems support it. It must have bounded duration or operating limits.

## 15. Degraded state
Degraded state is used when one noncritical sensor, module or heat source is limited. Output is reduced while remaining inside safe boundaries.

## 16. Neutral state
Neutral reduces acoustic activity and places thermal routing into a stable transition configuration before mode reversal or certain maintenance actions.

## 17. Safe shutdown
Safe shutdown isolates heat source, reduces acoustic activity, protects pressure boundary, and leaves relief systems active.

## 18. Cascade control
A high-level load controller can set a temperature or thermal-power target while lower loops regulate flow or acoustic drive. This structure reduces interactions.

## 19. Feedforward
If source temperature or load disturbances are measurable before they affect the controlled variable, feedforward can reduce transient error.

## 20. Feedback
Temperature, pressure and flow feedback correct disturbances and model errors. Sensor calibration determines the quality of the correction.

## 21. PID role
PID can regulate flow, temperature or other slow loops. Acoustic resonance control may require additional phase/frequency logic rather than simple PID alone.

## 22. Anti-windup
Valve saturation and pump limits can cause integral windup. Controllers should handle saturation explicitly.

## 23. Rate limiting
Commanded thermal or acoustic changes should have ramp limits to avoid thermal shock and abrupt pressure transients.

## 24. Setpoint management
The system should distinguish user target, safe limit, alarm limit and hard trip limit.

## 25. Redundant sensors
Critical trips such as overpressure or overheating can use redundant sensors or independent physical protection. Redundancy does not replace qualified relief devices.

## 26. Sensor plausibility
A reading should be checked for range, rate-of-change and cross-sensor consistency. Impossible values should enter a fault state rather than drive normal control.

## 27. Sensor drift
Calibration drift can slowly bias control. Long-duration tests should compare sensors against reference instruments.

## 28. Sensor placement
Sensor location matters because thermal gradients exist. A sensor in a pipe wall may not equal the fluid bulk temperature.

## 29. DAQ
A data-acquisition system should log synchronized temperature, pressure, flow, acoustic and control channels. Time synchronization is essential for phase analysis.

## 30. Sampling frequency
Acoustic signals require much higher sampling than slow thermal loops. The DAQ should use appropriate rates for each channel.

## 31. Anti-aliasing
Acoustic measurement should use filtering and sampling strategy that prevents aliasing from contaminating amplitude and phase estimates.

## 32. Data storage
Raw data should be retained alongside processed summaries. Derived COP tables without raw evidence are difficult to audit.

## 33. Metadata
Each run should record geometry version, gas, pressure, source conditions, ambient conditions, sensor calibration state and software/model version.

## 34. Run identifier
Assign a unique run ID to every experiment. This makes simulation-to-hardware correlation traceable.

## 35. Digital twin boundary
A model can provide a predicted state for comparison, but it should not overwrite measured data. Model and measurement remain separate channels.

## 36. Alarm levels
Suggested levels are advisory, warning, degraded and trip. Exact thresholds must be derived from engineering limits.

## 37. Thermal alarm
Overtemperature should trigger controlled derating or bypass before the hard material limit is reached.

## 38. Pressure alarm
High pressure should first produce a controlled response and then an independent hard safety response if pressure continues rising.

## 39. Flow alarm
Insufficient flow through a critical exchanger should prevent continued high heat input because local temperature could rise rapidly.

## 40. Rejection alarm
Loss of heat rejection capacity can cause the hot side to rise above control limits. The system must detect and derate.

## 41. Acoustic instability alarm
Unexpected frequency drift, amplitude growth or phase collapse can indicate unstable operation. The control system should move toward neutral or safe shutdown.

## 42. Mode-switch logic
Cooling-to-heating and heating-to-cooling should be treated as explicit state transitions, including stabilization, isolation and verification.

## 43. Control authority
The controller can optimize within limits but must not change safety limits dynamically without an independently verified mechanism.

## 44. Fault hierarchy
A fault should be classified by consequence: informational, correctable, degraded operation, immediate shutdown, or physical protection event.

## 45. Redundant safety
Software safety should be backed by independent mechanical relief and hardware interlock where required.

## 46. Cybersecurity
Networked controls should isolate operational technology from general networks. Remote access must not bypass hard safety layers.

## 47. Manual operation
The prototype should have a local stop and a defined manual recovery procedure. Remote software should not be the only route to a safe state.

## 48. Calibration
Temperature, pressure and flow sensors require traceable calibration appropriate to expected uncertainty.

## 49. Validation
A control algorithm is not validated by a successful simulation alone. It must demonstrate stable behavior on hardware across the defined test envelope.

## 50. Closing principle
ATAPR is an adaptive control concept around a fixed thermoacoustic machine. Its job is to keep the physical system inside a validated operating envelope, not to compensate for an unvalidated architecture or replace independent safety.
