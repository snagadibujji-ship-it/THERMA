# 001 — Project Identity and Scope

## 1. Purpose
This file defines the identity, scope, terminology and evidence boundary of GHIA THERMA. It is the anchor document for the engineering record and should be read before any performance claim, geometry claim or prototype statement is interpreted.

## 2. Project identity
THERMA is a GHIA project. TA-CRX was the internal engineering codename used during iterative concept development. THERMA became the product-family name because the project expanded beyond refrigeration into reversible heating and cooling.

## 3. What the project is
THERMA is a conceptual reversible thermoacoustic thermal platform. In the intended architecture, an imposed temperature gradient can generate acoustic work for refrigeration, while acoustic work can be used to pump heat toward a higher-temperature delivery loop.

## 4. What the project is not
THERMA is not a claim that GHIA invented thermoacoustics, and it is not currently a certified refrigerator, heater, pressure vessel, or commercial product. It is not experimentally proven at the level of THERMA-specific COP, cooling capacity, pressure integrity, lifecycle, or certification.

## 5. Architecture lock
The THERMA 3.5 core is documented as fixed mechanical hardware with oscillating working gas. The core contains no piston, displacer, crankshaft, connecting rod, flywheel, or mechanical bearing power train. Gas motion is acoustic oscillation around equilibrium, not reciprocating mechanical motion.

## 6. System boundary
The primary THERMA boundary includes the thermoacoustic working-gas domain, resonator, regenerator, hot and cold heat exchangers, pressure boundary and acoustic routing. Secondary thermal loops, pumps and valves may move external fluids; these are not part of a piston/compressor core.

## 7. Cooling objective
The project has repeatedly used 0–3 °C as the cold-side target for selected refrigeration and cold-storage applications. Temperature target is distinct from cooling capacity, which must be reported as a rate such as watts or kilowatts.

## 8. Heating objective
A conceptual heat-pump case examined raising water from 20 °C to 80 °C. The sensible heat required for 1 L of water is approximately 69.8 Wh under the standard cp assumption; the actual THERMA work requirement and COP remain prototype questions.

## 9. Waste-heat objective
A central value proposition is the use of suitable industrial waste heat as a thermal driving source. The source should enter through a controlled secondary heat-transfer interface rather than being routed directly into the acoustic core.

## 10. Reversibility
THERMA 3.5 is intended to support cooling and heating operation through controlled acoustic and thermal routing. The transition should pass through a neutral/verified state rather than abruptly swapping operating modes.

## 11. Evidence discipline
Every result must be classified as external established evidence, first-principles calculation, THERMA screening/design hypothesis, or hardware-only evidence.

## 12. No-image rule for authority
Generated images are visual communication assets. They do not establish exact tube lengths, resonator dimensions, regenerator pore geometry, pressure ratings, material certification, or measured performance.

## 13. Historical modeling
Earlier conversations included screening values and simplified COP assumptions. Those values are retained as history only where useful. They must not be promoted to measured results.

## 14. Prototype objective
The preferred first prototype is a single-core, heavily instrumented proof-of-physics system. Its purpose is to measure acoustic behavior and thermal transfer, compare measurements to an independently reproducible model, and identify redesign needs.

## 15. Primary research questions
1. Can the exact selected geometry produce stable acoustic operation at the intended source temperature?
2. Can the heat exchangers transfer useful thermal power under oscillatory flow?
3. Can the regenerator maintain the intended thermoacoustic gradient without excessive loss?
4. Can the system deliver measurable 0–3 °C cooling or useful 20–80 °C heat-pump output?
5. Can reversible operation be controlled safely?

## 16. Commercial boundary
The project should be presented as deep-tech R&D until measured prototype data establish capability. Economic value is most compelling where thermal input has low marginal cost, especially suitable industrial waste heat.

## 17. IP boundary
The general thermoacoustic principle has prior art. Potentially protectable subject matter may exist in a specific integrated architecture, control method, thermal-routing arrangement, module arrangement or implementation, but novelty and non-obviousness require formal prior-art and legal review.

## 18. Safety boundary
High-temperature and pressurized streams must be conditioned. A raw extreme stream, such as an accidental 1500 °C industrial input, must be diverted or recovered through a rated upstream system; it must not directly enter the qualified THERMA core.

## 19. Reliability philosophy
The lifecycle objective is a long-lived platform with replaceable service modules rather than a claim of maintenance-free operation for a century.

## 20. Engineering workflow
The intended workflow is: define → model → independently reproduce → attack assumptions → redesign → prototype → measure → correlate → regress → repeat until a defensible design is achieved.

## 21. Definition of success
Success is not a green simulation table. Success is a reproducible model that predicts hardware measurements within a defined error band and becomes more accurate as validated data are accumulated.

## 22. Document relationship
Files 002–100 expand this scope. File 100 is the master record and should summarize the state of evidence after all supporting modules are complete.

## 23. Source-derived baseline
The original GHIA THERMA dossier describes THERMA as a conceptual/research-stage product, explicitly separates established science from first-principles calculations, THERMA screening outputs and hardware-only facts, and states that the models are not a substitute for exact-geometry validation, material testing, pressure-vessel qualification, helium leak testing or certification.

## 24. Cooling-chain interpretation
For cooling, the logical chain is: suitable heat source → thermal conditioning → thermoacoustic engine action → acoustic power transfer → refrigeration section → cold heat exchanger → secondary cold loop → load, with final heat rejection to a sink.

## 25. Heating-chain interpretation
For heating, the logical chain is: lower-temperature source → source heat exchanger → thermoacoustic heat-pump operation → hot-side heat exchanger → secondary hot-water loop → user/process load. The quantity of water does not magically increase; thermal energy is added to the same mass flow.

