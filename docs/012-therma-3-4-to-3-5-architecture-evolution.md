# 012 — THERMA 3.4 to 3.5 Architecture Evolution

## Purpose
Document the engineering evolution from earlier THERMA generations to the reversible 3.5 concept while preserving what changed, why it changed, and what remains unproven.

## 1. Core lineage
The project history passes through Core-1, 2.x, 3.0, 3.1, 3.2, 3.3, 3.4 and 3.5. Version numbers represent design iterations, not maturity certificates.

## 2. Early objective
The initial direction focused on converting a thermal gradient into useful refrigeration with thermoacoustic physics.

## 3. First major problem
Early conceptual work exposed sensitivity to heat-source temperature, thermal losses, exchanger performance and acoustic matching.

## 4. Low-grade heat branch
The project explored 55–60 C source conditions. This exposed the small available thermal head and the importance of heat-sink temperature.

## 5. More favorable source band
Later work shifted attention toward roughly 80–120 C industrial sources for a more realistic first prototype.

## 6. 2.x direction
The 2.x family explored alternative acoustic arrangements, modularity and more realistic system-level integration.

## 7. 3.0 direction
3.0 emphasized system architecture and control rather than a single idealized core.

## 8. 3.1 direction
3.1 explored adaptive behavior and historical screening COP values. Those values are retained as model history, not hardware evidence.

## 9. 3.2 direction
3.2 expanded adaptive operation, lifecycle thinking, load modeling and modular architecture.

## 10. 3.3 problem
The project realized that steady-state cooling is not enough for everyday operation. Warm rooms and product loads may require high transient cooling power.

## 11. 3.3 response
3.3 explored rapid cooling with multiple fixed cores and thermal buffering. This separates energy availability from instantaneous cooling output.

## 12. 3.4 focus
The v1 dossier describes 3.4 as a focus on regenerator optimization, heat-exchanger optimization, modular parallel cores, acoustic-streaming mitigation and serviceability.

## 13. Why regenerator optimization mattered
A regenerator that stores heat effectively but causes excessive acoustic resistance can reduce total system output. Optimization therefore requires coupled thermal/acoustic analysis.

## 14. Why heat exchangers mattered
The thermal interfaces connect the internal acoustic field to external thermal loops. A theoretical core cannot deliver practical power if its heat exchanger is undersized.

## 15. Streaming problem
Acoustic streaming can create mean mass transport and parasitic heat flow. The redesign logic required explicit attention to streaming and related nonlinear effects.

## 16. Serviceability
The concept moved toward replaceable thermal and acoustic modules where practical. This supports maintenance without treating the entire machine as disposable.

## 17. 3.5 goal
3.5 expanded the concept to reversible cooling and heating, using one fixed thermoacoustic hardware platform with controlled routing.

## 18. Cooling mode
In cooling mode, a heat-driven thermoacoustic engine creates acoustic work that drives refrigeration.

## 19. Heating mode
In heating mode, acoustic work drives heat pumping from a lower-temperature source toward a hot-water or process loop.

## 20. Reversible control
Mode switching should pass through a neutral state, reduce acoustic amplitude, verify pressure and thermal conditions, then ramp into the new state.

## 21. No-moving-core lock
Throughout the architecture correction, the intended 3.5 core remains fixed hardware. The working gas oscillates acoustically; no piston, displacer, crankshaft, connecting rod, flywheel or mechanical compressor is added.

## 22. Why the error matters
Later generated illustration work introduced reciprocating components. Those images represent architecture drift and must not be used as authoritative THERMA 3.5 engineering drawings.

## 23. Visual history rule
Historical images may be retained for development history but should be labeled as rejected, obsolete, or non-authoritative if they violate the current architecture.

## 24. 3.5 thermal interface
The 3.5 architecture favors controlled secondary loops so the same fixed core can serve different heat sources and user loads.

## 25. Modular scaling
Parallel fixed cores can provide larger total capacity while allowing individual modules to be isolated.

## 26. Staged scaling
Staged cores may improve temperature matching but increase complexity. No stage count is accepted until a quantitative benefit is demonstrated.

## 27. Rapid cooling integration
3.5 inherits the 3.3 lesson that rapid 0–3 C cooling requires sufficient transient power, thermal buffering or parallel capacity.

## 28. High-temperature integration
3.5 inherits the safety requirement that very hot source streams must be conditioned before entering the core.

## 29. 1500 C rule
A raw 1500 C stream must be diverted or recovered through a separately qualified interface. It is never direct core input.

## 30. Heating integration
The 20→80 C hot-water case remains a conceptual heat-pump target. It is not a measured THERMA result.

## 31. Economic lesson
The project screening indicates that waste heat with low marginal cost is the strongest candidate business case.

## 32. Mature competitor lesson
Small THERMA units are unlikely to beat mature compressor systems on cost alone without a valuable thermal input or system-level advantage.

## 33. Environmental lesson
The environmental benefit comes from energy reuse and avoided generation, not from destroying heat.

## 34. Network lesson
Factory-to-community concepts require controlled thermal-water networks, not raw exhaust distribution.

## 35. Control lesson
The controller should be adaptive but operate within fixed engineering limits. Software must not replace independent safety.

## 36. Model lesson
Every architecture change requires regression testing against a fixed canonical scenario set.

## 37. Prototype lesson
The next physical prototype should be single-core and heavily instrumented rather than a full-scale modular system.

## 38. Model-validation lesson
The exact-geometry model should be validated against published geometry or other trusted reference data where possible before being treated as predictive.

## 39. Manufacturing lesson
Precision pressure fabrication, heat exchangers, acoustic geometry and instrumentation dominate early cost and risk.

## 40. Materials lesson
Material choice must be based on pressure, temperature, gas compatibility, cycling, corrosion and fabrication rather than image aesthetics.

## 41. Acoustic lesson
No version number makes acoustic geometry automatically valid. Resonator dimensions must be solved numerically for the selected operating condition.

## 42. Thermal lesson
No version number makes a heat exchanger automatically adequate. Heat-transfer and pressure-loss testing remain mandatory.

## 43. Safety lesson
The product architecture must contain thermal isolation, pressure relief, leak detection, safe shutdown and emergency source diversion.

## 44. Evidence lesson
Version evolution is useful history, but only measured results should move from the C category to D hardware evidence.

## 45. Rejected architecture handling
A rejected design can remain in the archive if it teaches a failure mode. It must be clearly labeled so an external reviewer cannot mistake it for the current design.

## 46. 3.5 design statement
The current 3.5 statement is: a reversible fixed-hardware thermoacoustic platform using suitable thermal gradients to generate acoustic work for cooling and using acoustic work to pump heat toward useful hot-side loads.

## 47. Open design choices
The exact acoustic topology, frequency, mean pressure, gas, regenerator structure, heat exchanger geometry, modular count and control laws remain design choices until the exact prototype geometry is frozen.

## 48. Open research questions
The key open questions are actual COP, power density, low-grade performance, streaming, acoustic losses, thermal-interface losses, pressure integrity, endurance, cost and economics.

## 49. Current gate
3.5 should be considered pre-prototype and ready for disciplined exact-geometry modeling, not commercial production.

## 50. Closing principle
Version evolution is valuable only when each generation removes a known weakness. THERMA 3.5 should be the start of a controlled validation phase, not the end of engineering questioning.
