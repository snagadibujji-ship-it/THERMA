# THERMA 3.5 — Break Test 001: Thermal Envelope and Rapid-Cooling Adversarial Analysis

Status: active engineering test record
Architecture: fixed-hardware thermoacoustic core with oscillating working gas
Purpose: deliberately search for a thermodynamic or architectural weakness rather than confirm the design by default.

## 1. Scope

This test attacks the current THERMA 3.5 concept at the system level using first-principles bounds and published thermoacoustic benchmarks.

The test does not claim exact acoustic-field validation because no single exact THERMA geometry, frequency, mean pressure, regenerator geometry and heat-exchanger geometry has yet been frozen.

The test therefore answers a narrower and defensible question:

> Are any of the current target claims already inconsistent with thermodynamic upper bounds or with the scale of published thermoacoustic hardware?

## 2. Locked architecture

The core is fixed hardware.

The working gas oscillates acoustically.

The core contains no piston.

The core contains no displacer.

The core contains no crankshaft.

The core contains no connecting rod.

The core contains no flywheel.

The core contains no reciprocating mechanical compressor.

External pumps and valves may exist in secondary thermal loops.

## 3. Test A — Ideal upper bound for heat-driven refrigeration

For a heat-driven refrigerator idealized as a reversible heat engine driving a reversible refrigerator, an upper bound can be formed from:

eta_engine,max = 1 - T_sink/T_source

COP_refrigerator,max = T_cold/(T_sink - T_cold)

COP_heat_driven,max = eta_engine,max * COP_refrigerator,max

This is an optimistic reversible bound. It is not a prediction of THERMA.

Assume a cold target of 3 °C and an environmental heat sink of 35 °C.

The resulting ideal upper bounds are approximately:

Source 60 °C -> COP_heat-driven,max ≈ 0.648

Source 70 °C -> COP_heat-driven,max ≈ 0.880

Source 80 °C -> COP_heat-driven,max ≈ 1.100

Source 100 °C -> COP_heat-driven,max ≈ 1.503

Source 120 °C -> COP_heat-driven,max ≈ 1.866

Source 150 °C -> COP_heat-driven,max ≈ 2.345

Source 200 °C -> COP_heat-driven,max ≈ 3.009

Source 300 °C -> COP_heat-driven,max ≈ 3.990

These are thermodynamic ceilings for the simplified cascade and include no real-world acoustic, regenerator, heat-exchanger, pressure-drop, streaming, leakage or control losses.

## 4. Immediate finding — low-temperature branch is the first weakness

At a 60 °C source, 35 °C sink and 3 °C cold target, the ideal heat-driven COP ceiling is only about 0.65.

Therefore any claimed THERMA thermal-input COP substantially above 0.65 for those exact boundary temperatures would be thermodynamically impossible.

At 80 °C, the ideal ceiling rises to only about 1.10.

Therefore an 80 °C source cannot support an arbitrarily high thermal-input COP under these conditions.

This does not prove that 60–80 °C operation is impossible.

It proves that it is a tight operating region in which losses matter strongly.

## 5. Literature cross-check

A published 2023 heat-driven thermoacoustic refrigerator reported a minimum onset heating temperature of about 64 °C, but its reported 5.62 kW cooling / COP 0.41 operating point used a 300 °C heating temperature, 10 °C cooling temperature and 45 °C ambient.

The same study reported 0.66–5.62 kW cooling and COP 0.12–0.41 over its tested conditions and a reported power density of up to 14.95 kW/m³.

This is important because it separates two ideas:

1. onset near the low-grade region has been demonstrated in one research architecture;
2. high useful cooling output was demonstrated at substantially hotter conditions.

The literature therefore does not support treating the 60–80 °C region as automatically equivalent to the 300 °C operating point.

## 6. Literature benchmark — reversible heating/cooling

A 2026 experimental heat-driven thermoacoustic refrigerator/heat pump reported 7.31 kW heating at COP_h 1.28 in a heating-only condition with 300 °C heating, 50 °C heat-pumping and 10 °C ambient temperatures.

In a different cooling-only condition, it reported 2.75 kW cooling at COP_c 0.34 with 300 °C heating, 35 °C ambient and 7 °C cooling.

Those results establish that the broader category is real.

