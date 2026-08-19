# 019 — Visual Asset, Diagram, and Image Audit

## 1. Purpose
This file is the authoritative registry for the THERMA visual assets generated during the project. It exists to prevent a generated picture from being mistaken for a validated engineering drawing.

## 2. Asset classes
Assets are divided into: system overview, internal architecture, thermal flow, acoustic physics, components, controls, safety, validation, application, and development history.

## 3. Evidence rule
A visual may communicate a concept, but dimensions, materials, pressure, acoustic amplitude, heat-transfer coefficient, COP, cooling capacity, or safety margin must come from separate engineering work.

## 4. Current architecture
The final THERMA 3.5 architecture is fixed-hardware thermoacoustics with oscillating working gas and no piston, displacer, crankshaft, connecting rod, flywheel, reciprocating compressor, or mechanical-bearing power train in the core.

## 5. Image history
The project generated approximately 35 standalone technical images before the architecture drift was identified. Some images are useful. Others contain superseded or incorrect architecture and must be tagged accordingly.

## 6. Image 01
System overview. Intended role: broad visual introduction to THERMA. Status: usable as a conceptual overview after correcting any small embedded text through PDF text rather than relying on image text.

## 7. Image 02
Exploded-view architecture. Intended role: explain modular construction. Status: conceptual communication asset; all dimensions remain non-authoritative.

## 8. Image 03
Internal cutaway attempt. Status: rejected as the primary engineering reference where it conflicts with later architecture.

## 9. Image 04
System energy-flow map. Intended role: show heat input, acoustic conversion, thermal output and rejection. Status: useful conceptual diagram.

## 10. Image 05
Fluid/piping architecture. Intended role: external thermal loops, pumps, valves and interfaces. Status: useful after numerical values are reconciled with the baseline.

## 11. Image 06
Modular architecture and mounting. Intended role: frame, modules and external packaging. Status: conceptual.

## 12. Early acoustic visuals
Later images include acoustic core, resonator, regenerator and related engineering sheets. These should be preferred over generic product renders when explaining thermoacoustic mechanics.

## 13. Heat-exchanger visuals
Heat-exchanger images can support explanation of hot/cold interfaces but must not be treated as validated exchanger dimensions or performance drawings.

## 14. Control visuals
Control-panel, sensors and DAQ diagrams are communication assets. The actual control implementation remains a prototype design task.

## 15. Safety visuals
The 1500 °C protection architecture is a conceptual safety diagram: raw extreme-temperature process fluid is diverted or recovered upstream before reaching the THERMA core.

## 16. Incorrect mechanical sequence
Images that show piston, displacer, connecting rod, crankshaft, flywheel, bearing housing, piston rings or similar reciprocating hardware belong to an accidental Stirling-like drift. They are not THERMA 3.5 architecture.

## 17. Do not delete history
The incorrect images remain useful as development-history artifacts because they document the point at which the project detected architecture drift. They should be retained outside the authoritative design set or clearly marked NOT THERMA 3.5.

## 18. Image 36–45 drift group
The later image sequence contains piston/displacer/connecting-rod/crankshaft/flywheel/bearing-cylinder-ring-pin parts. These are excluded from authoritative THERMA 3.5 design references.

## 19. Why the drift matters
A thermoacoustic system can use oscillating gas motion without a mechanical reciprocating power train. Adding pistons and crankshafts changes the thermodynamic and mechanical architecture and would turn the project into a different machine class.

## 20. PDF integration rule
When the final dossier is assembled, each image should be paired with authoritative PDF text containing: purpose, component names, flow direction, status, assumptions, and warnings about provisional dimensions.

## 21. Image text rule
Small generated text is not authoritative. Important information must be repeated as normal PDF text, tables or vector diagrams.

## 22. Cropping rule
Each image is intended to be a standalone full-canvas asset. Do not rely on cropping a multi-panel montage for an engineering figure.

## 23. Resolution rule
Use the highest practical resolution for standalone technical images. Readability of components and major labels takes priority over decorative density.

## 24. Color rule
Blue can represent cold-side flow, red/orange hot-side flow, green heat rejection or designated secondary thermal paths, and neutral metallic colors represent fixed hardware. Color is a visual aid, not a physical specification.

## 25. Component consistency
A component should appear across multiple drawings with consistent terminology. The same object should not become a turbine, piston or unrelated device in another drawing unless the file explicitly documents a historical branch.

