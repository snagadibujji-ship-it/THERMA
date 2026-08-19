# THERMA 3.5 — Coupled Critical-Path Screening Simulation

## Status

This document records a **reduced-order engineering screening campaign** focused on the eight make-or-break variables identified after adversarial testing:

1. exact acoustic geometry
2. regenerator behavior
3. oscillatory heat exchangers
4. source/sink temperature head
5. acoustic power density
6. pressure/thermal fatigue
7. control under faults
8. prototype measurement

This is **not** a validated DeltaEC/SAGE/CFD model and it is not a substitute for an exact-geometry thermoacoustic solver. The purpose is to determine which combinations are thermodynamically impossible, structurally suspect, economically implausible, or worth taking to prototype.

## Architecture lock

THERMA 3.5 is treated as a fixed-hardware thermoacoustic system with oscillating working gas. No piston, displacer, crankshaft, connecting rod, flywheel or reciprocating mechanical compressor is included in the core.

Secondary-loop pumps and valves are allowed because they move external thermal fluid and are outside the thermoacoustic power-conversion core.

---

## 1. Screening model hierarchy

The model is deliberately layered.

### Layer A — thermodynamic ceiling

For a heat-driven cascade, a conservative upper-bound screen can be formed by combining a reversible heat engine and reversible refrigerator:

\[ 
COP_{HD,max} = \left(1-\frac{T_S}{T_H}\right)\frac{T_C}{T_S-T_C}
\]

where:

- \(T_H\) = source temperature
- \(T_S\) = heat-sink temperature
- \(T_C\) = cold-side temperature

This is an **ideal ceiling only**. It is not a prediction of THERMA.

### Layer B — system-efficiency envelope

A second stress screen assumes that the real machine achieves 10%, 20%, 30% or 50% of the ideal cascade ceiling. These percentages are not measured efficiencies; they are sensitivity multipliers showing how quickly a promising thermodynamic ceiling becomes commercially weak once losses are introduced.

### Layer C — load power

For water-equivalent product:

\[
Q = m c_p \Delta T
\]

For 25 °C → 3 °C:

- \(c_p = 4.186\,kJ/(kg\cdot K)\)
- \(\Delta T = 22\,K\)

The 15-minute average cooling power is:

\[
P_c = \frac{m c_p \Delta T}{900}
\]

### Layer D — acoustic geometry sanity checks

For a quarter-wave helium resonator, the first-order length estimate is:

\[
L \approx \frac{c}{4f}
\]

This is only a first screening relation. End corrections, compliance, inertance, distributed losses, temperature gradients and coupled resonator sections must be solved in the final model.

### Layer E — acoustic cycling

Even without mechanical moving parts, an acoustic core can experience billions of pressure cycles per year. The cycle rate is:

\[
N_{year}=f\times 365\times24\times3600
\]

This converts the "no moving parts" claim into the correct engineering question: **what fixed components experience cyclic stress and thermal fatigue?**

---

# 2. Source/sink temperature stress matrix

Target cold-side temperature: **3 °C**.

First stress matrix uses a heat sink of 35 °C.

| Source | Ideal engine efficiency term | Ideal heat-driven COP ceiling |
|---:|---:|---:|
| 60 °C | 0.075 | 0.648 |
| 70 °C | 0.102 | 0.880 |
| 80 °C | 0.127 | 1.100 |
| 90 °C | 0.152 | 1.307 |
| 100 °C | 0.174 | 1.503 |
| 110 °C | 0.196 | 1.689 |
| 120 °C | 0.216 | 1.866 |
| 130 °C | 0.236 | 2.034 |
| 140 °C | 0.254 | 2.193 |
| 150 °C | 0.272 | 2.345 |
| 160 °C | 0.289 | 2.490 |
| 170 °C | 0.305 | 2.629 |
| 180 °C | 0.320 | 2.761 |
| 190 °C | 0.335 | 2.888 |
| 200 °C | 0.349 | 3.009 |

### Interpretation

The 60–80 °C region is not automatically impossible, but the available reversible ceiling is small compared with high-temperature operation. The same source temperature becomes substantially worse when the heat sink is hotter.

### Sink-temperature sensitivity

For selected source temperatures:

