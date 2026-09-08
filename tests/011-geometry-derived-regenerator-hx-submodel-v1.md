# THERMA 3.5 — Iteration 011: Geometry-Derived Regenerator and HX Submodel V1

## Purpose

Replace the arbitrary attenuation and series-resistance placeholders used in Iteration 010 with explicit, reproducible geometry-derived screening parameters. This remains a reduced-order engineering model, not DeltaEC/SAGE/CFD validation and not fabrication authorization.

## 1. Inherited baseline

- Gas: helium
- Mean pressure: 1.0 MPa
- Screening mean temperature: 373.15 K
- Frequency neighborhood: 70–130 Hz
- Main bore ID: 50 mm
- Main area: 1.9635e-3 m^2
- Isolated quarter-wave reference: 2.842 m at approximately 100 Hz and 100 C
- Historical 2.548/2.55 m values: historical notes only
- Hot HX reference length: 0.120 m
- Regenerator reference length: 0.100 m
- Cold HX reference length: 0.120 m

Ideal-gas screening values inherited from Iteration 010:

- rho = 1.2903 kg/m^3
- c = 1136.65 m/s
- mu = 2.3e-5 Pa s (screening assumption)
- cp = 5193 J/kg-K (screening assumption)
- k_g = 0.18 W/m-K (screening assumption)

## 2. Regenerator matrix concept

V1 chooses a stainless-steel woven-screen matrix because it is manufacturable and gives an explicit first geometry.

Screening geometry:

- Core ID: 50 mm
- Core area A = 1.9635e-3 m^2
- Regenerator length Lr = 0.100 m
- Nominal wire diameter dw = 0.10 mm
- Nominal screen pitch = 0.50 mm
- Nominal porosity epsilon = 0.80
- Nominal hydraulic diameter dh = 0.20 mm
- Gas volume Vg = epsilon A Lr = 1.571e-4 m^3
- Solid volume Vs = (1-epsilon) A Lr = 3.927e-5 m^3

These are simulation-freeze assumptions only. Actual weave pitch, wire flattening and stack compression must be measured before hardware correlation.

## 3. Geometry-derived hydraulic screening

For oscillatory flow, the hydraulic diameter provides the first resistance scale. The steady Darcy form is used only as a dimensional screening estimate:

Delta p = f (L/dh) rho u^2/2

with Reynolds number:

Re = rho |u| dh / mu

This is not a claim that steady-flow friction directly predicts oscillatory loss. The oscillatory Womersley scale must be carried explicitly:

Wo = (dh/2) sqrt(omega rho/mu)

At 100 Hz with the stated screening properties:

Wo is approximately 0.59.

Therefore the regenerator is in a regime where viscous penetration is comparable to the channel scale and a simple steady friction factor is inadequate for final prediction.

## 4. Regenerator thermal interaction scales

Thermal penetration depth screening scale:

delta_k = sqrt(2 k_g/(rho cp omega))

At 100 Hz this gives approximately 0.26 mm.

The nominal hydraulic diameter of 0.20 mm is therefore deliberately in the same order as the thermal penetration scale. This is useful for heat exchange but increases viscous-loss sensitivity.

Viscous penetration scale:

delta_v = sqrt(2 mu/(rho omega))

At 100 Hz this gives approximately 0.24 mm.

Important consequence:

The chosen 0.20 mm hydraulic scale is smaller than or comparable to both screening penetration depths. The gas cannot be treated as an inviscid plug flow in the matrix.

STATUS: CONDITIONAL — promising for thermal contact, high loss risk.

## 5. Regenerator solid thermal capacity scale

Using stainless steel screening values:

- rho_s = 8000 kg/m^3
- cp_s = 500 J/kg-K

Solid heat capacity of the V1 matrix:

Cs = rho_s Vs cp_s ≈ 157 J/K.

Gas heat capacity in the void volume:

Cg = rho Vg cp ≈ 1.05 J/K.

Thus the solid matrix has approximately two orders of magnitude larger thermal capacity than the contained gas in this screening geometry.

STATUS: PASS as a qualitative regenerator-capacity check.

