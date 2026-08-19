# THERMA 3.5 — Advanced Adversarial Stress Campaign

**Status:** architecture stress review / pre-prototype
**Purpose:** deliberately attack the current THERMA 3.5 concept until a failure mechanism, impossible operating region, hidden dependency, or weak assumption is found.

> This report is an engineering stress screen, not an exact-geometry DeltaEC/SAGE/CFD certification. The concept is still pre-prototype. The goal is to find weaknesses early rather than produce optimistic green tables.

## 1. Locked architecture under test

THERMA 3.5 is treated as a fixed-hardware thermoacoustic platform with oscillating working gas.

The acoustic core contains:

- hot heat exchanger;
- regenerator / structured thermal matrix;
- acoustic resonator;
- inertance/compliance/impedance elements as required by the exact topology;
- cold heat exchanger;
- sealed pressurized working-gas boundary;
- instrumentation and sensing interfaces.

The core does **not** contain:

- piston;
- displacer;
- crankshaft;
- connecting rod;
- flywheel;
- conventional reciprocating compressor;
- mechanical bearing power train.

External pumps and valves may move secondary thermal fluids. Their existence does not change the fixed-hardware requirement for the thermoacoustic core.

## 2. Test philosophy

The campaign attacks six classes of weakness:

1. thermodynamic headroom;
2. acoustic conversion and power density;
3. heat-exchanger and regenerator losses;
4. transient pull-down and load scaling;
5. thermal, pressure and fault extremes;
6. lifetime, control and economic edge cases.

Every result is labeled as one of:

- **A:** established external evidence;
- **B:** first-principles calculation;
- **C:** THERMA screening result/design hypothesis;
- **D:** hardware-only result requiring measurement.

## 3. Test 01 — three-temperature thermodynamic ceiling

For heat-driven refrigeration, a reversible three-temperature machine is bounded by the source temperature, heat-sink temperature and cold-load temperature.

For a source temperature `T_source`, sink `T_sink`, and cold target `T_cold`, the reversible heat-driven cooling COP ceiling used for this stress screen is:

`COP_Qh,max = T_cold * (T_source - T_sink) / [T_source * (T_sink - T_cold)]`

where all temperatures are absolute Kelvin and `T_source > T_sink > T_cold`.

Cold target: `3 °C`.

Sink case: `35 °C`.

Results:

| Source | Ideal heat-input COP ceiling |
|---:|---:|
| 60 °C | 0.648 |
| 70 °C | 0.880 |
| 80 °C | 1.100 |
| 100 °C | 1.503 |
| 120 °C | 1.866 |
| 150 °C | 2.345 |
| 200 °C | 3.009 |

### Finding

The 60–80 °C region has very little ideal headroom once a realistic hot ambient/sink is considered. This does not prove THERMA cannot operate there, but it makes low-grade operation a high-risk optimization problem.

### Severity

**HIGH** for 60–80 °C sources.

## 4. Test 02 — hot-climate sink stress

The same calculation was repeated with a sink at 25, 35, 45 and 55 °C.

| Source | Sink 25 °C | Sink 35 °C | Sink 45 °C | Sink 55 °C |
|---:|---:|---:|---:|---:|
| 60 °C | 1.319 | 0.648 | 0.296 | 0.080 |
| 70 °C | 1.646 | 0.880 | 0.479 | 0.232 |
| 80 °C | 1.955 | 1.100 | 0.652 | 0.376 |
| 100 °C | 2.523 | 1.503 | 0.969 | 0.640 |
| 120 °C | 3.033 | 1.866 | 1.254 | 0.878 |

### Finding

A source that looks attractive at a 25 °C sink can become marginal at a 45–55 °C sink. Therefore source temperature cannot be specified without the local heat-sink temperature.

### Break point

At 60 °C source and 55 °C sink, the ideal cooling COP ceiling is only about 0.08. Any real loss makes the useful region extremely difficult.

**Conclusion:** universal 60 °C operation is not credible as a blanket product promise.

## 5. Test 03 — rapid pull-down stress

For water-equivalent product, sensible heat from 25 °C to 3 °C is:

`Q = m * cp * ΔT`

Using `cp = 4.186 kJ/kg-K` and `ΔT = 22 K`:

| Product equivalent | Sensible energy | Average cooling power for 15 min |
|---:|---:|---:|
| 30 kg | 0.767 kWh | 3.07 kW |
| 100 kg | 2.563 kWh | 10.25 kW |
| 500 kg | 12.817 kWh | 51.27 kW |
| 1000 kg | 25.633 kWh | 102.53 kW |

