# THERMA 3.5 — Coupled System Model v4

## 0. Purpose

This run builds directly on `tests/006-exact-geometry-screening-results.md`.
The objective is to couple, at reduced order, the exact candidate resonator reference, working-gas state, regenerator scale, heat-exchanger reference lengths, temperature head, acoustic-power scale, loss factors, and fatigue/control implications.

This is a screening model, not DeltaEC, SAGE, CFD, FEA, or a certified pressure-vessel calculation. It is intended to determine whether the current candidate survives a more tightly coupled consistency test and to identify which missing exact-geometry inputs dominate the uncertainty.

## 1. Architecture lock

THERMA 3.5 is treated as a fixed-hardware thermoacoustic system with oscillating working gas.

The core contains:

- hot heat exchanger
- regenerator
- acoustic resonator/network
- cold heat exchanger
- working-gas pressure boundary
- inertance/compliance elements where used

The core does not contain:

- piston
- displacer
- crankshaft
- connecting rod
- flywheel
- reciprocating compressor
- mechanical-bearing power train

External pumps and valves may exist in secondary thermal loops.

## 2. Frozen baseline inherited from v6

Working gas: helium.
Mean pressure: 1.0 MPa.
Reference frequency: 100 Hz.
Reference resonator diameter: 50 mm.
Reference quarter-wave length: 2.842 m at 100 C, before end corrections and network effects.
Regenerator reference length: 100 mm.
Nominal regenerator gap: 0.50 mm.
Hot heat exchanger reference length: 120 mm.
Cold heat exchanger reference length: 120 mm.
Drive ratio: 5%.
Nominal source temperature: 100 C.
Nominal heat sink: 35 C.
Nominal cold target: 3 C.

These are candidate screening parameters, not a frozen fabrication specification.

## 3. Reference acoustic state

For helium with gamma about 1.667 and R about 2077 J/kg-K, the ideal-gas sound-speed estimate at 100 C is approximately 1137 m/s.

A first-order quarter-wave reference is therefore:

L = c/(4f)

L ≈ 1137/(4×100) ≈ 2.84 m.

This is a reference only. The final acoustic network can be shorter, longer or differently shaped when inertance, compliance, junctions, side branches and end corrections are included.

## 4. Frequency drift test

If the physical resonator length remains fixed at 2.842 m, the first-order resonance estimate changes with gas temperature.

At 20 C: approximately 88.6 Hz.
At 100 C: approximately 100.0 Hz.
At 130 C: approximately 103.9 Hz.
At 200 C: approximately 112.6 Hz.

Therefore a fixed geometry operated across a broad temperature envelope experiences approximately 11-13% frequency movement relative to the 100 C reference over the 20-200 C range.

Implication: a fixed-frequency driver is likely suboptimal across a large temperature range unless the final acoustic network is deliberately designed for broad bandwidth. Adaptive frequency control or a geometry with sufficient impedance bandwidth becomes a serious architecture requirement.

## 5. Gas-density and acoustic-power scale

At 1.0 MPa and 100 C, the ideal-gas estimate for helium density is approximately:

rho ≈ p/(RT) ≈ 1.29 kg/m^3.

For a 50 mm diameter section, area is approximately 0.001963 m^2.

With 5% drive ratio:

p_amp ≈ 0.05×1.0 MPa = 50 kPa.

A plane-wave order-of-magnitude acoustic power estimate is:

P_ac ≈ p_amp^2 A /(2 rho c)

which gives approximately 1.67 kW.

This result is a wave-power scale, not useful refrigeration capacity.

## 6. Coupled loss model

To expose sensitivity, this run uses a transparent multiplicative screening model rather than inventing a single exact efficiency.

Let:

eta_net = eta_impedance × eta_regenerator × eta_hotHX × eta_coldHX × eta_stream × eta_other.

The model does not claim these factors are measured THERMA values. They are scenario parameters used to see how quickly the 1.67 kW acoustic scale collapses when realistic loss channels are introduced.

Three illustrative scenarios were screened.

### Scenario A — optimistic screening

eta_impedance = 0.90
eta_regenerator = 0.90
eta_hotHX = 0.90
eta_coldHX = 0.90
eta_stream = 0.95
eta_other = 0.95

Combined eta_net ≈ 0.50.

Useful acoustic/thermal transfer scale from the idealized 1.67 kW is therefore about 0.84 kW.

### Scenario B — middle screening

eta_impedance = 0.80
eta_regenerator = 0.85
eta_hotHX = 0.80
eta_coldHX = 0.80
eta_stream = 0.90
eta_other = 0.90

Combined eta_net ≈ 0.40.

Transferred scale ≈ 0.67 kW.

### Scenario C — harsh screening

eta_impedance = 0.65
eta_regenerator = 0.70
eta_hotHX = 0.65
eta_coldHX = 0.65
eta_stream = 0.80
eta_other = 0.80

Combined eta_net ≈ 0.14.

Transferred scale ≈ 0.24 kW.