They do not validate THERMA geometry or THERMA performance at 60–80 °C sources or 0–3 °C loads.

## 7. Test B — 0–3 °C rapid pull-down

For water-equivalent product mass m cooled from 25 °C to 3 °C:

Q = m * cp * DeltaT

with cp ≈ 4.186 kJ/kg-K and DeltaT = 22 K.

The sensible energy requirements are approximately:

30 kg -> 0.767 kWh

100 kg -> 2.558 kWh

500 kg -> 12.791 kWh

1000 kg -> 25.581 kWh

If all of that sensible heat were removed in 15 minutes, the ideal average refrigeration capacities would be:

30 kg -> 3.07 kW

100 kg -> 10.23 kW

500 kg -> 51.16 kW

1000 kg -> 102.32 kW

Real requirements are higher after walls, infiltration, product packaging, fan heat, exchanger approach and other loads.

## 8. Rapid-cooling conclusion

The 15-minute target is not a universal property of THERMA.

For a small 30 kg water-equivalent load, a few-kW cooling system is theoretically within the same order of magnitude as published thermoacoustic research hardware.

For 500 kg, roughly 51 kW average sensible cooling is already required before losses.

For 1000 kg, roughly 102 kW average sensible cooling is required before losses.

Therefore a single small THERMA core cannot honestly be presented as a universal minutes-scale rapid refrigerator.

A rapid version must scale the actual refrigeration power, use parallel cores, or use a validated thermal-storage strategy.

## 9. Test C — Compare rapid capacity with published power density

Using the published 14.95 kW/m³ power-density figure only as an illustrative benchmark, not as a THERMA prediction:

30 kg / 15 min -> about 0.205 m³ of active refrigeration volume at that benchmark.

100 kg / 15 min -> about 0.685 m³.

500 kg / 15 min -> about 3.42 m³.

1000 kg / 15 min -> about 6.84 m³.

This simple comparison shows the physical scaling burden.

It is not a final machine-volume estimate because the published power density depends on a particular device, operating conditions and definition.

## 10. Test D — Heating 20 °C to 80 °C

One litre of water requires approximately 69.8 Wh of sensible heat to rise from 20 °C to 80 °C.

The reversible heat-pump COP ceiling is:

COP_h,Carnot = T_hot/(T_hot - T_source)

For 20 °C source and 80 °C delivery:

COP_h,Carnot ≈ 5.89.

This is an ideal upper bound, not a THERMA prediction.

At 1 L/min, the ideal thermal delivery rate is approximately 4.19 kW.

At 5 L/min, approximately 20.93 kW.

At 10 L/min, approximately 41.86 kW.

At 100 L/min, approximately 418.6 kW.

The actual input work will be higher than the reversible minimum because of acoustic, regenerator, heat-exchanger and control losses.

## 11. Test E — Ambient-temperature sensitivity

Keeping source temperature at 80 °C, cold target at 3 °C and changing the heat sink produces a major shift in the ideal heat-driven refrigeration ceiling.

Sink 25 °C -> ceiling ≈ 1.95.

Sink 30 °C -> ceiling ≈ 1.45.

Sink 35 °C -> ceiling ≈ 1.10.

Sink 40 °C -> ceiling ≈ 0.845.

Sink 45 °C -> ceiling ≈ 0.652.

Sink 50 °C -> ceiling ≈ 0.499.

This is a critical adversarial result for Indian-summer operation.

A machine cannot be specified only by source temperature.

The source/sink pair and required cold target must be specified together.

## 12. Test F — 60 °C source in hot ambient

At 60 °C source and 45 °C sink with a 3 °C cold target, the ideal heat-driven COP ceiling becomes substantially lower than the already difficult 35 °C-sink case.

This should be considered a high-risk operating state rather than a guaranteed operating state.

The correct response for a future controller is controlled derating or shutdown when the available thermal gradient is insufficient.

## 13. Test G — 1500 °C accidental input

A raw 1500 °C liquid stream must not enter the THERMA core.

This is not a performance test in which more input is expected to create more cooling.

It is a protection test.

The correct architecture is:

1500 °C stream -> isolation/diverter -> high-temperature-rated recovery stage -> controlled secondary thermal loop -> THERMA hot-side interface.

