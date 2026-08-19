# THERMA 3.5 — Exact-Geometry Coupled Screening Simulation v1

## 0. Purpose

This run converts the previously identified critical path into one internally consistent design-study baseline.

The purpose is not to claim that THERMA 3.5 has been experimentally proven.

The purpose is to answer:

1. What happens when one exact candidate geometry is frozen?
2. Which variables dominate?
3. Where does the candidate fail?
4. Which values are physically plausible?
5. What measurements are required before fabrication?
6. Which design choices must be changed before hardware?

## 1. Architecture lock

THERMA 3.5 is modeled as fixed thermoacoustic hardware with an oscillating working gas.

No piston is used.

No displacer is used.

No crankshaft is used.

No connecting rod is used.

No flywheel is used.

No reciprocating mechanical compressor is used.

External pumps and valves are allowed only in secondary thermal-fluid loops.

## 2. Candidate exact-geometry baseline

This is an **exact candidate geometry for simulation only**. It is not a certified fabrication drawing.

| Parameter | Baseline |
|---|---:|
| Working gas | Helium |
| Mean pressure | 1.00 MPa |
| Reference gas temperature | 300 K |
| Frequency | 100 Hz |
| Resonator ID | 50 mm |
| Quarter-wave acoustic length | 2.548 m |
| Regenerator length | 100 mm |
| Regenerator hydraulic gap | 0.50 mm |
| Hot HX axial length | 120 mm |
| Cold HX axial length | 120 mm |
| Drive ratio | 5% |
| Hot-source case | 100 °C |
| Heat-sink case | 35 °C |
| Cold target | 3 °C |

The quarter-wave length is a first-order acoustic estimate using:

c = sqrt(gamma R T)

and

L = c/(4 f).

For helium at 300 K, gamma ≈ 1.667 and R ≈ 2077 J/kg-K.

This gives c ≈ 1019.2 m/s and L ≈ 2.548 m.

## 3. Important limitation

This is still a reduced-order screening model.

It does NOT solve:

- full nonlinear Rott thermoacoustics
- exact acoustic boundary conditions
- Gedeon streaming
- turbulent/transition heat transfer
- exact regenerator loss
- exact HX pressure drop
- weld fatigue
- detailed shell mechanics
- full CFD
- exact DeltaEC/SAGE geometry

Therefore the results below are decision-support values, not hardware predictions.

## 4. Acoustic wavelength and packaging

At 100 Hz:

c ≈ 1019.2 m/s

lambda = c/f ≈ 10.19 m

A quarter-wave section is ≈ 2.548 m.

This immediately creates a packaging problem.

A 2.55 m acoustic path can be physically coiled, folded, or implemented using a different resonator topology, but every bend, junction and area change can add acoustic loss.

Therefore:

**Packaging is not independent of acoustic efficiency.**

## 5. Frequency-temperature drift

For a fixed acoustic length:

f approximately scales with sqrt(T).

For the same 2.548 m path, first-order predicted resonance becomes:

| Gas temperature | Approx. resonance |
|---:|---:|
| 20 °C | 98.85 Hz |
| 35 °C | 101.35 Hz |
| 60 °C | 105.38 Hz |
| 80 °C | 108.50 Hz |
| 100 °C | 111.53 Hz |
| 120 °C | 114.48 Hz |

This is a major finding.

A fixed-frequency controller operating at 100 Hz cannot assume the acoustic optimum remains exactly 100 Hz while the thermal state changes.

Therefore THERMA requires either:

- frequency tracking,
- impedance adaptation,
- a geometry designed for the expected temperature distribution,
- or a sufficiently broad acceptable operating band.

## 6. Helium density at baseline

At 1 MPa and 300 K:

rho = p/(R T)

rho ≈ 1.605 kg/m³.

The acoustic speed is approximately:

c ≈ 1019.2 m/s.

These are ideal-gas screening values.

Real-gas effects should be checked before using elevated-pressure hardware values for final design.