## 26. System overview requirements
A correct master overview should show heat-source interface, hot heat exchanger, regenerator, acoustic core/resonator, cold heat exchanger, secondary loops, controls and safety boundary.

## 27. Thermal-flow requirements
A correct thermal-flow drawing should distinguish source heat, acoustic/work conversion, useful cooling or heating, and final heat rejection.

## 28. Acoustic-flow requirements
An acoustic drawing should show pressure/velocity oscillation, resonance or impedance, fixed geometry and the working-gas domain without implying a mechanical piston.

## 29. Regenerator drawing requirements
Show matrix, oscillating-gas direction, thermal gradient, heat exchange and design variables; do not invent experimentally validated pore size or lifetime.

## 30. Heat-exchanger drawing requirements
Show fluid-side separation, flow arrangement and thermal-interface role; keep effectiveness and pressure-drop values provisional unless validated.

## 31. Pressure-system drawing requirements
Show pressure boundary, ports, relief, isolation, sensors and inspection access. Pressure rating must never be inferred from a render.

## 32. Control drawing requirements
Show sensor inputs, control state, outputs to valves/pumps/acoustic drive, and independent safety layer.

## 33. Safety drawing requirements
Show detection, degraded mode, isolation, relief and safe shutdown. Include emergency bypass for high source temperature.

## 34. Prototype test-bench visual
A final test-bench image should show calibrated thermometry, flow meters, pressure sensors, acoustic microphones/transducers, DAQ, power measurement and relief/isolation hardware.

## 35. Simulation diagram
A useful simulation diagram should show: assumptions → model → parameter sweep → adversarial conditions → sensitivity → output → audit → prototype comparison.

## 36. Application diagram
Factory heat should enter a controlled thermal loop, not raw exhaust gas. Local THERMA nodes can then serve cooling or heating loads.

## 37. Community network image
A network image may show homes, restaurants, hospitals, shops and cold storage as loads, but the number of buildings served must remain scenario-dependent.

## 38. Environmental image
Environmental visuals should communicate avoided purchased energy and heat recovery, not claim that THERMA destroys heat or directly changes global temperature.

## 39. Historical image map
The image library should include a small metadata row for each asset: image number, date, subject, architecture state, intended document chapter, status and audit note.

## 40. Suggested status codes
PASS = usable conceptual asset; FIX = concept is useful but visual details need correction; REJECT = architecture invalid or misleading; HISTORY = retained only for development record.

## 41. Visual validation checklist
Before inclusion: correct architecture, correct flow arrows, no unsupported mechanical components, no contradictory temperatures, no fabricated experimental results, readable labels, correct terminology, and clear conceptual-status note.

## 42. 3.3 visual requirements
Rapid cooling diagrams should show transient cooling power, parallel modules and/or properly conditioned thermal buffering. Do not imply that a small single core automatically reaches 0–3 °C in minutes for arbitrary loads.

## 43. 3.4 visual requirements
3.4 should emphasize regenerator, heat-exchanger and streaming optimization, modularity and an initial favorable waste-heat operating range.

## 44. 3.5 visual requirements
3.5 should emphasize reversible thermal routing and acoustic control while preserving the fixed core.

## 45. Heating visual requirements
Heating diagrams should show low-temperature source, heat-pump path, hot-side delivery and energy balance. The 20→80 °C case remains a conceptual target, not a THERMA measurement.

## 46. Cooling visual requirements
Cooling diagrams should distinguish the cold-side temperature target from cooling capacity and show final heat rejection.

## 47. 1500 °C protection visual
The correct conceptual visual is: 1500 °C source → rated recovery HX/diverter → conditioned secondary loop → THERMA; direct 1500 °C core input is prohibited.

## 48. Documentation cross-link
Related files: 001 identity, 003 core physics, 004 resonator, 005 regenerator, 006 heat exchangers, 007 pressure/safety, 009 control, 011 rapid cooling, 012 evolution, 013 prototype, 020 master validation.

## 49. Final asset philosophy
The repository should preserve the image generation history while keeping the authoritative architecture in text and validated engineering data. The visual library supports communication; it does not replace exact-geometry calculation or experiment.

## 50. Closing status
The generated image set is a historical design asset collection. It is not an approved manufacturing package. The final THERMA 3.5 visual set must be rebuilt only after exact geometry and prototype data are established.
