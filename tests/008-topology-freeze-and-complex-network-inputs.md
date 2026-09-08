# THERMA 3.5 — Iteration 008: Topology Freeze and Complex-Network Input Gate

## Purpose

This iteration continues from tests 006 and 007. It does not repeat generic source-temperature sweeps. Its purpose is to convert the current reduced-order candidate into a reproducible **Prototype A acoustic test topology** and explicitly separate what is defined from what is still unknown.

This document is a design/model gate, not a claim that the complete thermoacoustic machine is fabrication-ready.

## Inherited validated screening reference

- Working gas: helium.
- Mean pressure: 1.0 MPa.
- Reference frequency: 100 Hz.
- Reference straight-tube ID: 50 mm.
- Corrected simple quarter-wave reference: approximately 2.842 m at 100 C.
- Regenerator reference length: 100 mm.
- Nominal regenerator gap: 0.50 mm.
- Hot HX reference length: 120 mm.
- Cold HX reference length: 120 mm.
- Nominal source: 100 C.
- Nominal sink: 35 C.
- Nominal cold target: 3 C.

The earlier 2.548/2.55 m values remain historical screening notes only.

## Critical correction retained

The scalar quantity p_amp^2 A /(2 rho c) is a traveling-wave power scale under the associated plane-wave assumptions. It is not proof of net acoustic power in a standing-wave field and is not cooling capacity.

The next model must use complex pressure p and complex volume velocity U:

Wdot_ac(x) = 0.5 Re[p(x) U*(x)].

Large pressure amplitude alone is therefore insufficient evidence of useful power flow.

## Prototype A topology: measurement-first acoustic core

The first hardware/model candidate is intentionally simplified to remove branch ambiguity:

[defined acoustic termination]
        |
        v
[straight resonator section]
        |
        v
[cold HX cartridge]
        |
        v
[regenerator cartridge]
        |
        v
[hot HX cartridge]
        |
        v
[defined pressure boundary / closure]

This topology is ranked ahead of folded and multi-branch architectures for the first exact-network model because it minimizes junction uncertainty and supports direct pressure/phase instrumentation.

## What is now defined enough for the network skeleton

PASS:

- Gas family: helium.
- Mean-pressure screening point: 1.0 MPa.
- Reference frequency: 100 Hz.
- Reference main-bore diameter: 50 mm.
- Straight quarter-wave reference scale: approximately 2.842 m at 100 C.
- Component order: hot HX -> regenerator -> cold HX -> resonator.
- Requirement for complex p/U propagation.

## Missing geometry that blocks a full numerical result

FAIL / UNKNOWN:

1. Exact termination impedance.
2. Exact resonator length allocation after subtracting core lengths and end corrections.
3. Hot HX channel hydraulic diameter, pitch, count, wall thickness and material.
4. Cold HX channel hydraulic diameter, pitch, count, wall thickness and material.
5. Regenerator matrix type, porosity, hydraulic radius, wire/channel geometry and solid material.
6. Core-to-resonator area transitions and loss coefficients.
7. Compliance volume, if any.
8. Inertance geometry, if any.
9. External thermal resistances and actual thermal-node temperatures.
10. Drive/generation boundary condition and acoustic load definition.

Because these values are not yet measured or frozen, any numerical matrix result would be assumption-dominated. This iteration therefore refuses to invent them and label the result validated.

## Exact solver contract for Iteration 009

The next executable model shall represent each element by a two-port complex transfer relation:

[p2, U2]^T = M_i(f, gas state, geometry, losses) [p1, U1]^T.

The complete network shall form:

M_system = M_N ... M_2 M_1.

For every frequency point, report:

- resonance condition / input impedance,
- |p| map,
- |U| map,
- phase(p)-phase(U),
- local acoustic power flow 0.5 Re[p U*],
- component pressure drop,
- component acoustic dissipation,
- sensitivity to geometry uncertainty.

Only after the acoustic solution is internally closed may thermal conversion be coupled to:

- regenerator heat exchange,
- hot HX thermal resistance,
- cold HX thermal resistance,
- external heat leak,
- source/sink approach temperatures,
- Qc, Qh and COP.

## Prototype ranking after this iteration

1. Prototype A: straight measurement-first acoustic core — CONDITIONAL BEST.
2. Prototype B: folded compact resonator — UNKNOWN until bend/junction losses are modeled.
3. Prototype C: multi-branch impedance network — UNKNOWN / high complexity.

## Gate status

PASS:

- Corrected quarter-wave reference retained as a screening reference.
- Complex phase-aware power definition selected.
- Simplest first topology selected.
- Missing-input list made explicit.

CONDITIONAL:

- 50 mm / 100 Hz / 1 MPa baseline.
- 100 mm regenerator and 120 mm HX reference lengths.

FAIL:

- Fabrication freeze.
- Claim of net acoustic power from pressure amplitude alone.
- Claim of cooling capacity from reduced-order acoustic scaling.

UNKNOWN:

- Exact network resonance.
- Real p/U phase map.
- Net acoustic power flow.
- Regenerator impedance.
- Oscillatory HX effectiveness.
- Streaming.
- Qc, Qh and COP.

## Decision

The highest-value next action is no longer another generic sweep. It is an **exact-input acquisition and solver-ready geometry freeze** for Prototype A, followed immediately by the complex transfer-matrix frequency sweep and sensitivity attack.

Fabrication authorization remains NO.