These are load-only numbers. They exclude wall leakage, infiltration, fans, packaging, thermal bridges, exchanger approach temperature and control overhead.

### Finding

The 15-minute target becomes a capacity problem before it becomes a temperature problem.

For restaurant, cold-room or food-load applications, rapid THERMA must be specified by **load mass and thermal load**, not by a generic “minutes-to-3°C” statement.

## 6. Test 04 — maintenance-load versus pull-down stress

A system can be attractive at steady state while failing at startup.

Example maintenance case:

- room heat leak = 0.5 kW;
- target = 3 °C;
- thermal-input COP screen = 0.8.

Thermal input required at steady state:

`0.5 / 0.8 = 0.625 kW`

This is vastly smaller than the tens of kilowatts needed for a large warm-product pull-down.

### Finding

THERMA should be sized around **two separate ratings**:

1. steady-state maintenance capacity;
2. transient pull-down capacity.

Conflating them produces bad sizing.

## 7. Test 05 — source collapse during operation

Scenario:

`120 °C source -> 95 °C -> 80 °C -> 65 °C`

while sink remains at 35 °C.

The machine must not continue with the same operating point after the thermal head collapses.

### Required response

- detect source temperature fall;
- lower acoustic operating state;
- increase bypass/thermal conditioning if available;
- enter degraded state before onset is lost;
- avoid unstable high-drive operation near threshold;
- record the event for model correction.

### Weakness exposed

A controller that regulates only cold-side temperature can conceal a collapsing source gradient until the acoustic process becomes unstable.

**Control weakness: HIGH if source-gradient supervision is missing.**

## 8. Test 06 — ambient spike stress

Scenario:

Ambient rises from `35 °C` to `55 °C` while source heat stays fixed at `100 °C`.

The sink temperature rises while the source remains constant; thermodynamic headroom falls significantly.

### Required behavior

`normal -> degraded -> reduced cooling capacity or safe stop`

rather than forcing the original operating point.

### Design implication

The product needs a heat-sink/ambient feed-forward term, not only cold-room feedback.

## 9. Test 07 — source-temperature overshoot

Scenario:

Nominal secondary-loop source = `120 °C`.

Industrial upstream event creates `180 °C`, then `250 °C`.

### Expected behavior

- isolate source;
- open rated bypass/diverter;
- protect secondary loop;
- stop acoustic drive if required;
- keep pressure boundary within qualified temperature;
- log maximum exposure.

### Finding

The THERMA core must never be the first component asked to absorb an upstream temperature spike.

A **thermal conditioning stage must be a product-level requirement**, not an optional accessory.

## 10. Test 08 — raw 1500 °C accident

Scenario:

An industrial plant accidentally sends a 1500 °C hot liquid/stream toward THERMA.

### Direct-feed result

**FAIL.**

The correct response is not “more cooling.” The raw stream must not enter the core.

### Required architecture

`1500 °C source -> emergency isolation -> high-temperature recovery/diverter -> rated secondary heat-transfer loop -> THERMA`

### Finding

1500 °C is a protection test, not a performance mode.

## 11. Test 09 — pressure-amplitude stress

A 2025 experimental thermoacoustic engine study with transcritical CO2 reported a pressure ratio of about `1.071` at 175 °C, corresponding to substantial dynamic pressure amplitude and an experimentally measured acoustic output of 21 W in that particular apparatus. The result is an external benchmark, not a THERMA prediction.

Source: https://doi.org/10.1016/j.applthermaleng.2025.127951

### Finding

Acoustic pressure can be large enough that pressure-boundary fatigue and port/nozzle stress cannot be treated as secondary details.

## 12. Test 10 — billions-of-cycles fatigue screen

If the acoustic frequency is 50, 100 or 200 Hz, continuous one-year operation implies approximately:

| Frequency | Cycles/year |
|---:|---:|
| 50 Hz | 1.5768 × 10^9 |
| 100 Hz | 3.1536 × 10^9 |
| 200 Hz | 6.3072 × 10^9 |

### Finding

Even without moving mechanical hardware, **the pressure boundary and thermal matrix experience cyclic loading**. “No moving parts” does not mean “no fatigue.”

This is one of the most important reliability weaknesses.

## 13. Test 11 — heat-exchanger degradation stress

Assume exchanger effectiveness falls over time because of fouling, oxidation, geometry drift or thermal contact degradation.

A useful screening test is:

`effectiveness = 1.00, 0.95, 0.90, 0.80, 0.70`

