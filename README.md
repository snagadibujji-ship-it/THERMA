# GHIA THERMA

**GHIA THERMA** is a conceptual/research-stage reversible thermoacoustic thermal platform. This repository is the engineering record for the project: physical logic, mathematics, thermodynamic calculations, acoustic concepts, simulation assumptions/results, failure-analysis history, prototype strategy, safety, economics, IP context, and the project's visual/diagram asset record.

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

## ✅ Closed documentation set — 20 core files

The documentation target is now **20 deep technical files**, not 100 mandatory files. The old 100-file planning document is retained only as historical planning context; it is **not the current completion target**.

### 001–005 — Foundation
- `docs/001-project-identity-and-scope.md`
- `docs/002-evidence-hierarchy-and-source-discipline.md`
- `docs/003-problem-statement.md`
- `docs/004-thermoacoustic-fundamentals.md`
- `docs/005-heat-engine-principle.md`

### 006–010 — Thermal modes and architecture
- `docs/006-refrigeration-principle.md`
- `docs/007-heat-pump-heating-principle.md`
- `docs/008-reversible-operation.md`
- `docs/009-architecture-overview.md`
- `docs/010-terminology-and-glossary.md`

### 011–015 — Core hardware and thermal/acoustic engineering
- `docs/011-working-gas-candidates.md`
- `docs/012-pressure-and-containment.md`
- `docs/013-acoustic-resonator.md`
- `docs/014-inertance-compliance-network.md`
- `docs/015-regenerator-physics.md`

### 016–020 — Validation, safety, economics and records
- `docs/016-thermal-penetration-and-boundary-layers.md`
- `docs/017-hot-heat-exchanger.md`
- `docs/018-cold-heat-exchanger.md`
- `docs/019-acoustic-streaming-and-nonlinear-losses.md`
- `docs/020-master-validation-ip-visual-audit.md`

**Each core file is intended to be a substantive engineering chapter.** The current target is meaningful depth, not an arbitrary line count; no file is padded to hit a number.

## Visual assets
The project generated approximately 35 standalone visual artifacts during the first illustration pass. These are treated as **communication assets**, not authoritative fabrication drawings. Several late images drifted into piston/Stirling-like architecture; those are excluded from THERMA 3.5 architecture claims and are documented as historical/invalid/replacement candidates rather than silently reused.

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

## Documentation close-out
The 20-file documentation set is the current baseline. Future work should focus on exact-geometry modeling, reproducible simulation, CAD, test instrumentation, prototype construction, measured datasets, prior-art/claim review and experimentally validated updates rather than adding filler documentation files.