## 6. Heat-exchanger channel concept

V1 replaces the arbitrary HX resistance placeholders with an explicit channel-count geometry.

Each HX is represented as a 50 mm-ID cartridge containing 19 parallel circular channels of 3.0 mm diameter over 120 mm length.

Per HX:

- Channel count N = 19
- Channel ID d = 3.0 mm
- Channel length L = 0.120 m
- Total open flow area = N pi d^2/4 = 1.343e-4 m^2
- Main-bore area = 1.9635e-3 m^2
- Open-area ratio ≈ 0.068

This creates a severe area contraction if connected directly to the 50 mm bore. Therefore abrupt direct transitions are rejected.

## 7. HX redesign after attack

A 19 x 3 mm channel bundle is rejected as the primary flow path because its open area is only about 6.8% of the main bore, creating an unacceptable first-order impedance discontinuity.

Revised V1 HX concept:

- 37 parallel channels
- Channel ID: 4.0 mm
- Channel length: 0.120 m
- Total open area = 4.650e-4 m^2
- Open-area ratio ≈ 0.237

Still too restrictive for a direct abrupt transition, but substantially improved. The HX must use a distributed/annular or tapered transition rather than a sudden contraction.

STATUS: CONDITIONAL — geometry is now explicit, but transition design remains a major loss item.

## 8. Oscillatory HX checks

At 100 Hz, for 4 mm channels:

Wo ≈ 11.8 using radius as the characteristic scale.

This is strongly different from the regenerator. The HX channels can support a more core-like oscillatory profile than the 0.20 mm regenerator passages, but oscillatory entrance, manifold and thermal boundary effects remain unresolved.

Thermal penetration depth remains approximately 0.26 mm, much smaller than the 2 mm channel radius. Therefore wall heat transfer depends strongly on surface area, oscillatory boundary layers and channel geometry; bulk-gas equilibrium cannot be assumed.

STATUS: UNKNOWN for actual HX effectiveness until oscillatory-flow heat-transfer correlations are selected or validated.

## 9. First impedance hierarchy conclusion

The geometry-derived screening strongly suggests:

1. Regenerator passages dominate viscous/thermal coupling.
2. HX manifolds and area transitions can dominate discrete impedance loss.
3. The 2.842 m resonator length alone cannot control the final resonance.
4. Any future network model must include explicit transition impedances.

This is a stronger and more physically grounded conclusion than the arbitrary alpha/R chain used in Iteration 010.

## 10. Failure analysis

FAIL:

- Treating the old assumed alpha/R values as hardware properties.
- Using abrupt 50 mm-bore to small-channel HX contractions.
- Assuming the nominal 0.20 mm regenerator hydraulic scale is automatically low-loss.
- Treating steady-flow friction alone as an oscillatory-flow model.

UNKNOWN:

- Exact complex impedance of the woven-screen stack.
- Stack compression and real porosity after assembly.
- Oscillatory pressure-drop correlation.
- Oscillatory HX Nusselt correlation for the chosen geometry.
- Streaming and nonlinear minor losses.

## 11. Redesign / Iteration 012

The next highest-value model shall create a geometry-derived impedance chain using:

- distributed regenerator resistance/reactance based on the selected pore scale,
- explicit HX open area and transition impedance,
- separate viscous and thermal penetration scales,
- parameter ranges for porosity and hydraulic diameter,
- finite termination impedance,
- complex frequency sweep and phase/power map.

The purpose is not to claim final watts. It is to determine whether the geometry-derived network preserves a useful phase structure without losses overwhelming the system.

## 12. Prototype ranking update

1. Prototype A straight measurement-first network — CONDITIONAL BEST.
2. Prototype B folded compact resonator — UNKNOWN.
3. Prototype C multi-branch impedance network — UNKNOWN / HIGH RISK.

## 13. Fabrication gate

FAIL — NOT AUTHORIZED.

This iteration improves the geometry definition but does not validate pressure-vessel design, welds, seals, material compatibility, helium leakage, nonlinear streaming, thermoacoustic onset, Qc/Qh/COP, or measured performance.