## 7. Thermal penetration depth

For a simple oscillatory thermal penetration estimate:

delta_k = sqrt(2 k/(rho cp omega))

Using approximate helium properties near 300 K gives:

delta_k ≈ 0.240 mm at 100 Hz.

This immediately constrains the regenerator and heat-exchanger surface geometry.

A 0.50 mm hydraulic gap is roughly about 2.08 times the estimated thermal penetration depth.

That does not establish optimum performance.

It only demonstrates that geometry is operating in the same scale as the oscillatory thermal boundary layer.

## 8. Frequency sweep for thermal penetration

| Frequency | Approx. thermal penetration depth |
|---:|---:|
| 75 Hz | 0.277 mm |
| 100 Hz | 0.240 mm |
| 125 Hz | 0.215 mm |

Increasing frequency reduces the thermal penetration depth.

This may allow smaller thermal features, but it also changes viscous losses, acoustic impedance, pressure drop and thermal phase behavior.

Therefore frequency cannot be optimized using one metric alone.

## 9. Acoustic pressure screen

At 1 MPa mean pressure and a 5% drive ratio:

p_amp = 50 kPa.

For a simple sinusoid:

p_rms ≈ 35.4 kPa.

A progressive-wave estimate gives an RMS gas velocity scale of approximately:

u_rms ≈ 21.6 m/s.

This is not a direct THERMA prediction because a real thermoacoustic network can contain standing-wave regions, phase differences and reactive acoustic energy.

## 10. Cross-sectional area

For a 50 mm internal diameter:

A ≈ 0.001963 m².

A purely progressive-wave intensity estimate is:

I = p_rms u_rms.

This gives approximately:

I ≈ 764.2 kW/m².

The corresponding idealized acoustic power crossing that area is:

P_ac,ideal ≈ 1.50 kW.

This is a **wave-power scale**, not expected delivered cooling power.

## 11. Why the 1.5 kW number is not a cooling prediction

The calculation above assumes a progressive wave and nearly optimal phase.

Real THERMA operation requires:

- nonzero acoustic power transmission,
- correct phase between pressure and velocity,
- regenerator conversion,
- heat-exchanger coupling,
- acceptable streaming,
- pressure-loss control,
- structural losses,
- and rejection of parasitic heat.

Therefore:

**1.50 kW acoustic wave power scale ≠ 1.50 kW cooling.**

## 12. Thermodynamic source/sink ceiling

For a heat-driven refrigeration cascade, a useful ideal upper-bound screening expression is:

COP_ideal = [Tc/(Th-Tc)] × [(Ts-Th)/Ts]

where:

- Ts is absolute driving-source temperature,
- Th is absolute heat-sink temperature,
- Tc is absolute cold-side temperature.

For 3 °C cold and 35 °C sink:

| Source | Ideal heat-driven COP ceiling |
|---:|---:|
| 60 °C | 0.648 |
| 80 °C | 1.100 |
| 100 °C | 1.503 |
| 120 °C | 1.866 |
| 150 °C | 2.345 |
| 200 °C | 3.009 |

These are reversible upper bounds.

They are not THERMA predictions.

## 13. Realistic screening efficiency envelope

To understand sensitivity, three deliberately broad system-efficiency products were tested:

Case A:
engine conversion 25%
acoustic transfer 60%
refrigeration conversion 40%

Combined factor = 6%.

Case B:
engine conversion 40%
acoustic transfer 60%
refrigeration conversion 50%

Combined factor = 12%.

Case C:
engine conversion 50%
acoustic transfer 70%
refrigeration conversion 60%

Combined factor = 21%.

These are **scenario multipliers**, not measured THERMA efficiencies.

At a 100 °C source and 35 °C sink, the ideal ceiling is 1.503.

Multiplying by the above illustrative factors yields:

- Case A ≈ 0.090
- Case B ≈ 0.180
- Case C ≈ 0.316

This is the correct way to use such numbers: as sensitivity scenarios, not claims.