These ranges do not establish actual THERMA efficiency. They demonstrate that a seemingly kilowatt-scale ideal acoustic wave can turn into a few-hundred-watt useful-transfer scale under plausible aggregate losses.

## 7. Temperature-head coupling

The ideal heat-driven refrigeration ceiling for a 3 C cold target and 35 C sink is strongly dependent on the source temperature.

60 C source: approximately 0.648.
80 C source: approximately 1.100.
100 C source: approximately 1.503.
120 C source: approximately 1.866.
150 C source: approximately 2.345.
200 C source: approximately 3.009.

These are reversible thermodynamic ceilings and not THERMA predictions.

Real THERMA performance would be lower because the effective thermal nodes are not identical to the source and sink bulk temperatures. Heat-exchanger approach temperatures reduce the useful span, while acoustic, regenerator and streaming losses reduce conversion efficiency.

## 8. Effective-node example

To test sensitivity, suppose a 100 C source is delivered to a hot-side thermal node at only 90 C after source-side approach loss, while the 35 C environment is represented by a 40 C hot-side rejection node.

The available temperature head then becomes materially smaller than the raw 100 C to 35 C difference.

This illustrates why THERMA should optimize the heat exchangers as part of the acoustic system rather than treat their temperatures as ideal boundary conditions.

## 9. Regenerator scale coupling

The previously screened thermal and viscous penetration depths at 100 Hz were on the order of a few tenths of a millimetre.

With a nominal 0.50 mm channel/gap, the gap is only approximately two times the thermal penetration scale in the prior screening model.

Therefore:

- frequency changes alter penetration depth
- gas choice alters penetration depth
- pressure can change density and related losses
- wall thermal properties alter phase behavior
- gap changes alter viscous loss and thermal contact
- porosity changes pressure drop and heat-transfer area

The regenerator cannot be tuned independently of the acoustic frequency and gas state.

## 10. Regenerator sensitivity thought experiment

Assume the 0.50 mm gap is the baseline.

A 20% reduction to 0.40 mm increases interaction with the solid surfaces but also raises viscous resistance.

A 20% increase to 0.60 mm lowers viscous resistance but reduces solid-area coupling per gas volume.

The model therefore predicts a qualitative optimum rather than monotonic improvement in either direction.

Exact optimization requires a manufactured channel geometry and thermoacoustic solver.

## 11. Heat-exchanger coupling

The 120 mm hot and cold HX dimensions in this candidate are only reference lengths.

Useful heat transfer depends on:

- oscillatory Reynolds number
- hydraulic diameter
- channel spacing
- oscillation amplitude
- thermal boundary-layer depth
- wall conductivity
- flow reversal frequency
- pressure amplitude
- temperature swing
- exchanger approach temperatures
- leakage/bypass paths

A long exchanger does not automatically mean high useful heat transfer because additional length can add hydraulic/acoustic resistance.

## 12. Acoustic junction penalty

The reference 2.84 m quarter-wave estimate assumes a simple tube.

The real THERMA core requires interfaces between:

resonator → regenerator → heat exchanger → impedance network → return path.

Each junction can create area change, reflection, phase shift, turbulence/streaming and local losses.

Therefore the exact junction geometry may be more important than the nominal total tube length.

## 13. Phase margin test

Thermoacoustic power transfer is sensitive to pressure/velocity phase.

A network that produces high pressure amplitude but poor phase at the regenerator may show a large acoustic signal while delivering poor net thermal performance.

The required exact simulation therefore needs:

- complex pressure amplitude
- complex particle velocity
- phase angle
- impedance at each interface
- acoustic power flow

Magnitude-only pressure results are insufficient.

## 14. Acoustic-power balance

The correct accounting chain is:

input thermal driving power
→ generated acoustic power
→ network-delivered acoustic power
→ refrigeration acoustic power
→ heat pumping
→ useful cold-side removal.

Each arrow requires its own loss term.

Therefore a claim such as "1.7 kW acoustic power" must never be reported as "1.7 kW cooling" without a validated conversion chain.

## 15. Rapid-cooling coupling

For 25 C → 3 C sensible cooling, the load energy is approximately 25.6 Wh/kg.

Required average power for a 15-minute pull-down is approximately:

30 kg → 3.07 kW.
100 kg → 10.23 kW.
500 kg → 51.2 kW.
1,000 kg → 102 kW.

This immediately shows that a single candidate core at a few-hundred-watt useful-transfer scale cannot perform a 1,000 kg 15-minute pull-down.

A credible rapid design therefore needs either:

- multiple validated cores
- a thermal buffer correctly sized for transient power
- a much higher-power core density
- a longer pull-down time
- or a smaller load.

## 16. Heating-mode coupling

For 1 L water from 20 C to 80 C, sensible heat is approximately 69.8 Wh.

The historical 1.6 L source-water/L product-water ratio came from a screening assumption of COP_H ≈ 2.1 and source cooling from 20 C to 0 C.

That ratio is conditional and must not be used as a THERMA universal property.

In the coupled model, any real heating performance must include:

- source HX approach
- hot HX approach
- acoustic losses
- regenerator losses
- auxiliary pump power
- heat leakage
- control overhead.