The exact cooling-power penalty is geometry-dependent and cannot be asserted without a validated heat-transfer model.

### Finding

THERMA performance may be strongly exchanger-dominated, so performance degradation must be explicitly modeled and monitored rather than treated as a fixed nominal parameter.

Recent review evidence emphasizes that thermoacoustic heat exchangers require geometry-specific design and that a universal method is still lacking.

Source: https://doi.org/10.1016/j.applthermaleng.2025.129093

## 14. Test 12 — regenerator thermal short-circuit

If regenerator solid conductivity becomes too high or its thermal path becomes too direct, heat may bypass the desired acoustic cycle.

If conductivity becomes too low, the regenerator may not store/release sufficient heat each cycle.

### Finding

The regenerator has a non-monotonic design optimum.

“Higher conductivity = better” is false as a universal rule.

## 15. Test 13 — boundary-layer geometry stress

A 2025 experimental/numerical study found that thermal penetration, stack spacing, position and nonlinear behavior strongly affected predicted temperature span and cooling power, with reported impacts as large as roughly 80% and 73% for the investigated cases.

Source: https://doi.org/10.1016/j.ijheatmasstransfer.2024.126250

### Finding

Small geometric errors are not guaranteed to be small performance errors.

This is a **geometry sensitivity risk** and means CAD tolerances must eventually be connected to acoustic/thermal uncertainty.

## 16. Test 14 — drive-ratio stress

A 2025 experimentally validated standing-wave refrigerator study reported a validated computational model with less than 5% relative error for its specific apparatus. It found optimum performance at specific stack spacing, blockage ratio, stack length and helium conditions, while changing drive ratio altered the trade-off between temperature span, cooling power and COP.

Source: https://doi.org/10.1016/j.applthermaleng.2024.125302

### Finding

Drive ratio is not simply a “turn it up for more cooling” control.

High drive can improve normalized cooling power while reducing COP or increasing nonlinear losses.

## 17. Test 15 — mean-pressure tradeoff

External experimental work reports that increasing mean pressure can increase power density while also changing thermoacoustic performance and reducing certain performance measures in the tested standing-wave refrigerator.

### THERMA conclusion

Mean pressure must be optimized against:

- power density;
- pressure-vessel stress;
- leakage;
- gas inventory;
- acoustic losses;
- safety.

A one-dimensional objective such as maximum pressure is insufficient.

## 18. Test 16 — working-fluid substitution

Candidate fluids should not be selected only from thermal conductivity or “high sound speed.” The full choice depends on:

- density;
- sound speed;
- heat capacity;
- viscosity;
- thermal conductivity;
- boundary-layer behavior;
- pressure;
- compatibility;
- safety;
- leakage consequences.

A 2025 experimental study found helium favorable in its investigated standing-wave refrigerator, but that does not prove helium is universally optimal for THERMA geometry.

Source: https://doi.org/10.1016/j.applthermaleng.2024.125302

## 19. Test 17 — zero-auxiliary-power myth

External circulation pumps, controls, valves, sensors, fans and heat-rejection equipment require power.

Therefore:

`net electricity = controls + pumps + fans + instrumentation + thermal conditioning + other auxiliaries`

Even a heat-driven THERMA core is not necessarily an electricity-free system.

### Finding

Economic comparisons must include auxiliary electricity, not only thermal input.

## 20. Test 18 — heat-source availability stress

A waste-heat source may be intermittent.

Stress schedule:

- 8 h high source;
- 4 h medium source;
- 4 h low source;
- 8 h source unavailable.

### Questions exposed

- Can the cold load remain protected?
- Can thermal buffering bridge outages?
- Is hot-side storage economically justified?
- Does repeated startup create thermal fatigue?
- Does source cycling disturb acoustic onset?

### Weakness

Waste heat is not automatically a reliable energy supply.

## 21. Test 19 — rapid mode-switching stress

Cooling -> neutral -> heating -> neutral -> cooling.

Required checks:

- acoustic amplitude ramp;
- thermal-gradient reversal;
- pressure stability;
- valve sequencing;
- exchanger approach temperatures;
- cold-loop protection;
- hot-water overtemperature protection.

### Finding

The neutral state is not optional if the platform is to be genuinely reversible.

## 22. Test 20 — sensor failure injection

Inject failures into:

- hot-side temperature sensor;
- cold-side temperature sensor;
- sink temperature sensor;
- pressure transducer;
- flow meter;
- acoustic pressure sensor.

### Safe behavior

