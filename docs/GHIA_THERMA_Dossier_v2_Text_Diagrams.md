# GHIA THERMA — Dossier v2 Text-Diagrams Baseline

## Status
Conceptual/research-stage pre-prototype engineering record.

## Architecture lock
THERMA 3.5 is documented as a fixed-hardware thermoacoustic platform with oscillating working gas.

Core architecture excludes:
- piston
- displacer
- crankshaft
- connecting rod
- flywheel
- reciprocating mechanical compressor
- mechanical bearings in the thermoacoustic core

Core chain:

    HEAT SOURCE
         |
         v
    SOURCE CONDITIONING HX
         |
         v
       HOT HX
         |
         v
     REGENERATOR
         |
         v
    FIXED ACOUSTIC CORE
    resonator / inertance / compliance
         |
         v
       COLD HX
         |
         v
      0–3 °C LOAD

Reversible heating route uses the same fixed architecture with acoustic-field/thermal-interface routing toward a higher-temperature secondary water loop.

## Evidence discipline
A — established external science/standards
B — first-principles calculation
C — THERMA screening/design target
D — hardware-only fact requiring measurement

No THERMA-specific COP, pressure integrity, leakage, fatigue life, exact geometry, certification, or production readiness is treated as experimentally proven.

## Key calculated reference
For 1 L of water, 20 °C to 80 °C:
Q = m cp ΔT ≈ 69.8 Wh.

Historical screening case used COP_H ≈ 2.1 and source-water cooling from 20 °C to 0 °C, producing an approximate 1.6 L source-water per 1 L hot-water ratio. This is conditional on those assumptions and is not a universal THERMA property.

## Prototype gate
1. Freeze exact geometry from a reproducible acoustic/thermal model.
2. Verify materials and pressure design.
3. Validate heat exchangers and regenerator geometry.
4. Build a single-core instrumented proof-of-physics prototype.
5. Measure acoustic, thermal, containment, control and endurance performance.
6. Correlate measured data with the model.
7. Only then proceed toward certification/conformity and product engineering.