## 14. Critical conclusion from the COP screen

A THERMA system can look thermodynamically attractive while still having poor real COP.

The gap between:

**ideal ceiling**

and

**prototype COP**

is created by:

- regenerator loss,
- acoustic mismatch,
- viscous loss,
- thermal short circuit,
- heat-exchanger approach temperature,
- streaming,
- structural loss,
- source-transfer loss,
- sink-transfer loss,
- control and auxiliary power.

Therefore the engineering goal is not to maximize the ideal COP.

The engineering goal is to minimize the gap between the ideal ceiling and hardware.

## 15. Source/sink stress matrix

The candidate was evaluated conceptually across source and sink temperatures.

The first red flag is that a high sink temperature can destroy the available thermal head even when the source is unchanged.

At a fixed 60 °C source:

- 35 °C sink leaves useful head.
- 50 °C sink leaves only a small temperature margin.
- 55 °C sink leaves almost no driving head.

Therefore a system designed for a 35 °C rejection environment cannot be assumed to work identically at 50–55 °C.

## 16. Heat-sink saturation test

If the heat sink rises toward the hot-source temperature:

Ts → Th

then:

(Ts - Th) → 0

and the ideal heat-driven refrigeration COP tends toward zero.

This is a fundamental limit.

Therefore heat rejection is not a secondary subsystem.

It is part of the core thermodynamic architecture.

## 17. Cold-side approach temperature

A nominal 3 °C load does not imply that the thermoacoustic cold exchanger operates exactly at 3 °C.

There must be an exchanger approach temperature.

Example screening:

Load = 3 °C

Cold-side HX thermal node = 0 °C

Approach = 3 K

That creates an additional burden on the refrigeration core.

The actual prototype must solve the complete thermal resistance chain.

## 18. Hot-side approach

Likewise, a 100 °C source stream does not mean the hot regenerator node is exactly 100 °C.

If the hot HX has a 10 K approach:

Source = 100 °C

Internal hot node ≈ 90 °C

That can significantly reduce the useful gradient.

Therefore the correct simulation input is not simply source temperature.

It is the complete thermal-node temperature distribution.

## 19. Regenerator stress

Baseline:

length = 100 mm

hydraulic feature/gap = 0.50 mm

thermal penetration depth ≈ 0.24 mm

The geometric ratio is:

gap / delta_k ≈ 2.08.

This is only a screening ratio.

A proper regenerator calculation must include:

- solid heat capacity,
- gas heat capacity,
- porosity,
- hydraulic radius,
- thermal conductivity,
- wall heat transfer,
- acoustic pressure,
- phase,
- pressure drop,
- axial conduction.

## 20. Regenerator failure mode — thermal short circuit

If the matrix is too conductive:

hot and cold ends can exchange heat through the solid.

That directly reduces the useful thermal gradient.

A regenerator can therefore become “better” at ordinary conduction while becoming worse as a thermoacoustic regenerator.

This is a key optimization conflict.

## 21. Regenerator failure mode — excessive resistance

If pores are too small:

pressure drop rises.

Acoustic power is consumed by viscous losses.

This can reduce the useful acoustic output even if the thermal contact area improves.

Therefore:

**more surface area ≠ automatically better.**

## 22. Heat-exchanger stress

Baseline hot/cold HX length = 120 mm.

The simulation does not claim a final UA.

Instead it asks:

Can 120 mm provide sufficient thermal transfer area without excessive acoustic pressure loss?

This requires experimental or high-fidelity geometry-specific validation.

## 23. Oscillatory-flow HX risk

Steady-flow heat-transfer correlations can be misleading in oscillatory thermoacoustic flow.

The relevant behavior depends on:

- oscillation amplitude,
- frequency,
- displacement amplitude,
- thermal penetration,
- phase,
- geometry,
- hydraulic diameter,
- porosity,
- wall conductivity.

Therefore the HX is one of the first components that must eventually be checked against physical measurements.

## 24. Pressure-cycle stress