Direct exposure would create severe material, thermal-shock and pressure hazards unless a separately qualified system were designed for that temperature.

## 14. Test H — “More heat gives more cooling” attack

The model is explicitly rejected if it assumes unlimited proportional scaling.

As source heat rises, possible limits include regenerator thermal short-circuiting, acoustic saturation, streaming, heat-exchanger bottlenecks, pressure drop, structural temperature limits and rejection capacity.

Therefore the correct control objective is optimum useful thermal throughput rather than maximum heat input.

## 15. Test I — No-moving-parts attack

The no-moving-mechanical-core requirement remains physically coherent with thermoacoustic operation because the working gas itself undergoes oscillatory pressure and velocity motion.

This does not mean the total installation has no moving components.

External secondary loops may use pumps and valves.

Those do not create the forbidden piston/Stirling core.

## 16. Test J — Architecture consistency attack

The largest documentation weakness discovered during illustration generation was architecture drift into piston, crankshaft, connecting-rod and flywheel assemblies.

Those generated images are now classified as invalid THERMA 3.5 architecture.

They must not be used as evidence or as authoritative engineering drawings.

The locked architecture is the fixed thermoacoustic core described in the repository documentation.

## 17. Test K — What can currently be claimed

Supported by basic thermodynamics:

- water sensible-heating calculations;
- first-law heat balances;
- Carnot upper bounds;
- load-energy and pull-down power calculations.

Supported by literature:

- thermoacoustic engines exist;
- heat-driven thermoacoustic refrigeration exists;
- reversible thermoacoustic heating/cooling has experimental precedent;
- limited low-grade onset has been demonstrated in published hardware.

Not yet established for THERMA:

- exact resonator geometry;
- exact acoustic pressure amplitude;
- exact onset temperature;
- exact cooling capacity;
- exact heating COP;
- exact regenerator effectiveness;
- exact oscillatory HX performance;
- exact power density;
- pressure-vessel life;
- long-term helium leakage.

## 18. Current failure/weakness classification

### Weakness 1 — Low-grade thermal driving
60–80 °C source temperatures with hot ambient sinks are thermodynamically tight.

### Weakness 2 — Rapid cooling power
Minutes-scale pull-down for large loads requires tens to hundreds of kilowatts of cooling power.

### Weakness 3 — Heat exchanger validation
Thermoacoustic oscillatory-flow heat transfer remains a documented design challenge in the field.

### Weakness 4 — Exact acoustic design
The current project does not yet have a validated exact geometry with measured onset, amplitude and impedance.

### Weakness 5 — Scaling
A small successful core cannot be scaled linearly to MW-class systems without a validated power-density and thermal-network model.

### Weakness 6 — High-temperature source handling
The system requires a controlled source interface and independent emergency diversion.

## 19. Does this break THERMA?

No fundamental contradiction has been found in the category-level physics.

However, the analysis breaks several overly broad product assumptions:

- universal 60 °C operation;
- universal 15-minute pull-down;
- proportional cooling from unlimited heat input;
- direct ingestion of arbitrary industrial temperatures;
- simple scaling from a small core to town-scale MW output;
- use of generated pictures as proof of exact engineering geometry.

## 20. Current engineering status after Break Test 001

THERMA 3.5 remains a plausible pre-prototype research architecture.

The strongest development target is no longer “prove everything by simulation.”

The strongest target is to choose one exact geometry, select a thermally favorable source condition, reproduce the model independently, and build the instrumented test article that can attack these identified weaknesses experimentally.

## 21. Immediate prototype gates

Gate A — exact acoustic geometry.

Gate B — heat-exchanger geometry validated for oscillatory flow.

Gate C — regenerator geometry and material selected.

Gate D — pressure boundary and relief system qualified.

Gate E — measured acoustic onset and stability.

Gate F — measured thermal power.

Gate G — 0–3 °C cooling demonstration.

Gate H — 20–80 °C heat-pump demonstration.

Gate I — reversible mode switching.

Gate J — endurance and measured-vs-model correlation.

## 22. Conclusion

The first serious adversarial test did not prove THERMA.

It did something more useful: it identified where THERMA is weakest before hardware is built.

The two largest immediate risks are low-grade-source performance and rapid-cooling power density.

Those are now explicit engineering targets rather than hidden assumptions.
