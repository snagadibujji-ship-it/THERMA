# GHIA THERMA — Current 20-File Engineering Documentation Index

This repository is the canonical text-first documentation baseline for GHIA THERMA. The previous 100-file planning list was a planning artifact; it is no longer the completion target. The **current closed documentation set is 20 core technical files**.

## Current architecture lock
THERMA 3.5 is a fixed-hardware thermoacoustic core with oscillating working gas. There is no piston, displacer, crankshaft, connecting rod, flywheel, reciprocating mechanical compressor, or mechanical-bearing power train in the thermoacoustic core. Pumps and valves may exist in external secondary thermal-fluid loops.

## Documentation rule
The twenty files are organized as a technical record rather than a quota. Some documents are longer or shorter depending on the subject. No file should be padded with repeated prose merely to reach an arbitrary line count. Source-derived facts, first-principles calculations, THERMA screening outputs and hardware-only evidence must remain distinguishable.

## 001–005 — Foundation
001 `project-identity-and-scope.md`
002 `evidence-hierarchy-and-source-discipline.md`
003 `problem-statement.md`
004 `thermoacoustic-fundamentals.md`
005 `heat-engine-principle.md`

## 006–010 — Thermal modes and architecture
006 `refrigeration-principle.md`
007 `heat-pump-heating-principle.md`
008 `reversible-operation.md`
009 `architecture-overview.md`
010 `terminology-and-glossary.md`

## 011–015 — Core hardware and thermal/acoustic engineering
011 `working-gas-candidates.md`
012 `pressure-and-containment.md`
013 `acoustic-resonator.md`
014 `inertance-compliance-network.md`
015 `regenerator-physics.md`

## 016–020 — Core engineering, audit and closure
016 `thermal-penetration-and-boundary-layers.md`
017 `hot-heat-exchanger.md`
018 `cold-heat-exchanger.md`
019 `acoustic-streaming-and-nonlinear-losses.md`
020 `master-validation-ip-visual-audit.md`

## Closed-set coverage
- Project identity and development history
- Evidence hierarchy and source discipline
- Thermoacoustic physical foundations
- Heat-driven engine mode
- Refrigeration and 0–3 °C target
- Heat-pump heating and 20→80 °C target case
- Reversible mode switching
- Working gas and pressure boundary
- Resonator, impedance, inertance and compliance
- Regenerator physics and thermal boundary layers
- Hot/cold heat exchangers
- Streaming and nonlinear losses
- Secondary thermal loops
- Sensors, control and safety logic
- Rapid cooling / 3.3 evolution
- 3.4 and 3.5 architectural evolution
- Simulation methodology and historical result discipline
- Water-heating calculation and conditional 1.6 L/L screening result
- Cold-room/load modeling
- Energy-source and waste-heat use cases
- Economics and environmental reasoning
- Prototype engineering and validation
- Prior art and IP boundaries
- Visual-asset audit

## Visual asset status
Approximately 35 standalone visual artifacts were generated during the first illustration pass. They are communication assets only. Several late images drifted into piston/Stirling-like architecture and are excluded from THERMA 3.5 architecture claims; the final visual audit records those as historical/invalid/replacement candidates rather than silently reusing them.

## Evidence boundary
The supplied v1 dossier states that THERMA is conceptual/pre-prototype and that exact geometry, THERMA-specific performance, materials life, pressure integrity and certification remain to be validated. The documentation therefore does not treat generated illustrations, simplified screening COPs, scenario counts or illustrative scaling as experimental evidence.

## Prototype close-out rule
The documentation phase is considered closed when the twenty files are internally consistent. Future technical work should now concentrate on exact-geometry modeling, reproducible simulation, CAD, instrumentation, prototype fabrication, measured datasets, model-to-hardware correlation and formal IP/certification work rather than adding placeholder documentation files.