At 100 Hz:

cycles/year = 100 × 31,557,600

= 3.156 billion cycles/year.

This is the fixed-hardware fatigue problem.

“No moving parts” does not mean:

“No cyclic stress.”

It means the stress comes from pressure and thermal oscillation rather than a crank mechanism.

## 25. Pressure-vessel preliminary stress screen

For an illustrative cylindrical shell:

mean pressure = 1 MPa

radius = 25 mm

wall thickness = 5 mm

thin-wall hoop stress:

sigma ≈ p r/t

≈ 5 MPa.

This is only an illustrative mechanical screen.

It ignores:

- weld factors,
- ports,
- stress concentration,
- thermal stress,
- cyclic stress,
- manufacturing tolerance,
- external loads,
- code requirements,
- temperature-dependent properties.

No fabrication decision should be made from this calculation.

## 26. Pressure amplitude stress

At 5% drive ratio:

pressure amplitude ≈ 50 kPa.

The dynamic stress amplitude in the real shell is not simply equal to the acoustic pressure because geometry, nodes/antinodes, ports, and structural coupling matter.

Therefore pressure instrumentation is mandatory in prototype testing.

## 27. Frequency-temperature mismatch

The baseline 100 Hz resonance shifts upward as gas temperature rises.

At 100 °C gas temperature:

first-order resonance ≈ 111.5 Hz.

This means a fixed 100 Hz drive may become detuned during operation.

This is a serious control-system requirement.

Potential solutions include:

1. frequency tracking,
2. variable-frequency drive,
3. adaptive impedance matching,
4. geometry designed around a thermal-state distribution.

## 28. Frequency sweep

A screening sweep from 75–125 Hz shows:

- lower frequency → larger thermal penetration depth,
- higher frequency → smaller thermal penetration depth,
- resonance geometry moves with temperature,
- acoustic losses and heat transfer change simultaneously.

Therefore the “best frequency” cannot be selected from thermal penetration alone.

## 29. Pressure sweep

Mean pressure increases acoustic power density roughly by increasing gas density, but it also increases:

- pressure-vessel load,
- leak consequence,
- seal requirements,
- stored energy,
- inspection requirements.

Therefore the optimization variable is:

**useful thermal output / pressure-boundary burden**

not raw pressure.

## 30. Drive-ratio sweep

Increasing drive ratio can increase acoustic power strongly at first.

But near nonlinear limits:

- waveform distortion increases,
- streaming can increase,
- losses can increase,
- stability can deteriorate,
- structural stress can rise.

Therefore a high-drive point is not automatically the optimum point.

## 31. Source-temperature sweep

The simulation confirms that increasing source temperature generally increases thermodynamic opportunity.

But above the chosen material and HX envelope:

- thermal gradients increase,
- material stress increases,
- heat-rejection demand increases,
- safety complexity increases.

So the best prototype is not necessarily the highest-temperature prototype.

## 32. Low-grade source failure test

At 60 °C source and 35 °C sink:

ideal heat-driven COP ceiling ≈ 0.648.

After realistic component losses, useful COP can become small.

This is why 60 °C operation remains a difficult research target rather than the first prototype target.

## 33. 80 °C source test

At 80 °C source and 35 °C sink:

ideal ceiling ≈ 1.100.

This gives more thermodynamic headroom than 60 °C.

It is therefore a more credible development region.

It still does not prove that the THERMA geometry can reach a useful COP.

## 34. 100 °C source baseline

At 100 °C source and 35 °C sink:

ideal ceiling ≈ 1.503.

This is the chosen baseline because it provides a stronger temperature head without immediately pushing the prototype toward extreme-temperature materials.

## 35. Rapid-cooling load test

Sensible load for water-equivalent product:

Q = m cp ΔT

For 25 → 3 °C:

ΔT = 22 K.

For 1 kg:

Q ≈ 25.6 Wh.

For 1,000 kg:

Q ≈ 25.6 kWh.

At 15 minutes:

P_cool ≈ 102 kW.

This is before losses.

Therefore a 1,000 kg / 15 min claim requires a fundamentally different module scale than a small proof-of-physics core.

## 36. 30 kg rapid test

30 kg:

Q ≈ 0.767 kWh.

15-minute average:

P ≈ 3.07 kW.

This is a much more plausible laboratory transient benchmark for a multi-kW prototype campaign.

## 37. 100 kg rapid test

100 kg:

Q ≈ 2.56 kWh.

15-minute average:

P ≈ 10.23 kW.

This requires substantial cooling capacity.

The model should therefore separate:

- prototype cooling capacity,
- storage-assisted cooling,
- multi-module rapid cooling.

## 38. 500 kg rapid test

500 kg:

Q ≈ 12.79 kWh.

15-minute average:

P ≈ 51.2 kW.

This is no longer a small single-core demonstration.

It requires validated module power density and parallel thermal integration.

## 39. Heat-pump reverse mode

For 1 L water:

20 → 80 °C

Q_H ≈ 69.8 Wh.

The physical system must draw:

Q_C = Q_H - W.

The amount depends on actual COP.

The historical 1.6 L/L result remains a model result tied to a specific COP and source-temperature assumption.

It is not universal.

## 40. Reversible transition stress

The transition sequence is:

cooling

→ ramp down acoustic drive

→ neutral state

→ isolate/bypass

→ verify pressure and temperatures

→ retune frequency/impedance

→ ramp up

→ heating.

The stress test asks whether thermal interfaces can switch roles without thermal shock or controller instability.

## 41. Sensor-failure test

Primary sensors:

- hot temperature,
- cold temperature,
- sink temperature,
- pressure,
- flow,
- acoustic pressure.

Fault injections:

- frozen reading,
- open circuit,
- offset,
- noise,
- delayed measurement,
- impossible value.

The safe response must move to a degraded or shutdown state.

## 42. Valve-failure test

A failed valve can cause:

- trapped pressure,
- flow starvation,
- uncontrolled bypass,
- excessive heat input,
- loss of cooling,
- unsafe mode transition.

The controller must not assume commanded valve position equals actual valve position.

Feedback confirmation is required.

## 43. Pump-failure test

External thermal pumps are not part of the acoustic core, but their failure can still damage the system.

Examples:

pump stops

→ flow collapses

→ HX temperature rises

→ thermal gradient shifts

→ acoustic operating point changes

→ shutdown/bypass required.

## 44. Heat-rejection saturation

If the heat sink cannot absorb rejected heat:

sink temperature rises.

Then:

Th rises.

Then the ideal heat-driven COP decreases.

Therefore heat-rejection capacity can become the direct cause of refrigeration failure.

## 45. Acoustic leakage test

Any leak or imperfect boundary can reduce:

- mean pressure,
- acoustic amplitude,
- stability,
- operating duration.

Helium leak testing is therefore a prototype-gate requirement.

## 46. Combined-fault test

Worst-case combined event:

high source temperature

+

low coolant flow

+

pressure sensor offset

+

heat-rejection saturation

+

frequency detuning.

The controller must move to safe shutdown rather than attempting to maintain nominal output.

## 47. Breakpoint search

A design is not considered robust merely because one point works.

The breakpoint search should determine:

- minimum source temperature,
- maximum sink temperature,
- maximum drive ratio,
- minimum flow,
- maximum pressure,
- maximum thermal gradient,
- maximum acceptable detuning,
- maximum allowable HX pressure drop.

## 48. Candidate operating window

For the screening baseline, a reasonable experimental search window is:

source: 80–120 °C

sink: 25–40 °C

frequency: 75–125 Hz

drive ratio: 1–5%

mean pressure: 0.5–2 MPa

This is a proposed test envelope, not a hardware rating.

## 49. What the simulation can establish

The reduced model can establish:

- thermodynamic ceilings,
- scaling relationships,
- resonance sensitivity,
- thermal-boundary scales,
- load power requirements,
- fatigue-cycle counts,
- sensitivity to source/sink conditions,
- subsystem interactions.

