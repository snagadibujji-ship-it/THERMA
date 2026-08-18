# 004 — Thermoacoustic Fundamentals

## Scope
This file establishes the physical vocabulary required for THERMA without treating the concept as a new law of physics.

## Acoustic field
Thermoacoustic systems contain a working gas whose pressure, density, velocity and temperature oscillate in time. The gas parcels move back and forth around local equilibrium positions. This oscillatory motion is the central physical distinction from a conventional one-way-flow machine.

## Pressure and velocity
An acoustic wave carries energy through correlated pressure and particle velocity. In practical resonators, the phase relationship between pressure and velocity determines where acoustic energy is stored, dissipated or transferred to other elements.

## Compression and expansion
During a portion of the acoustic cycle, a gas parcel is compressed. Its pressure and temperature rise. During another portion it expands and its temperature falls. If the gas exchanges heat with nearby solid surfaces at the correct phase, the cycle can create net directed heat transport.

## Gas-solid thermal interaction
A regenerator or stack supplies a large solid surface area. The oscillating gas repeatedly interacts with that surface. The timing of thermal exchange relative to pressure and velocity is essential: too little exchange wastes potential, while excessive conduction can short-circuit the desired temperature gradient.

## Thermal boundary layer
Oscillatory thermal diffusion creates a characteristic penetration depth in the gas adjacent to a solid surface. The relevant scale influences pore spacing, stack geometry and heat-transfer effectiveness.

## Viscous boundary layer
Viscous effects also create a characteristic near-wall region in which acoustic velocity is strongly attenuated. It contributes to acoustic losses and therefore influences channel geometry and hydraulic radius.

## Regenerator/stack
The regenerator provides solid thermal capacity and heat-transfer surface area. Important design variables include thermal conductivity, heat capacity, porosity, pore size, hydraulic radius, length and pressure drop.

## Thermoacoustic engine
In engine mode, a sufficient thermal gradient across a suitable thermoacoustic element can amplify acoustic oscillations and produce time-averaged acoustic power. The thermal gradient is converted partly into organized acoustic/mechanical energy.

## Thermoacoustic refrigerator
In refrigerator mode, externally supplied acoustic work is used to pump heat away from a cold-side load and toward a warmer rejection side. The cold-side heat exchanger couples this process to the secondary thermal loop.

## Heat-pump mode
In heat-pump mode, acoustic work drives heat transfer from a lower-temperature source to a higher-temperature delivery side. The hot-side output includes both extracted source heat and supplied work, subject to losses.

## First-law relationship
For a heat pump, the basic energy balance is Q_H = Q_C + W. For a refrigerator driven by external work, COP_C = Q_C/W. For heating, COP_H = Q_H/W. In a heat-driven engine-refrigerator architecture, the input convention must be stated separately because the driving heat is not identical to electrical/mechanical work.

## Carnot bound
For a reversible heat pump between absolute temperatures T_C and T_H, the maximum heating COP is T_H/(T_H-T_C). This is an upper bound, not a THERMA performance prediction.

## Acoustic impedance
The acoustic system presents an impedance relating pressure amplitude and volume velocity. The resonator, inertance, compliance and load must be matched sufficiently well to transfer useful acoustic power.

## Resonance
Resonance occurs where the stored acoustic energy and reactive elements support a suitable oscillatory mode. Exact resonance is not simply a visual tube length; boundary conditions, gas properties, end corrections, geometry and losses all matter.

## Inertance and compliance
An inertive element stores kinetic/acoustic energy; a compliant volume stores potential/compressional energy. Together with acoustic resistance, these elements form an impedance network.

## Streaming
Thermoacoustic systems can develop steady mass transport called acoustic streaming. Gedeon streaming in looped configurations can carry heat parasitically. Streaming is therefore a loss mechanism and a stability concern.

## Nonlinear effects
At larger pressure amplitudes, the simple linear model can break down. Saturation, harmonic generation, streaming, turbulence-like losses and nonlinear heat-transfer behavior can limit scaling.

## No-mechanical-moving-parts rule
The gas oscillates, but the THERMA 3.5 core is not a reciprocating piston engine. There is no piston, crankshaft, connecting rod or flywheel in the intended core. External pumps or valves in secondary loops may move, but they are not the core's thermoacoustic energy converter.

## Why this matters
The absence of a mechanical compressor or reciprocating power train could reduce wear mechanisms, but it does not eliminate all failure modes. Pressure boundaries, seals, heat exchangers, sensors, valves, acoustic structures and materials still require inspection and maintenance.

## Practical conclusion
Thermoacoustic physics is established. THERMA's research challenge is the exact implementation: geometry, gas, pressure, regenerator, heat exchangers, impedance, controls and integration must be optimized as a coupled system.