## 26. Energy balance discipline
No operating mode may be described as creating heat or cooling from nothing. For heat-pump operation the first-law balance remains Q_H = Q_C + W, with actual COP constrained by temperature lift, exchanger approaches, acoustic losses and auxiliary loads.

## 27. Rapid cooling boundary
The 0–3 °C target does not mean that any load reaches 3 °C instantly. Pull-down time is a load problem as well as a machine problem. A rapid design must supply enough transient cooling power or use a correctly engineered thermal buffer/parallel-module arrangement.

## 28. Source-temperature boundary
A higher source temperature can provide more thermodynamic opportunity, but it does not guarantee proportionally higher cooling. Excess heat can instead increase losses, thermal stress and safety risk if the heat exchanger and core are not designed for it.

## 29. Extreme-input protection
A raw 1500 °C industrial stream is outside the normal THERMA core interface. The required response is upstream isolation/diversion and, where justified, a separately qualified high-temperature recovery stage that delivers a controlled secondary-loop temperature to THERMA.

## 30. Working-gas boundary
The working gas is sealed and separated from user water. Helium is a candidate because of favorable thermoacoustic properties, but gas choice remains an optimization variable that depends on the exact geometry, pressure, frequency, losses and material compatibility.

## 31. Acoustic boundary
The resonator, inertance, compliance and related acoustic geometry are fixed hardware. They must be solved for an exact geometry before fabrication; generated illustrations do not establish a validated resonance, impedance or pressure-amplitude point.

## 32. Regenerator boundary
The regenerator is a core thermal component. Porosity, pore size, thermal conductivity, heat capacity, hydraulic radius, length and pressure drop must be jointly evaluated. A replaceable cartridge is a serviceability strategy, not proof that cartridge life has been established.

## 33. Heat-exchanger boundary
The hot and cold heat exchangers are often likely performance bottlenecks. Oscillatory-flow heat transfer requires geometry-specific validation rather than blind reuse of steady-flow correlations.

## 34. Control boundary
Sensors and control can choose among normal, economy, boost, degraded, neutral/transition and safe-shutdown states. Software should not be the sole safety barrier; independent pressure and thermal protection remains necessary.

## 35. External-loop boundary
Pumps and valves in secondary water or thermal-fluid loops are allowed because they move the external working fluid. Their presence does not change the core architectural requirement of no mechanical moving power train.

## 36. Prototype measurement set
A credible first prototype should measure hot source temperature/flow, cold-side temperature/flow, heat-rejection temperature/flow, acoustic pressure amplitude, frequency, phase, mean pressure, helium inventory, any electrical driver power, and useful thermal output.

## 37. Prototype acceptance logic
Prototype acceptance should be defined before testing and should cover containment, acoustics, thermal performance, controls, emergency response, endurance and measured-versus-model agreement.

## 38. Economic boundary
The strongest initial economic scenario is suitable high-utilization waste heat with low marginal thermal cost. Using electricity merely to create heat and then running heat-driven refrigeration usually loses against direct electric compression unless there is an additional system benefit.

## 39. Network boundary
Distributed deployment may use insulated thermal-fluid piping from a factory source to local THERMA nodes. It should transport controllable secondary fluid, not raw exhaust gas, and must include pipeline loss, distance, load diversity and capital cost.

## 40. IP boundary restated
A chat transcript can document project history, but it does not itself establish patent rights. Formal prior-art searching, claim drafting and legal review are needed before asserting novelty.

## 41. Documentation rule
Every future technical result should preserve its boundary conditions: source temperature, sink temperature, target temperature, thermal input, acoustic/electrical work, output quantity, COP definition, duration and model fidelity.

## 42. Simulation rule
A large randomized screening campaign is not equivalent to a high-fidelity CFD or exact-geometry thermoacoustic simulation. Scenario counts test the assumptions of the screening model; they do not supply missing empirical material or acoustic-field data.

## 43. Correction rule
Where historical results conflict, the correct action is to expose the conflict, document the assumptions and replace the number only after a reproducible recalculation or measurement. A green result that cannot be reproduced is not treated as a final result.

## 44. Lifecycle rule
The long-life objective is expressed as serviceable platform life with replaceable modules and traceable inspection, not a maintenance-free guarantee.

## 45. Interview boundary
For college or engineering interviews, THERMA can be presented as a conceptual deep-tech research project combining thermodynamics, acoustics, heat transfer, controls, safety and prototype planning. It should not be presented as experimentally proven commercial hardware.

## 46. Visual-asset boundary
The repository may reference the generated THERMA images created during the project, but those images are illustrations. They may support explanation and design discussion; they do not define authoritative dimensions or performance unless backed by a separate calculation or experiment.

## 47. Future-document rule
Supporting files should expand the equations, subsystem models, historical simulations, failure analysis, materials, controls, test plans, economics, prior art and visual-asset audit without contradicting this identity document.

## 48. Final architectural statement
The intended THERMA 3.5 core is a fixed geometry thermoacoustic machine whose working gas oscillates acoustically. External pumps and valves may serve secondary loops, but a piston, displacer, crankshaft, connecting rod, flywheel or conventional reciprocating compressor is not part of the intended core.

## 49. Current maturity statement
THERMA is a documented pre-prototype engineering concept. The most valuable next step is an exact-geometry, reproducible model followed by a heavily instrumented proof-of-physics prototype.

## 50. Closing rule
When a future file appears to improve THERMA by adding a component or mechanism, the change must first be classified as either a secondary-loop component, a fixed thermoacoustic component, an instrumentation/control component, or an actual architecture change requiring explicit review. Silent architecture drift is prohibited.