A single failed measurement must not cause the controller to command maximum source heat or acoustic drive.

### Finding

Sensor plausibility checks and redundancy are mandatory for serious prototype control.

## 23. Test 21 — stuck valve / failed pump

Scenarios:

1. hot-loop valve stuck closed;
2. cold-loop valve stuck closed;
3. pump loses flow;
4. bypass valve fails open;
5. bypass valve fails closed.

### Finding

Software-only diagnosis is insufficient. Differential pressure, flow and temperature signatures should cross-check one another.

## 24. Test 22 — simultaneous faults

Harder case:

`high ambient + source overshoot + low flow + one failed sensor`

The controller must fail toward a safe thermal state rather than trying to preserve the cooling setpoint at all costs.

### Severity

**CRITICAL** for prototype safety analysis.

This is a required hardware-in-the-loop test later.

## 25. Test 23 — startup from cold soak

Scenario:

- THERMA at low ambient;
- source suddenly becomes available;
- working gas pressure stable;
- secondary loops initially near ambient.

Risks include thermal shock, delayed heat-exchanger stabilization and acoustic onset transients.

### Finding

Startup sequencing needs a ramp profile, not simply `ON`.

## 26. Test 24 — shutdown under thermal gradient

Scenario:

A running unit loses heat source suddenly.

Required response:

- reduce acoustic state;
- stabilize pressure;
- prevent uncontrolled thermal backflow;
- isolate source if necessary;
- preserve safe sink-side conditions.

### Finding

Emergency shutdown must be modeled as a transient thermal event, not just a software bit.

## 27. Test 25 — cold-side overload

Scenario:

A warm product load enters faster than design.

The controller should report:

`load > capacity`

rather than indefinitely increasing source input.

### Finding

A cooling machine must have an explicit overload state and communicate expected recovery time.

## 28. Test 26 — heat-rejection saturation

Scenario:

Heat sink temperature rises until exchanger approach becomes impossible.

The machine may have plenty of internal acoustic capability but insufficient rejection capacity.

### Finding

A THERMA refrigerator cannot be evaluated independently of its heat sink and heat-rejection hardware.

## 29. Test 27 — scaling to 10 MW

A 10 MW industrial heat-source concept cannot be treated as ten thousand 1 kW cores without validated module power density and coupling.

Scaling questions:

- acoustic cross-talk;
- header losses;
- flow distribution;
- heat rejection;
- maintenance access;
- module mismatch;
- control-network latency;
- common-mode faults.

### Finding

MW-scale architecture is a separate engineering problem, not simple multiplication.

## 30. Test 28 — economic reversal test

Suppose electricity becomes cheap while waste heat is expensive to recover.

The business case may reverse toward ordinary electric compression.

### Finding

THERMA's economics depend on the value of the heat source, not merely the existence of waste heat.

## 31. Test 29 — small-building economics

For small household-scale loads, the cost of:

- pressure vessel;
- acoustic resonator;
- heat exchangers;
- safety systems;
- pumps;
- controls;
- commissioning;

may dominate energy savings.

### Finding

Small residential applications are probably not the first commercial target.

## 32. Test 30 — industrial sweet spot search

The architecture becomes more attractive where all of the following overlap:

- continuous waste heat;
- source temperature comfortably above sink;
- high cooling demand;
- long annual utilization;
- limited electricity availability/cost;
- manageable piping distance;
- reliable heat rejection;
- industrial operator capable of maintenance.

### Finding

The strongest early-market candidate remains high-utilization industrial waste heat rather than generic household refrigeration.

## 33. Test 31 — no-moving-parts reality check

The absence of pistons and crankshafts reduces conventional mechanical wear, but it does not eliminate:

- pressure fatigue;
- thermal fatigue;
- regenerator degradation;
- exchanger fouling;
- seal aging;
- valves/pumps in secondary loops;
- control-electronics failure.

### Finding

“No moving parts” should be advertised as **reduced mechanical-motion wear**, not as “nothing can wear out.”

## 34. Test 32 — acoustic contamination / structural vibration

High acoustic pressure can couple into the chassis, piping and supports.

Risks:

- resonance of support structures;
- fatigue at nozzles;
- noise;
- vibration-induced instrumentation errors;
- acoustic leakage into adjacent modules.

### Finding

The structural frame needs modal analysis once the exact acoustic geometry exists.

## 35. Test 33 — model-form uncertainty

Three reduced models can all be internally consistent while disagreeing because they use different assumptions for:

- heat transfer;
- acoustic loss;
- streaming;
- leakage;
- exchanger effectiveness;
- regenerator effectiveness.

### Finding

Agreement between two reduced models is not independent validation if both share the same hidden assumption.

## 36. Test 34 — literature-to-THERMA transfer risk

Published results cannot be transferred directly because experiments use different:

- geometry;
- working fluid;
- pressure;
- source temperature;
- sink temperature;
- drive ratio;
- stack/regenerator;
- heat exchanger;
- load definition.

### Finding

Literature is a physics anchor, not a THERMA performance certificate.

## 37. Test 35 — advanced optimization trap

Modern thermoacoustic research is moving toward surrogate models, multi-objective optimization, inverse design and reinforcement-learning-assisted optimization, but recent review work emphasizes data scarcity and model-generalization challenges.

Source: https://doi.org/10.1016/j.rser.2026.117255

### Finding

AI optimization should not be allowed to optimize an unvalidated physics model into a false optimum.

## 38. Test 36 — adversarial objective mismatch

Try optimizing only for `maximum cooling power`.

Likely side effects:

- reduced COP;
- higher drive ratio;
- more pressure amplitude;
- more heat rejected;
- more structural loading;
- potentially shorter component life.

### Finding

THERMA must use a multi-objective design target:

`maximize useful cooling/heating`

subject to:

`pressure + temperature + fatigue + leakage + cost + acoustic stability + safety limits`.

## 39. Test 37 — worst-combination screen

Combine:

- source = 80 °C;
- sink = 50 °C;
- cold target = 3 °C;
- large transient load;
- exchanger degradation;
- partial flow loss;
- acoustic detuning.

The thermodynamic ceiling is already severely reduced by the small source/sink gap, before real losses are included.

### Finding

This combination should be classified as **degraded/unacceptable for first prototype operation**, unless physical testing demonstrates otherwise.

## 40. Test 38 — best-case screen

Combine:

- source = 120–200 °C;
- sink = 25–35 °C;
- stable flow;
- optimized regenerator;
- validated heat exchangers;
- controlled drive ratio.

### Finding

This is the strongest region for the first proof-of-physics prototype, consistent with the existing project conclusion that a favorable 80–120 °C source is a better first target than universal 60 °C operation.

## 41. Test 39 — architecture break test

Attempt to break the concept by removing each subsystem:

### Remove regenerator
Acoustic engine/refrigerator function loses its intended thermoacoustic thermal interaction.

### Remove heat exchanger
Useful external thermal transfer collapses.

### Remove resonator/impedance network
The required acoustic field cannot be established as designed.

### Remove pressure boundary
Working-gas containment is lost.

### Remove sink/heat rejection
The refrigeration process cannot reject the transported heat.

### Finding

THERMA is a tightly coupled system. It cannot be reduced to “a hot tube making cold.”

## 42. Test 40 — fundamental conclusion of adversarial testing

The concept did **not** fail at the level of the underlying thermoacoustic principle.

It **did fail** several optimistic product assumptions:

- universal low-grade operation;
- arbitrary rapid cooling;
- unlimited proportional scaling;
- direct exposure to arbitrary source temperatures;
- assumption that no moving mechanical parts means no fatigue or maintenance;
- assumption that thermal source availability is constant;
- assumption that an acoustic design can be finalized from an illustration.

## 43. Current weaknesses ranked

| Rank | Weakness | Severity | Required response |
|---:|---|---|---|
| 1 | Low source-to-sink temperature head | Critical | Target favorable source first |
| 2 | Heat-exchanger uncertainty | Critical | Exact-geometry experimental validation |
| 3 | Rapid cooling power density | Critical | Separate transient-capacity architecture |
| 4 | Acoustic geometry uncertainty | Critical | Reproducible exact-geometry model |
| 5 | Pressure/thermal fatigue | High | Cyclic qualification |
| 6 | Heat-source intermittency | High | buffering + degraded modes |
| 7 | Sensor/actuator faults | High | redundancy + independent protection |
| 8 | Heat-rejection saturation | High | size rejection system with load |
| 9 | Scaling economics | High | module validation before scaling |
| 10 | Model-form uncertainty | High | correlation against hardware |

## 44. What survived

The following remain credible as research hypotheses:

- heat-driven thermoacoustic refrigeration is physically real;
- thermoacoustic devices can operate without a conventional mechanical compressor;
- waste heat can be a useful driving resource in favorable temperature ranges;
- acoustic heat-pump operation is physically established in the research literature;
- reversible acoustic/thermal routing is a plausible direction;
- fixed-hardware modularity can be engineered in principle;
- industrial waste heat is the strongest early application class.

