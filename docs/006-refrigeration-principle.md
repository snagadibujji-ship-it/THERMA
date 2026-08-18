# 006 — Thermoacoustic Refrigeration Principle

## Purpose
This file defines the refrigeration side of THERMA and keeps temperature targets separate from cooling capacity.

## Basic process
The refrigeration section uses acoustic work to pump heat away from a cold load and reject that energy at a warmer sink. The acoustic field oscillates the working gas through a fixed thermoacoustic geometry; there is no mechanical compressor or piston in the intended core.

## Cold heat exchanger
The cold heat exchanger is the interface between the user-side cooling loop and the thermoacoustic working gas. Its objective is to remove heat from the secondary fluid with a controlled approach temperature and acceptable pressure drop.

## Refrigeration loop
The simplified chain is: load → secondary cold loop → cold heat exchanger → thermoacoustic refrigerator → heat-rejection exchanger → sink. The process must be analyzed using the actual load profile rather than a single nominal cold temperature.

## 0–3 °C target
The project repeatedly selected 0–3 °C as the target cold-side range for chilled products and selected cold-room applications. This is a temperature target, not a statement of cooling power.

## Cooling capacity
Cooling capacity Qc is the rate at which heat is removed. It should be reported in watts or kilowatts under defined source, sink and load conditions. A machine that reaches 3 °C slowly is not equivalent to a machine that removes tens of kilowatts while maintaining 3 °C.

## Pull-down vs maintenance
Initial pull-down can dominate the thermal requirement because the room, product and internal mass begin warm. After reaching the target, the machine primarily removes incoming heat from conduction, infiltration, doors, lighting and internal equipment.

## Rapid cooling
The 3.3 design problem arose because a heat-driven machine may take many hours to pull down a warm load. Rapid cooling therefore requires a dedicated high-capacity mode, multiple parallel fixed cores, thermal buffering, or another source of short-duration cooling energy.

## 15-minute example
For 500 kg of water-equivalent product cooling from 25 °C to 3 °C, sensible heat removal is approximately 12.8 kWh. Removing that in 15 minutes would require about 51 kW average cooling before additional losses. This example is a load-sizing demonstration, not a THERMA hardware result.

## Heat rejection
All refrigeration processes reject the extracted load heat plus input work/energy. The receiving sink can be ambient air, cooling water or another appropriate thermal reservoir.

## COP definitions
For externally driven refrigeration, COPc = Qc/W when W is supplied work. For heat-driven systems, the input convention may use driving heat, so the reported thermal-input COP must identify that denominator explicitly.

## Temperature lift
Performance depends strongly on the difference between cold-side target and heat-sink temperature as well as heat-exchanger approach temperatures. A 0–3 °C target can therefore be much harder in a hot ambient than in a cool environment.

## Heat exchanger requirements
Oscillatory-flow heat transfer is not identical to steady-flow heat transfer. The heat exchanger must be evaluated for the actual acoustic amplitude, frequency, pressure and flow path.

## Regenerator coupling
Refrigeration performance depends on the regenerator's ability to exchange heat with oscillating gas while limiting unwanted thermal conduction and viscous/acoustic losses.

## Acoustic impedance
The refrigerator must be matched to the acoustic power source. A large acoustic power generator does not help if the refrigerator input impedance is poorly matched or dissipative.

## Streaming losses
Mean flow caused by acoustic streaming can carry heat in an undesired direction and reduce net refrigeration. Gedeon streaming is an important concern in looped systems.

## Control
The control system should maintain cold-side temperature by adjusting permissible operating states, acoustic drive/routing and external fluid flow. It should not override hard safety limits.

## Cold-loop instrumentation
Recommended measurements include supply and return temperatures, flow rate, pressure, product/room temperature, ambient/sink temperature and acoustic state. Cooling capacity can be calculated from mass flow and enthalpy/temperature change where measurement quality is sufficient.

## Load model
A cold room model should include wall conduction, infiltration, door openings, thermal bridges, product entry, lighting, fans and initial pull-down. The maintenance load after stabilization should be treated separately.

## Fault response
High source temperature, low flow, pressure abnormality, leak detection or loss of sink capacity should cause a controlled degradation or shutdown. The architecture should reject extreme input rather than attempt unlimited cooling extraction.

## 1500 °C event
A 1500 °C accidental liquid stream must be blocked from direct entry into the THERMA core. The upstream recovery exchanger/diverter must protect the core while allowing a qualified secondary loop to continue if safe.

## Evidence boundary
Published thermoacoustic refrigeration systems demonstrate the technology class. THERMA-specific cooling capacity, COP and pull-down time remain unvalidated until a physical prototype is measured.

## Design objective
The credible refrigeration milestone is a measured, stable 0–3 °C cold-side condition with a separately measured cooling capacity and input-energy accounting under clearly specified operating conditions.
