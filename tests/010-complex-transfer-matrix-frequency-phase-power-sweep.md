# THERMA 3.5 — Iteration 010: Complex Transfer-Matrix Frequency, Phase and Power Sweep

## Purpose

Execute the next required model from Iteration 009 without repeating generic temperature sweeps. This run performs a reproducible **screening-level complex acoustic network calculation** for Prototype A.

This is not DeltaEC, SAGE, CFD, FEA, a pressure-vessel analysis, or a fabrication authorization. Several component-loss and load values are explicit assumptions used to expose sensitivity.

## 1. Inherited baseline

- Working gas: helium.
- Mean pressure: 1.0 MPa.
- Uniform screening temperature: 100 C = 373.15 K.
- Main bore ID: 50 mm.
- Main area: 1.9635e-3 m^2.
- Reference resonator section: 2.842 m.
- Hot HX reference length: 0.120 m.
- Regenerator reference length: 0.100 m.
- Cold HX reference length: 0.120 m.
- Frequency sweep: 70 to 130 Hz.
- Historical 2.548/2.55 m values remain historical notes only.

Using ideal-gas helium screening properties with R = 2077 J/kg-K and gamma = 1.667:

- rho = p/(RT) = 1.2903 kg/m^3.
- c = sqrt(gamma R T) = 1136.65 m/s.
- Characteristic impedance for volume velocity Zc = rho c/A = 7.469e5 Pa s/m^3.

The simple 2.842 m value remains a quarter-wave reference for an isolated uniform section. It is not the full-network resonance length.

## 2. Complex state model

The propagated state is:

x = [p, U]^T

where p and U are complex pressure and complex volume velocity amplitudes.

For each uniform screening segment:

[p2]   [ cosh(gL)       Zc sinh(gL) ] [p1]
[U2] = [ sinh(gL)/Zc    cosh(gL)    ] [U1]

with:

g = alpha + j k
k = 2 pi f/c

A lumped screening series resistance is represented by:

[p2]   [1 R] [p1]
[U2] = [0 1] [U1]

The complete matrix is the ordered product of the hot HX, regenerator, cold HX and resonator matrices.

Local average acoustic power is evaluated as:

Wdot_ac = 0.5 Re[p U*]

Sign depends on the chosen propagation direction; magnitude and power differences are used for screening.

## 3. Explicit V1 loss assumptions

These values are NOT measured THERMA values and are NOT claims about manufacturable hardware.

Component screening parameters:

- Hot HX: L = 0.120 m, alpha = 0.8 1/m, series R = 15,000 Pa s/m^3.
- Regenerator: L = 0.100 m, alpha = 2.5 1/m, series R = 35,000 Pa s/m^3.
- Cold HX: L = 0.120 m, alpha = 0.8 1/m, series R = 15,000 Pa s/m^3.
- Resonator: L = 2.842 m, alpha = 0.03 1/m, no added lumped R.

These are deliberately exposed sensitivity parameters, not fitted experimental correlations.

## 4. Boundary cases

### Case A — ideal standing-wave reference

A reflecting/closed-end reference is retained conceptually to verify that strong pressure resonance does not imply net through-power.

For the ideal lossless standing-wave reference, pressure and volume velocity are predominantly in quadrature, so the cycle-average real acoustic power tends toward zero away from dissipative elements.

### Case B — finite complex load

The executable screening case uses:

ZL = 0.25 Zc (1 + 0.5 j)

This is a deliberately finite complex load used to test phase-sensitive power flow. It is not a measured termination impedance.

## 5. Frequency-sweep result

For the stated loss and finite-load assumptions, the input-impedance imaginary part crosses zero at approximately:

**81.27 Hz**

within the 70–130 Hz sweep.

This result must NOT be interpreted as the final THERMA resonance frequency. It is the resonance-like condition of this specific assumed full network.

Important comparison:

- Isolated 2.842 m quarter-wave section at 100 C: approximately 100 Hz by construction.
- Adding the 0.340 m core references produces a simple total physical-path quarter-wave scale of approximately c/[4(3.182 m)] = 89.3 Hz before component impedance and loss effects.
- The assumed finite-load/loss network produces approximately 81.27 Hz.

Therefore the full network can shift the apparent resonance materially away from the isolated 2.842 m reference.

## 6. Phase and power map at the finite-load screening condition

The following values use a prescribed 50 kPa complex input-pressure amplitude only as a normalization/reference amplitude. They are not a prediction that the thermal system can generate this pressure amplitude.

At approximately 81.27 Hz:

| Location | |p| Pa | |U| m^3/s | phase(p)-phase(U), rad | Wdot_ac W |
|---|---:|---:|---:|---:|
| Input | 50,000 | 0.02990 | -2.565 | -626 |
| Hot HX exit | 47,703 | 0.02734 | -2.320 | -444 |
| Hot HX resistance exit | 47,425 | 0.02734 | -2.314 | -439 |
| Regenerator exit | 44,835 | 0.02370 | -1.626 | -29 |
| Regenerator resistance exit | 44,796 | 0.02370 | -1.608 | -20 |
| Cold HX exit | 43,958 | 0.02742 | -1.353 | +130 |
| Cold HX resistance exit | 44,048 | 0.02742 | -1.344 | +136 |
| Resonator termination | 10,557 | 0.06493 | +0.650 | +273 |

The sign reversal follows the selected complex propagation convention and finite-load direction. The important screening result is that the model produces a nontrivial phase evolution and real-power redistribution; magnitude-only pressure would not reveal this.

Because the loss model is assumed rather than measured, these watt values are **normalization-dependent screening outputs**, not THERMA power predictions.

## 7. Resonator-length sensitivity attack

Keeping all other assumptions fixed and changing only the 2.842 m resonator section:

- -5% resonator length: resonance-like zero-imaginary-input condition approximately 85.06 Hz.
- Baseline length: approximately 81.27 Hz.
- +5% resonator length: approximately 77.81 Hz.

Conclusion: a 5% length error changes the modeled condition by several hertz. Geometry tolerance and thermal expansion cannot be treated as secondary issues.

## 8. What this run proves

PASS:

- The Prototype A screening geometry can be represented by a reproducible complex transfer-matrix chain.
- The isolated 2.842 m quarter-wave reference is not sufficient to predict the full-network resonance.
- Pressure magnitude alone is insufficient; phase changes substantially through the assumed component chain.
- A finite complex load can produce nonzero real acoustic power flow even when the standing-wave reference itself would have little net through-power.
- Resonator-length sensitivity is large enough to require explicit tolerance control and/or tuning strategy.

CONDITIONAL:

- Approximately 81.27 Hz is valid only for the stated screening loss/load assumptions.
- The phase/power map is useful for architecture screening but not yet for prototype performance prediction.
- The 50 kPa normalization amplitude is inherited from the earlier 5% drive-ratio scale and is not a demonstrated thermal-onset amplitude.

FAIL:

- Any claim that the old ~1.67 kW traveling-wave scale is actual cooling power.
- Any fabrication authorization based on this run.
- Any claim that the assumed HX/regenerator loss coefficients are measured hardware properties.

UNKNOWN:

- Exact regenerator impedance and thermoacoustic coupling.
- Oscillatory-flow HX correlations for the actual manufactured channels.
- Streaming and nonlinear effects.
- Real source and termination impedances.
- Thermally generated pressure amplitude.
- Qc, Qh and COP.

## 9. Failure analysis

The model exposes a major dependency: the apparent resonance is dominated not only by the nominal resonator length but also by the added core phase and boundary impedance.

Therefore a CAD drawing that simply uses a 2.842 m tube plus 120/100/120 mm cartridges would be an uncontrolled design, not a validated 100 Hz machine.

The next model must replace the assumed component losses with geometry-derived impedance and thermal interaction.

## 10. Redesign / next highest-value model

Iteration 011 shall build a **geometry-derived regenerator and oscillatory-HX submodel** before any full thermal-output claim.

Priority sequence:

1. Choose a manufacturable regenerator matrix concept and calculate porosity, hydraulic radius, gas volume and solid heat capacity.
2. Choose an actual HX channel count/diameter/spacing that fits the 50 mm core.
3. Derive oscillatory-flow hydraulic resistance and thermal interaction from geometry rather than arbitrary alpha/R placeholders.
4. Insert those complex impedances into the network.
5. Repeat the frequency/phase/power sweep.
6. Only after the acoustic model is geometry-derived, couple thermal-node temperatures and evaluate onset/thermal transfer.

## 11. Prototype ranking update

1. Prototype A straight measurement-first network — **CONDITIONAL BEST**.
2. Prototype B folded compact resonator — **UNKNOWN**.
3. Prototype C multi-branch impedance network — **UNKNOWN / HIGH RISK**.

Prototype A remains the best path because the new result demonstrates that even the simplest topology has enough phase/boundary sensitivity to justify measurement-first validation before additional branches or compact packaging are introduced.

## 12. Fabrication gate

**FAIL — NOT AUTHORIZED.**

The next gate is not generic optimization. It is replacement of assumed component impedances with geometry-derived regenerator/HX models and then a coupled acoustic/thermal rerun.