| Source | Sink 25 °C | Sink 35 °C | Sink 45 °C | Sink 55 °C |
|---:|---:|---:|---:|---:|
| 60 °C | 1.319 | 0.648 | 0.296 | 0.080 |
| 80 °C | 1.955 | 1.100 | 0.652 | 0.376 |
| 100 °C | 2.523 | 1.503 | 0.969 | 0.640 |
| 120 °C | 3.033 | 1.866 | 1.254 | 0.878 |
| 150 °C | 3.708 | 2.345 | 1.632 | 1.192 |
| 200 °C | 4.643 | 3.009 | 2.154 | 1.627 |

### Break condition

The heat-driven ceiling collapses as the source approaches the sink. Therefore **source temperature alone is not the right operating variable**. The correct variable is the usable temperature head after all heat-exchanger approach temperatures and thermal losses.

---

# 3. Realistic-efficiency stress envelope

The following is not a forecast. It is an intentionally pessimistic scaling screen.

| Source | Ideal ceiling | 10% of ceiling | 20% | 30% | 50% |
|---:|---:|---:|---:|---:|---:|
| 60 °C | 0.648 | 0.065 | 0.130 | 0.194 | 0.324 |
| 70 °C | 0.880 | 0.088 | 0.176 | 0.264 | 0.440 |
| 80 °C | 1.100 | 0.110 | 0.220 | 0.330 | 0.550 |
| 100 °C | 1.503 | 0.150 | 0.301 | 0.451 | 0.752 |
| 120 °C | 1.866 | 0.187 | 0.373 | 0.560 | 0.933 |
| 150 °C | 2.345 | 0.235 | 0.469 | 0.704 | 1.173 |
| 200 °C | 3.009 | 0.301 | 0.602 | 0.903 | 1.505 |

### Interpretation

At 80 °C source and 35 °C sink, a machine operating at 30% of the reversible cascade ceiling would be around COP 0.33 on this screening definition. That is near the scale of published experimental heat-driven thermoacoustic cooling results and illustrates why **heat-exchanger and acoustic losses are decisive**.

The published 2026 heat-driven refrigerator/heat pump reported 2.75 kW cooling at COPc 0.34 for 300 °C heating, 35 °C ambient and 7 °C cooling, and 7.31 kW heating at COPh 1.28 for a 300 °C heating condition, 50 °C heat-pumping side and 10 °C ambient. Those values are external benchmarks, not THERMA predictions.

---

# 4. Rapid-cooling load stress

For 25 °C → 3 °C water-equivalent product:

| Load | Sensible energy | 15-min average cooling power |
|---:|---:|---:|
| 30 kg | 0.767 kWh | 3.07 kW |
| 100 kg | 2.558 kWh | 10.23 kW |
| 500 kg | 12.791 kWh | 51.16 kW |
| 1,000 kg | 25.581 kWh | 102.32 kW |

At an illustrative cooling COP of 0.34, the thermal drive requirement just for the sensible load would be:

| Load | Cooling energy | Thermal input at COP 0.34 |
|---:|---:|---:|
| 30 kg | 0.767 kWh | 2.26 kWh |
| 100 kg | 2.558 kWh | 7.52 kWh |
| 500 kg | 12.791 kWh | 37.62 kWh |
| 1,000 kg | 25.581 kWh | 75.24 kWh |

These are **minimum sensible-load values**, excluding room heat leak, infiltration, fans, product packaging, thermal bridges, heat exchanger approach losses and control power.

### Break condition

A 1,000 kg, 15-minute pull-down is not a small-machine problem. It is a roughly **100 kW-class cooling-power requirement** before parasitic loads.

Therefore any claim of universal 15-minute cooling must be rejected unless the proposed module array can demonstrate the required cooling power.

---

# 5. Acoustic resonator length sanity check

Using an approximate helium sound speed of 1007 m/s for a first-order sanity check:

| Frequency | Quarter-wave length | Half-wave length |
|---:|---:|---:|
| 40 Hz | 6.29 m | 12.59 m |
| 50 Hz | 5.04 m | 10.07 m |
| 60 Hz | 4.20 m | 8.39 m |
| 75 Hz | 3.36 m | 6.71 m |
| 80 Hz | 3.15 m | 6.29 m |
| 100 Hz | 2.52 m | 5.04 m |

