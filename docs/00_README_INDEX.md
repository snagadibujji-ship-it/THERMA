# GHIA THERMA — 100-File Engineering Knowledge Base

## Scope
This repository is the working documentation baseline for GHIA THERMA. The 100-file set is organized as a numbered engineering knowledge base. Each file is intended to be a substantial technical module, with diagrams written as text where useful and with clear separation between established science, calculations, THERMA design hypotheses, and hardware-only facts.

## Architecture lock
**THERMA 3.5 is a fixed-hardware thermoacoustic platform.** The intended core contains oscillating working gas, acoustic resonator/impedance elements, regenerator, heat exchangers, pressure boundary, thermal loops, instrumentation, controls, and safety systems.

The core architecture explicitly excludes mechanical reciprocating hardware such as pistons, displacers, crankshafts, connecting rods, flywheels, and mechanical bearings. Those appeared later in generated image work and are excluded from the THERMA 3.5 baseline.

## Evidence discipline
- **A — Established:** external science, literature, standards, prior art.
- **B — Calculated:** first-principles calculations from stated assumptions.
- **C — THERMA model:** project screening, architecture hypotheses, design targets.
- **D — Hardware:** requires physical measurement.

Historical simulation values must not be presented as measured THERMA performance.

## 100-file map
01–10: project identity, evidence rules, problem, existing technologies, thermoacoustic fundamentals.
11–20: engine/refrigeration/heat-pump modes, reversibility, architecture, gas, pressure, resonator, regenerator, HX.
21–30: thermal loops, safety, 3.3/3.4/3.5 evolution, temperature envelope, equations, water heating, cold rooms, energy sources, lifecycle simulation.
31–40: economics, environmental analysis, network scaling, simulation history, failure logic, lifecycle philosophy, Monte Carlo, reality filter, simulation audit, materials/manufacturing.
41–50: prototype architecture, test plan, funding, prior art, interview package, risks, conclusions, references, core diagrams, control diagrams.
51–60: acoustic subsystem deep dives, regenerator/hx design, gas management, pressure boundary, thermal interfaces, sensor/control, safety logic, maintenance, serviceability, modularity.
61–70: cooling applications, heating applications, industrial integration, waste heat recovery, river/source-water heating, rapid cooling, storage, load modelling, annual operations, cost modelling.
71–80: validation strategy, uncertainty, model verification, reproducibility, adversarial scenarios, fault trees, 1500°C event, material lifecycle, fabrication planning, prototype BOM.
81–90: prototype commissioning, instrumentation, DAQ, calibration, data reduction, acceptance criteria, endurance, field pilot planning, IP claims framework, prior-art comparison.
91–100: glossary, equations, assumptions register, decision log, version history, image/diagram index, simulation audit ledger, prototype gate, interview summary, master project index.

## Status
This index is a roadmap for the 100-file set. Files are expanded sequentially and should point back to this README and to related modules where dependency exists.