Recent reviews continue to identify heat-driven thermoacoustic cooling as a promising route while emphasizing acoustic losses, phase mismatch, materials and scaling as major unresolved issues. https://doi.org/10.1016/j.ijrefrig.2025.12.030

## 45. Prototype decision after stress testing

The most defensible first prototype is **not** a consumer refrigerator.

It is:

- single core;
- fixed hardware;
- heavily instrumented;
- favorable 80–120 °C thermal source;
- controlled heat sink;
- measurable acoustic field;
- measurable hot/cold heat transfer;
- exact geometry solved before fabrication;
- independent mechanical safety layer.

The first question is:

> Can one exact geometry convert a controlled thermal gradient into measurable stable acoustic power and useful thermal transfer with a reproducible model-to-hardware correlation?

If yes, the project advances.

If no, the next step is redesign or stop—not optimistic scaling.

## 46. Final stress-test verdict

**THERMA 3.5 is not broken as a physical concept by this campaign.**

However, the campaign exposes several conditions under which the concept becomes technically unattractive or impossible to meet with current assumptions.

The principal make-or-break variables are:

1. exact acoustic geometry;
2. heat-exchanger effectiveness under oscillatory flow;
3. regenerator performance;
4. source/sink temperature head;
5. power density and rapid-load capacity;
6. pressure and thermal fatigue;
7. control robustness under combined faults;
8. economics at real installed scale.

## 47. Verification level

This report combines first-principles calculations, adversarial scenario logic and current literature review.

It is **not** a physical validation report.

The next true verification stage is hardware.

## 48. Required next exact-geometry work

Before claiming prototype readiness, the following parameters need to be frozen:

- working gas;
- mean pressure;
- drive ratio / acoustic amplitude target;
- frequency;
- resonator lengths/areas;
- inertance/compliance values;
- regenerator length, pore scale and porosity;
- hot and cold exchanger geometry;
- flow rates;
- pressure boundary dimensions;
- thermal conditioning loop;
- control sequence.

Only after those are defined can a coupled solver produce a geometry-specific prediction suitable for hardware comparison.

## 49. Final engineering rule

Every future THERMA result must answer:

`What exactly was assumed?`

`What equation or solver produced the result?`

`What external evidence supports the model?`

`What would falsify it?`

`What must be measured in the prototype?`

## 50. Close-out statement

The advanced campaign did what it was supposed to do: it reduced optimism, exposed weak operating regions, identified the most dangerous hidden assumptions, and narrowed the credible prototype envelope.

THERMA 3.5 should now be developed around **evidence, exact geometry, measurement and regression**, not around a single idealized COP or a visually impressive machine.

### Primary references used for this stress campaign

1. 2026 review — Heat-driven thermoacoustic cooling technologies: https://doi.org/10.1016/j.ijrefrig.2025.12.030
2. 2026 review — Machine-learning-assisted design and optimization: https://doi.org/10.1016/j.rser.2026.117255
3. 2025 experimental validation/optimization of standing-wave TAR: https://doi.org/10.1016/j.applthermaleng.2024.125302
4. 2025 transient/thermal-boundary investigation: https://doi.org/10.1016/j.ijheatmasstransfer.2024.126250
5. 2025 transcritical CO2 thermoacoustic engine experiment: https://doi.org/10.1016/j.applthermaleng.2025.127951
6. 2023 additive-manufactured stack experimental development: https://doi.org/10.1016/j.ijrefrig.2022.10.007
7. 2024 comprehensive thermoacoustic review: https://doi.org/10.1016/j.ijheatmasstransfer.2024.125758

## Appendix — interpretation rules

- A calculated ceiling is not a performance prediction.
- An experimental result from another machine is not a THERMA result.
- A generated diagram is not a fabrication drawing.
- A Monte Carlo scenario count is not millions of physical experiments.
- A no-moving-parts core can still suffer pressure and thermal fatigue.
- A waste-heat source is only useful when the source-to-sink temperature relationship is favorable.
- Rapid cooling is a power-density problem, not merely a target-temperature problem.
- More thermal input is not guaranteed to produce proportionally more acoustic power.
- More acoustic drive is not guaranteed to improve COP.
- A reversible system needs a controlled neutral transition state.
- Software is not an adequate substitute for independent pressure and thermal safety barriers.
- Scaling requires validated module power density and distribution design.
- Prototype correlation is the final authority.