### Critical observation

A compact THERMA package cannot assume that a low-frequency quarter-wave resonator will physically fit without folding, coiling, inertance/compliance substitutions or another architecture. Those changes alter losses and impedance and therefore must be included in the exact-geometry model.

This is one of the strongest reasons the visual dimensions generated earlier cannot be treated as final fabrication geometry.

---

# 6. Thermal penetration depth screening

Using a rough helium thermal diffusivity of 1.8×10^-4 m²/s for a first-order sensitivity estimate:

\[
\delta_k=\sqrt{\frac{2\alpha}{\omega}}
\]

| Frequency | Estimated thermal penetration depth |
|---:|---:|
| 40 Hz | 1.20 mm |
| 60 Hz | 0.98 mm |
| 80 Hz | 0.85 mm |
| 100 Hz | 0.76 mm |
| 150 Hz | 0.62 mm |

### Implication

Regenerator or stack channel dimensions need to be related to the thermal and viscous penetration depths. A matrix that is too coarse may not exchange enough heat; a matrix that is too fine can impose large viscous/acoustic losses.

This screen is not a regenerator design. It only establishes that **frequency, gas properties and pore/channel scale are tightly coupled**.

---

# 7. Pressure-amplitude stress

If mean pressure is 8 MPa, a drive ratio of:

| Drive ratio | Pressure amplitude |
|---:|---:|
| 0.5% | 40 kPa |
| 1.0% | 80 kPa |
| 2.0% | 160 kPa |
| 3.0% | 240 kPa |
| 5.0% | 400 kPa |

These amplitudes are not automatically damaging, but they show why the phrase **"no moving parts" does not mean "no cyclic stress"**.

Published thermoacoustic studies commonly operate under substantial mean pressures and pressure amplitudes; one 2025 validated study found strong sensitivity to drive ratio and mean pressure. The exact THERMA pressure must come from the final acoustic model and pressure-boundary design.

---

# 8. Cyclic-life stress

At fixed acoustic frequency:

| Frequency | Pressure cycles/year |
|---:|---:|
| 50 Hz | 1.58 billion |
| 75 Hz | 2.37 billion |
| 100 Hz | 3.15 billion |
| 150 Hz | 4.73 billion |

### Consequence

Fatigue must be considered for:

- pressure vessel walls
- welds
- ports/nozzles
- heat-exchanger interfaces
- regenerator supports
- seals
- brazed joints
- acoustic tubing
- structural mounts

The final fatigue analysis must be based on the actual stress amplitude and material S-N data at temperature. The present screen only proves that the cycle count is large enough to make fatigue a first-class design constraint.

---

# 9. Illustrative thin-cylinder stress screen

For a thin cylindrical pressure wall:

\[
\sigma_h\approx\frac{Pr}{t}
\]

An illustrative geometry of radius 50 mm and wall thickness 5 mm gives:

| Mean pressure | Illustrative hoop stress |
|---:|---:|
| 5 MPa | 50 MPa |
| 8 MPa | 80 MPa |
| 10 MPa | 100 MPa |

This is **not** a THERMA wall-thickness recommendation. It deliberately excludes stress concentrations, weld factors, thermal gradients, cyclic effects, corrosion allowance and code factors.

### Break condition

A pressure-vessel design cannot be frozen from an image. It needs code-based design, material data, weld procedure qualification, inspection, relief sizing and pressure/leak tests.

---

# 10. Heat-exchanger stress

The current literature makes the HX problem one of THERMA's highest-risk subsystems. A 2026 review reports no consensus on oscillatory heat-transfer design rules and recommends simultaneous consideration of length, porosity, fin spacing, separation gap and HX effectiveness rather than optimizing a single parameter in isolation.

The coupled variables are:

```text
frequency ─────┐
mean pressure ─┤
gas properties ├──► oscillatory flow field
geometry ──────┤                 │
flow amplitude ┘                 ▼
                     heat transfer + acoustic loss
                              │
                ┌─────────────┴─────────────┐
                ▼                           ▼
         useful Q transfer            pressure drop
                │                           │
                └────────────┬──────────────┘
                             ▼
                    system COP / power
```

### Required future model

The exact THERMA exchanger should be modeled with:

- oscillatory velocity amplitude
- thermal boundary layer thickness
- hydraulic radius
- fin/plate spacing
- porosity
- exchanger length
- fluid temperatures
- gas pressure
- frequency
- expected acoustic power loss
- external secondary-fluid flow

---

# 11. Regenerator stress

The regenerator must provide strong gas-solid thermal interaction while avoiding excessive pressure drop and acoustic power loss.

### Failure modes

1. thermal short-circuit through the solid matrix
2. insufficient thermal contact
3. excessive viscous loss
4. excessive pressure drop
5. poor heat capacity ratio
6. local temperature hot spots
7. thermal fatigue
8. manufacturing nonuniformity
9. blockage or fouling
10. degradation after cycling

### Coupling to frequency

The thermal penetration-depth screen shows that a change from 40 to 150 Hz changes the characteristic thermal penetration depth from roughly 1.20 mm to 0.62 mm in the rough helium estimate used here.

Therefore a regenerator optimized for one frequency cannot be assumed to remain optimal over a wide control-frequency range.

---

# 12. Source/sink transient stress

A source temperature that is adequate at steady state may fail during startup, source interruption or ambient spike.

Required transient cases:

- source rises rapidly
- source collapses
- sink rises rapidly
- cold load arrives warm
- heat sink fan/pump failure
- partial flow blockage
- valve misposition
- sensor bias
- control delay
- loss of acoustic amplitude

The model must enforce physical state boundaries rather than simply extrapolating steady-state COP.

---

# 13. Fault-injection matrix

| Fault | Expected response | Design requirement |
|---|---|---|
| high source T | bypass/reduce drive/shutdown | independent overtemperature layer |
| high pressure | isolate + relief | mechanical protection |
| low cold-loop flow | reduce output / stop | flow verification |
| heat-rejection failure | ramp down / safe stop | heat-sink monitoring |
| gas leak | isolate | pressure trend + leak test |
| sensor stuck high | plausibility check | redundant/diagnostic sensing |
| sensor stuck low | plausibility check | redundant/diagnostic sensing |
| valve stuck | transition to safe state | fail-safe hardware |
| controller failure | safe state | independent protection |
| power loss | passive-safe state | relief/isolation as required |

---

# 14. Reversible-mode stress

The machine must not switch cooling→heating while thermal gradients and pressure fields are changing uncontrollably.

Required transition logic:

```text
COOLING
  ↓
reduce acoustic amplitude
  ↓
verify pressure
  ↓
verify hot/cold temperatures
  ↓
neutral routing
  ↓
confirm stable state
  ↓
reconfigure thermal paths
  ↓
ramp acoustic condition
  ↓
HEATING
```

The same sequence is required in reverse.

### Break condition

If a transition requires a sudden thermal or acoustic discontinuity, the architecture is not ready for a real prototype.

---

# 15. Acoustic power-density stress

A key unknown is not merely whether acoustic motion exists, but whether enough acoustic power can be generated per unit core volume.

The prototype must measure:

- pressure amplitude
- frequency
- phase
- acoustic impedance
- acoustic power flow
- thermal input
- cold/heating output
- auxiliary power

The relationship must eventually close as:

\[
Q_{useful}=f(T_H,T_C,T_S,p_m,p_a,f,geometry,regenerator,HX,losses)
\]

Until that function is experimentally correlated, any THERMA kW/module claim is a hypothesis.

---

# 16. Published benchmark comparison

The following are external benchmarks only.

### 2026 heat-driven refrigerator/heat pump

Published experiment:

- heating condition: 300 °C
- heating-only output: 7.31 kW
- heating COP: 1.28
- cooling condition: 300 °C heating, 35 °C ambient, 7 °C cold
- cooling output: 2.75 kW
- cooling COP: 0.34

This is proof that the technology category can achieve useful kW-scale heat-driven cooling/heating under suitable conditions; it does not prove THERMA 3.5 performance.

### 2025 experimentally validated thermoacoustic refrigerator

Published study reports an experimentally validated computational method and strong sensitivity to drive ratio and pressure. It is a useful methodology benchmark for the THERMA exact-geometry model, but its geometry and operating point are not THERMA's.

### 2026 heat-exchanger review

Recent review literature emphasizes that oscillatory-flow heat exchanger design still lacks universal rules. This directly supports treating THERMA HX modeling as an experimental risk rather than a solved subsystem.

