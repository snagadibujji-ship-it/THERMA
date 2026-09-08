# THERMA 3.5 — Iteration 009: Geometry Freeze V1 and Phase-Power Model

## Purpose

Continue from tests 006–008 without repeating generic temperature sweeps. The objective is to create a solver-ready **assumption-controlled Prototype A geometry** so the next iteration can run a reproducible complex transfer-matrix frequency/phase/power calculation.

This is a MODEL GEOMETRY FREEZE FOR SCREENING, not fabrication authorization.

## Inherited reference

- Gas: helium.
- Mean pressure: 1.0 MPa.
- Reference frequency: 100 Hz.
- Reference straight-tube ID: 50 mm.
- Corrected simple quarter-wave reference at 100 C: 2.842 m.
- Historical 2.548/2.55 m values are retained only as prior screening notes.
- Regenerator reference length: 100 mm.
- Hot HX reference length: 120 mm.
- Cold HX reference length: 120 mm.
- Nominal source/sink/cold target: 100 C / 35 C / 3 C.

## Critical architecture decision

Prototype A remains a **measurement-first acoustic test article**. It is not yet a complete heat-driven refrigerator claim. Its first job is to establish resonance, complex pressure/velocity phase, component impedance and acoustic power flow under a defined boundary condition.

Topology:

[drive / pressure boundary]
  -> [hot-HX cartridge]
  -> [regenerator cartridge]
  -> [cold-HX cartridge]
  -> [straight resonator]
  -> [termination]

## Geometry Freeze V1 — explicit screening assumptions

### Main bore and resonator

- Main circular bore ID: 50.0 mm.
- Main area: pi*(0.025 m)^2 = 1.9635e-3 m^2.
- Acoustic resonator length reference: 2.842 m from the 100 C quarter-wave calculation.
- For the first matrix run, the 2.842 m value is treated as the acoustic reference section length, with core phase effects solved separately rather than hidden inside a corrected physical length.
- No bends or branches in V1.

### Hot HX V1

- Axial cartridge length: 120 mm.
- Screening flow passage: straight parallel channels.
- Channel hydraulic diameter: 1.0 mm ASSUMPTION.
- Channel count: to be selected so the total open flow area does not exceed the 50 mm-bore area; exact manufacturable count remains UNKNOWN.
- Wall material: stainless-steel screening placeholder.
- Hot boundary: 100 C screening node.

### Regenerator V1

- Axial length: 100 mm.
- Flow path: distributed porous/microchannel equivalent.
- Nominal hydraulic scale: 0.50 mm screening gap.
- Matrix material: stainless-steel screening placeholder.
- Porosity, exact wire geometry and solid heat capacity: UNKNOWN and therefore not validated.

### Cold HX V1

- Axial cartridge length: 120 mm.
- Screening flow passage: straight parallel channels.
- Channel hydraulic diameter: 1.0 mm ASSUMPTION.
- Wall material: stainless-steel screening placeholder.
- Cold-side thermal boundary: not fixed to 3 C in the acoustic-only solve; 3 C remains the system target, not a guaranteed local gas temperature.

### Junctions

- V1 uses concentric, equal-area interfaces where possible.
- Abrupt area-ratio loss coefficient is therefore set to zero only for the ideal skeleton.
- Real transition loss coefficient: UNKNOWN; must enter the sensitivity attack.

### Inertance / compliance

- No separate inertance tube in Prototype A V1.
- No explicit compliance volume in Prototype A V1.
- Any effective source/termination compliance is represented by the complex boundary impedance.

### Boundary conditions

- Drive boundary: complex pressure source or prescribed source impedance; absolute amplitude is swept separately.
- Termination: first run uses ideal closed-end/reflecting boundary as the standing-wave reference.
- Second boundary case: finite complex load impedance sensitivity.
- These boundaries are MODEL assumptions, not measured hardware properties.

## Complex acoustic equations

State vector:

x = [p, U]^T

Local acoustic power:

Wdot_ac(x) = 0.5 Re[p(x) U*(x)]

For an ideal uniform lossless duct:

[p2]   [ cos(kL)      j Zc sin(kL) ] [p1]
[U2] = [ j/Zc sin(kL) cos(kL)      ] [U1]

where:

Zc = rho*c/A
k = omega/c
omega = 2*pi*f

For lossy components, k and/or impedance become complex and the component matrix must report dissipated acoustic power.

## Mandatory outputs for Iteration 010

1. Frequency sweep around the reference resonance, initially 70–130 Hz.
2. Input impedance magnitude and phase.
3. Complex p and U at every component boundary.
4. Phase difference phi = angle(p) - angle(U).
5. Local Wdot_ac = 0.5 Re[p U*].
6. Acoustic power loss across each component.
7. Sensitivity to resonator length, termination impedance and component loss.
8. Standing-wave reference case versus finite-load case.

## Attack hypotheses

H1: The ideal closed-end network will show strong standing-wave resonance but little net through-power away from dissipative elements.

H2: Adding realistic regenerator/HX resistance and a finite complex load can create nonzero local acoustic power flow while also dissipating power.

H3: The phase at the regenerator is architecture-sensitive; pressure amplitude alone cannot determine useful thermoacoustic behavior.

H4: Geometry/termination uncertainty may dominate the result, so sensitivity must be reported before thermal performance claims.

## Current status

PASS:

- Solver skeleton topology.
- Explicit reference dimensions for the first network model.
- Complex p/U and phase-power formulation.
- Straight no-branch Prototype A ranking.

CONDITIONAL:

- 50 mm, 100 Hz, 1 MPa baseline.
- 100 mm regenerator and 120 mm HX references.
- 1 mm HX hydraulic diameter assumptions.
- 0.50 mm regenerator hydraulic scale assumption.

FAIL:

- Fabrication authorization.
- Cooling-capacity claim.
- COP claim.
- Treating the 2.842 m acoustic reference as a final manufactured length.

UNKNOWN:

- Real manufactured HX channel count and geometry.
- Regenerator porosity and exact matrix.
- Measured source/termination impedance.
- Real transition losses.
- Streaming.
- Exact acoustic-to-thermal conversion.
- Qc, Qh and COP.

## Prototype ranking

1. Prototype A straight measurement-first network — CONDITIONAL BEST.
2. Prototype B folded compact resonator — UNKNOWN.
3. Prototype C multi-branch impedance network — UNKNOWN / high risk.

## Decision

Iteration 010 shall execute the defined V1 complex transfer-matrix model, first as an ideal standing-wave reference and then with explicit finite component losses and boundary-impedance sensitivity. The objective is to determine whether the selected geometry produces a measurable, controllable phase/power map before any thermal-output or fabrication claim.
