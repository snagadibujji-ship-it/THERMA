# GHIA THERMA

**GHIA THERMA** is a conceptual/research-stage reversible thermoacoustic thermal platform. The repository is the engineering record for the project: physical logic, mathematics, thermodynamic calculations, acoustic concepts, simulation assumptions/results, failure-analysis history, prototype strategy, safety, economics, IP context, and the project's visual/diagram asset record.

## 🔒 THERMA 3.5 architecture lock

THERMA 3.5 is documented as a **fixed-hardware thermoacoustic core with oscillating working gas**.

### Core architecture — allowed
- Hot heat exchanger
- Cold heat exchanger
- Regenerator / structured thermal matrix
- Acoustic resonator
- Inertance / compliance / impedance elements
- Pressurized working-gas boundary
- Secondary thermal loops
- Pumps and valves in external thermal loops
- Sensors, DAQ, controller and independent safety hardware

### Core architecture — prohibited
- No piston
- No displacer
- No crankshaft
- No connecting rod
- No flywheel
- No reciprocating mechanical compressor
- No mechanical-bearing power train in the thermoacoustic core

The working gas moves back and forth **acoustically**; that oscillatory fluid motion is not equivalent to a mechanical piston or reciprocating engine.

## Evidence discipline
All major content is classified as one of:

1. **A — Established external science**
2. **B — First-principles calculation**
3. **C — THERMA screening/design hypothesis**
4. **D — Hardware-only evidence**

A green simulation result is not treated as a hardware measurement. Earlier screening COPs, scaling assumptions, Monte Carlo counts and illustrative geometry remain historical/design information unless independently reproduced and validated.

## Main technical directions

```text
                         GHIA THERMA 3.5
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
        HEAT-DRIVEN MODE                     WORK-DRIVEN MODE
               │                                 │
      thermal gradient                    acoustic work
               │                                 │
               ▼                                 ▼
       acoustic generation                 heat pumping
               │                                 │
               ▼                                 ▼
       refrigeration stage                hot-water loop
               │
               ▼
          0–3 °C target
```

The project has also explored a conceptual **20 °C → 80 °C water-heating case**. The 69.8 Wh sensible-heating requirement for 1 L of water is a standard calculation; the historical 1.6 L source-water/L hot-water ratio is conditional on a screening COP and source-temperature drop and is **not** a measured THERMA property.

## Source baseline
The supplied v1 dossier describes THERMA as conceptual/pre-prototype and states that exact geometry, THERMA-specific performance, material life, pressure integrity, certification and commercial readiness remain unproven. It also distinguishes established science, calculations, project-model outputs and hardware-only facts. fileciteturn2file0L13-L29

## 100-file documentation system
The repository now uses a planned **100-file engineering record**. The index is in `docs/100-file-index.md` and points to the full documentation map across foundations, physics, thermal systems, simulation, energy sources, economics, safety, materials, prototype validation, applications, IP, visual assets and the master research record.

### Documentation map
- `docs/001-010` — identity, evidence discipline, problem, thermoacoustic foundations, heat-engine/refrigeration/heating principles, reversible operation, architecture and glossary
- `docs/011-020` — working gas, pressure, resonator, impedance, regenerator, boundary layers, heat exchangers, streaming and secondary loops
- `docs/021-030` — source conditioning, rejection, cooling/heating loops, pressure/safety boundary, sensors, controls, reversible transitions and PFD/P&ID logic
- `docs/031-040` — equations, 20→80 °C calculation, cold-room model, 3.3/3.4/3.5 evolution, 24-hour/one-year simulations, adversarial testing and simulation audit
- `docs/041-050` — energy-source pathways, waste heat, economics, comparison cases, industrial networks and environmental accounting
- `docs/051-060` — deeper acoustic engineering and losses
- `docs/061-070` — deeper thermal engineering, heat-exchanger methodology and energy balances
- `docs/071-080` — materials, fatigue, leakage, overtemperature, emergency protection and lifecycle
- `docs/081-090` — prototype, BOM, instrumentation, testing, endurance and model-to-hardware correlation
- `docs/091-100` — applications, IP, portfolio, history, image/diagram index, audit ledger and final master record

## Visual assets
The project generated approximately 35 standalone visual artifacts during the first illustration pass. These are treated as **communication assets**, not authoritative fabrication drawings. Several late images drifted into piston/Stirling-like architecture; those are excluded from THERMA 3.5 architecture claims and should be marked historical/invalid/replacement candidates in the final asset index rather than silently reused.

## Research workflow

```text
DEFINE
  ↓
MODEL
  ↓
INDEPENDENTLY REPRODUCE
  ↓
ATTACK ASSUMPTIONS
  ↓
FAILURE ANALYSIS
  ↓
REDESIGN
  ↓
PROTOTYPE
  ↓
MEASURE
  ↓
MODEL ↔ HARDWARE CORRELATION
  ↓
REGRESSION / ENDURANCE
  ↓
FREEZE OR REDESIGN
```

## Prototype gate
Before physical fabrication, the project still needs an exact reproducible acoustic/thermal geometry, qualified pressure design, helium handling/leak procedure, oscillatory-flow heat-exchanger validation, controlled regenerator geometry, calibrated instrumentation, independent safety layers and predefined cooling/heating/mode-switch/endurance acceptance tests.

## Important status statement
THERMA is **not** currently presented as a certified production refrigerator/heater, a proven 100-year machine, or an experimentally validated THERMA-specific COP. The intended next engineering milestone is a heavily instrumented proof-of-physics prototype.

## Repository purpose
This repository is the source-of-truth text record for the project's engineering reasoning. Supporting images, calculations, datasets, CAD, simulation code and future prototype measurements should be linked to the appropriate numbered documentation files rather than inserted without evidence labels.