---

# 17. What the screening model can establish

### Established by first-principles screening

- 0–3 °C cooling has a nonzero but limited thermodynamic opportunity at low source temperatures.
- Sink temperature is a first-order driver.
- Rapid cooling requires large instantaneous cooling power.
- Low-frequency resonators can be physically long.
- acoustic operation generates huge fixed-structure cycle counts over long life.
- source temperature cannot be considered independently from sink temperature.

### Not established

- THERMA's exact resonator geometry
- THERMA's onset temperature
- THERMA's pressure amplitude
- THERMA's acoustic power density
- THERMA's regenerator effectiveness
- THERMA's HX effectiveness
- THERMA's actual COP
- THERMA's actual cooling/heating capacity
- THERMA's fatigue life
- THERMA's pressure-vessel safety
- THERMA's commercial cost

---

# 18. Critical-path ranking after simulation

## Rank 1 — exact geometry
Without an exact geometry, the rest of the coupled model has no stable foundation.

## Rank 2 — heat exchangers
HX loss and temperature approach can destroy available temperature head and acoustic power.

## Rank 3 — regenerator
Regenerator thermal effectiveness and acoustic loss must be co-optimized.

## Rank 4 — source/sink head
60–80 °C operation is highly environment-dependent.

## Rank 5 — acoustic power density
The machine must generate useful watts, not merely measurable oscillation.

## Rank 6 — fatigue
No mechanical moving parts does not eliminate pressure and thermal cycling.

## Rank 7 — fault control
The system must remain safe during sensor, flow, temperature and pressure faults.

## Rank 8 — prototype measurement
The final authority is hardware correlation.

---

# 19. Prototype gate implied by this simulation

A minimum credible prototype campaign should produce:

1. source temperature and flow
2. sink temperature and flow
3. cold-side temperature and flow
4. hot-side temperature and flow
5. mean pressure
6. pressure amplitude
7. frequency
8. phase
9. acoustic power
10. thermal input
11. useful cooling power
12. useful heating power
13. COP under an explicitly defined convention
14. heat-exchanger approach temperatures
15. regenerator temperature profile
16. leak rate
17. vibration/acoustic stability
18. fault response
19. mode-switch response
20. repeated-cycle drift

No commercial performance claim should be made before these measurements exist.

---

# 20. Final simulation verdict

The advanced screening campaign does **not** prove THERMA 3.5 works.

It does something more useful at the current stage: it narrows the experiment.

The surviving engineering hypothesis is:

> A fixed-hardware thermoacoustic platform may be viable when operated with a sufficiently favorable source/sink temperature head, a geometry-specific resonator/regenerator/HX design, adequate acoustic power density, qualified pressure/thermal cycling, safe fault controls and measured prototype correlation.

The stress campaign therefore changes the next task from broad concept exploration to:

**EXACT GEOMETRY → HIGH-FIDELITY THERMOACOUSTIC MODEL → HX/REGENERATOR OPTIMIZATION → PROTOTYPE → MEASURED CORRELATION**

Anything outside that chain should be treated as a secondary research branch until the core experiment is proven.

---

## External references used for the screening context

- Arefin, Ramadan, Bailliet (2026), *Heat exchangers for thermoacoustic systems: A review*, Applied Thermal Engineering, DOI 10.1016/j.applthermaleng.2025.129093. https://www.sciencedirect.com/science/article/abs/pii/S1359431125036853
- Jia et al. (2026), *A heat-driven thermoacoustic refrigerator/heat pump for solar-thermal application*, Applied Energy, DOI 10.1016/j.apenergy.2025.127334. https://www.sciencedirect.com/science/article/pii/S0306261925020641
- Al-Mufti et al. (2025), *Towards greener cooling: A comprehensive study on the experimental validation and parametric optimization of a thermoacoustic refrigerator*, Applied Thermal Engineering, DOI 10.1016/j.applthermaleng.2024.125302. https://www.sciencedirect.com/science/article/pii/S1359431124029703

## Evidence status

All numerical results in this file are either:

- first-principles screening calculations from explicitly stated assumptions, or
- external literature benchmarks clearly identified as external.

None are presented as measured THERMA 3.5 results.