## 17. Reversible-mode transition

The neutral state is treated as mandatory.

Cooling mode:

source heat → acoustic generation → refrigeration → rejection.

Transition:

reduce acoustic amplitude → stabilize temperatures → isolate/bypass selected loop → verify pressure and flow → retune frequency/impedance → ramp into heating.

Heating mode:

source-side heat pickup + acoustic work → hot-water delivery.

A direct instantaneous swap is not considered a safe design target.

## 18. Fault-control stress

The reduced model flags the following as high priority:

- source-temperature overshoot
- heat-sink saturation
- loss of cold-side flow
- loss of hot-side flow
- sensor drift
- sensor disagreement
- pressure rise
- pressure decay/leak
- resonator detuning
- acoustic amplitude runaway
- actuator/valve failure
- controller restart during thermal instability.

The software state machine should therefore have independent hardware protection.

## 19. Extreme 1500 C input

A raw 1500 C industrial liquid is outside the candidate interface.

Required architecture:

1500 C source
→ high-temperature rated recovery/diverter
→ controlled secondary thermal loop
→ THERMA source HX
→ core.

Direct exposure is treated as a protective shutdown/diversion condition, not a high-performance operating point.

## 20. Fatigue coupling

At 100 Hz the hardware sees approximately:

3.15×10^9 cycles/year.

This does not itself prove fatigue failure. It proves that cyclic pressure and thermal loading must be explicitly qualified.

Critical locations include:

- pressure shell welds
- nozzles
- HX attachments
- acoustic junctions
- thin-wall sections
- support points
- thermal-expansion interfaces.

## 21. Sensitivity ranking

The reduced-order evidence suggests the following priority ranking for exact simulation:

1. source/sink temperature head
2. acoustic phase and impedance
3. regenerator gap and geometry
4. heat-exchanger effectiveness/approach
5. acoustic pressure amplitude
6. aggregate network losses
7. working-gas state
8. frequency tracking
9. fatigue envelope
10. controller response.

This ranking is preliminary and should be updated when exact geometry is solved.

## 22. What this run proves

This run proves only that a coupled reduced-order model can expose interactions that are hidden by isolated calculations.

It does not prove:

- exact onset
- exact acoustic power
- exact cooling power
- exact COP
- exact heat-exchanger effectiveness
- pressure-vessel life
- prototype readiness.

## 23. What this run breaks

The following claims should remain rejected:

- universal 60 C THERMA operation
- direct conversion of ideal acoustic power into cooling power
- 15-minute cooling of arbitrary large loads
- unlimited proportional performance from more heat
- 10 MW scaling by simple multiplication
- fatigue immunity because there are no mechanical moving parts
- direct exposure to arbitrary industrial temperatures.

## 24. What survives

The architecture remains a physically credible thermoacoustic research direction.

The main unknown is no longer whether the equations permit the concept in principle.

The main unknown is whether one exact manufactured geometry can produce enough stable acoustic power and thermal transfer at useful efficiency and acceptable stress.

## 25. Required next model fidelity

The next high-fidelity simulation must use:

- exact resonator length and diameter map
- every junction area
- every branch volume
- inertance geometry
- compliance volume
- exact regenerator pore/gap geometry
- hot HX channel geometry
- cold HX channel geometry
- working-gas properties at local temperatures
- source-side thermal resistance
- sink-side thermal resistance
- material thermal properties
- frequency sweep around the natural mode
- complex pressure/velocity solution
- thermal output and loss terms.

## 26. Prototype correlation requirements

Once a physical article exists, the exact same parameter set must be used in the model and hardware comparison.

Minimum measured channels:

- mean pressure
- pressure amplitude
- frequency
- phase
- hot-side temperature
- cold-side temperature
- source flow
- rejection flow
- useful Q_H or Q_C
- auxiliary electrical power
- helium inventory
- leak rate
- uncertainty.

## 27. Engineering decision

The current candidate should not be fabrication-frozen from this run alone.

It should move to an exact-geometry acoustic/thermal solver stage.

If the exact solver finds no stable operating point with acceptable acoustic power and heat transfer, redesign is mandatory before prototype manufacture.

If the solver finds a stable point, the result should still remain a prototype hypothesis until measured.

## 28. Final verdict

V4 does not produce a false green light.

It narrows the engineering problem to a tractable coupled model and identifies the most sensitive parameters.

The candidate survives first-principles screening, but the exact-geometry coupled solver remains the gate between a conceptual design and a credible prototype candidate.

## Evidence classification

Level A: thermoacoustic principles, energy balances and published technology-class behavior.
Level B: equations and calculations shown in this screening file.
Level C: all THERMA-specific geometry, efficiency factors, loss factors and predicted outputs.
Level D: none; no hardware measurements are contained here.

## Reproducibility note

The calculations in this file are intentionally transparent reduced-order calculations. They use the frozen candidate from test 006 and explicitly expose any added efficiency factors as assumptions. They are not presented as a replacement for an exact-geometry solver.
