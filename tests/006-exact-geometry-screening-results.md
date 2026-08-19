# THERMA 3.5 — Exact-Geometry Screening Results

## Status

This is a reduced-order screening run against one explicitly frozen candidate geometry. It is not a DeltaEC/SAGE/CFD solution and does not establish experimental performance.

## Candidate geometry

Working gas: helium.
Mean pressure: 1.0 MPa.
Nominal frequency: 100 Hz.
Resonator diameter: 50 mm.
First-order quarter-wave reference length evaluated with c = sqrt(gamma R T).
Regenerator length: 100 mm.
Nominal regenerator gap: 0.50 mm.
Hot heat exchanger: 120 mm reference length.
Cold heat exchanger: 120 mm reference length.
Drive ratio: 5%.
Nominal source temperature: 100 °C.
Nominal heat sink: 35 °C.
Nominal cold target: 3 °C.

## Acoustic reference

Using a screening helium sound-speed calculation at 100 °C, c ≈ 1,137 m/s. A simple quarter-wave reference at 100 Hz therefore gives L ≈ 2.84 m before end corrections, junction effects, inertance/compliance elements and other acoustic-network modifications.

This is an important correction to earlier generic geometry estimates: the reference length is temperature-dependent and should not be treated as a fixed 2.55 m fabrication value.

## Temperature/frequency drift

For the same simple quarter-wave reference geometry, estimated acoustic resonance changes approximately with sound speed. Using the same simplified property model:

20 °C: c ≈ 1,007 m/s.
100 °C: c ≈ 1,137 m/s.
130 °C: c ≈ 1,181 m/s.
200 °C: c ≈ 1,280 m/s.

If length is fixed to the 100 °C / 100 Hz reference, the corresponding first-order frequency would move roughly with c/L. The result is an approximately 11–13% frequency change over a broad source-temperature excursion. This supports the need for a tuning strategy or sufficiently broad stable operating window.

## Thermal penetration / viscous scale

For the screening property assumptions used here, characteristic oscillatory boundary-layer scales at 1 MPa are on the order of tenths of a millimetre. At 100 Hz the calculated viscous penetration depth is about 0.238 mm and thermal penetration depth about 0.267 mm.

The nominal 0.50 mm regenerator gap is therefore only on the order of two thermal penetration depths. That means the regenerator geometry is strongly coupled to frequency, gas properties, porosity, wall condition and acoustic amplitude. It should not be considered an arbitrary manufacturing dimension.

## Acoustic pressure/power scale

At 1.0 MPa mean pressure and a 5% drive ratio, the assumed pressure amplitude is about 50 kPa.

For a simple plane-wave order-of-magnitude calculation across a 50 mm diameter section, the estimated acoustic power scale is approximately 1.7 kW under the idealized lossless relation P ≈ p_amp² A /(2 rho c).

This number is NOT cooling capacity. It is not a full thermoacoustic power result and does not include boundary-layer losses, streaming, imperfect impedance matching, regenerator losses, heat-exchanger losses, nonlinear saturation or acoustic-network geometry.

It is useful only as a scale check: THERMA cannot claim kilowatts of cooling merely because an ideal acoustic wave calculation produces kilowatts of acoustic power.

## Thermodynamic head test

For a 3 °C cold target and 35 °C heat sink, an ideal reversible heat-driven cooling upper-bound model gives approximately:

60 °C source → 0.648.
80 °C source → 1.100.
100 °C source → 1.503.
120 °C source → 1.866.
150 °C source → 2.345.
200 °C source → 3.009.

These are thermodynamic ceilings, not THERMA predictions. Actual performance must be lower after heat-exchanger approach temperatures, acoustic losses, regenerator losses, nonlinear effects, streaming and auxiliaries.

## Rapid cooling test

Sensible energy for 25 → 3 °C water-equivalent load is approximately 25.6 Wh/kg.

30 kg: approximately 0.767 kWh; 15-minute average cooling ≈ 3.07 kW.
100 kg: approximately 2.56 kWh; 15-minute average cooling ≈ 10.2 kW.
500 kg: approximately 12.8 kWh; 15-minute average cooling ≈ 51.2 kW.
1,000 kg: approximately 25.6 kWh; 15-minute average cooling ≈ 102 kW.

These figures are sensible-load requirements before infiltration, wall heat leak, product packaging, fans, pumps, heat-exchanger approach temperatures and other losses. Therefore rapid 15-minute cooling is governed by cooling power density and thermal-buffer/module architecture, not by the 0–3 °C target alone.

## Fatigue stress

At 100 Hz, fixed components are exposed to approximately 3.15 billion acoustic cycles per year. At 75 Hz the count is approximately 2.37 billion/year; at 125 Hz approximately 3.94 billion/year.

This does not prove failure, but it proves that “no moving parts” does not mean “no cyclic fatigue problem.” The pressure boundary, welds, ports, heat-exchanger attachments, acoustic tubing and structural mounts all require cyclic-load assessment.

## Break conditions observed

1. Low source temperature combined with high sink temperature can remove almost the entire thermodynamic head.
2. Resonator frequency shifts with gas temperature, creating a packaging/control problem if no tuning mechanism exists.
3. Regenerator channel scale is comparable to oscillatory thermal/viscous boundary-layer scales, making performance highly geometry-sensitive.
4. Ideal acoustic power scale is not equal to useful cooling capacity.
5. Rapid cooling requires tens to hundreds of kW for large loads and therefore cannot be obtained by small-core scaling alone.
6. Billion-cycle exposure makes fixed-hardware fatigue a first-class qualification problem.

## What survives

The candidate remains physically plausible as a thermoacoustic research architecture because none of the screening results creates a first-principles contradiction. However, the candidate does not yet pass a fabrication-freeze gate.

## Required next calculation

The next model must add exact acoustic junction geometry, inertance/compliance volumes, actual regenerator matrix geometry, hot/cold heat-exchanger channel geometry and thermal boundary conditions. The resulting model must calculate resonance, pressure amplitude, phase, acoustic power, thermal span, heat-transfer rate and loss channels together.

## Required hardware evidence later

Prototype measurements must include pressure amplitude, mean pressure, frequency, phase, hot and cold temperatures, source/sink flows, heat input, Qc, Qh, auxiliary power, helium inventory, leakage and uncertainty.

## Evidence status

All numbers in this file are reduced-order screening calculations from the explicitly stated assumptions. None should be described as experimentally measured THERMA performance.