## 50. What the simulation cannot establish

It cannot establish:

- final acoustic power,
- final COP,
- final cooling capacity,
- structural fatigue life,
- exact HX effectiveness,
- helium leak rate,
- actual streaming losses,
- certification compliance,
- commercial cost.

## 51. Critical failure gate

The candidate fails as a prototype concept if:

1. the exact geometry cannot sustain stable acoustic operation;
2. acoustic power is too small for useful thermal output;
3. the regenerator loss overwhelms the acoustic power;
4. the HX cannot transfer enough heat;
5. the source/sink head is insufficient;
6. thermal or pressure cycling exceeds qualified limits;
7. mode switching becomes unsafe.

## 52. Critical survival gate

The candidate survives simulation only if:

- stable resonance exists,
- thermal gradient survives exchanger approaches,
- regenerator losses remain bounded,
- acoustic power remains positive,
- heat rejection remains possible,
- control can maintain a safe state,
- and prototype measurements can resolve the unknowns.

## 53. Most important result

The candidate geometry is **not yet proved**.

But it has produced a much stronger engineering map.

The model identifies the variables that must be measured.

That is progress.

## 54. Required exact-geometry next step

Before the next high-fidelity simulation, freeze:

- complete resonator path,
- each tube diameter,
- every junction,
- compliance volume,
- inertance geometry,
- regenerator cartridge dimensions,
- HX channel dimensions,
- mean pressure,
- working gas,
- operating frequency,
- source/sink boundary conditions.

## 55. Prototype instrumentation

Required development instrumentation:

- calibrated thermocouples/RTDs,
- absolute pressure transducers,
- differential acoustic pressure sensors,
- flow meters,
- frequency acquisition,
- phase measurement,
- heat-balance measurements,
- helium inventory/leak measurement,
- electrical power measurement where applicable,
- synchronized DAQ.

## 56. Model validation sequence

Validate in this order:

1. empty resonator/acoustic network,
2. resonator with working gas,
3. regenerator installed,
4. hot HX installed,
5. cold HX installed,
6. complete thermal loops,
7. controlled source gradient,
8. refrigeration mode,
9. heat-pump mode,
10. reversible transition.

This prevents a complete-system failure from hiding the subsystem cause.

## 57. Final status

The exact candidate geometry is **a screening baseline**.

It is more informative than a generic temperature sweep.

It is still not a fabrication design.

The model has narrowed the engineering uncertainty.

The remaining uncertainty is concentrated in exact acoustic geometry, regenerator loss, oscillatory heat transfer, pressure cycling, nonlinear losses and hardware measurement.

## 58. Engineering decision

**Do not freeze THERMA 3.5 for fabrication yet.**

Freeze the simulation geometry first.

Then run a reproducible exact-geometry thermoacoustic solver.

Only after that should mechanical CAD and pressure-vessel detailing proceed.

## 59. Result classification

| Result | Evidence |
|---|---|
| Thermodynamic limits | B — calculation |
| Resonator first-order length | B — calculation |
| Thermal penetration depth | B — calculation |
| Cycle-count estimate | B — calculation |
| Acoustic wave-power scale | B — simplified calculation |
| Component efficiency factors | C — assumed scenarios |
| Exact THERMA COP | D — hardware required |
| Exact acoustic power | D — exact model + hardware |
| Fatigue life | D — materials/testing required |
| HX effectiveness | D — geometry-specific validation |

## 60. Bottom line

This candidate **does not prove THERMA**.

It does something more useful:

It tells us exactly what must be solved before THERMA can be called prototype-ready.

The make-or-break chain remains:

exact geometry
→ acoustic field
→ regenerator
→ oscillatory HX
→ source/sink head
→ acoustic power density
→ fatigue
→ fault control
→ measurement.

This simulation therefore ends with a **prototype engineering gate**, not a simulated declaration of success.
