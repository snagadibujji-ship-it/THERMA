# 005 — Heat-Engine Principle

## Purpose
This file explains the heat-driven thermoacoustic engine portion of THERMA.

## Fundamental chain
The core heat-engine concept is a thermal-gradient-to-acoustic-power conversion process. A suitable hot-side and cold-side temperature difference is imposed across an appropriate thermoacoustic regenerator/stack. The oscillating working gas interacts with the solid matrix, and the correct phase relationship can cause acoustic amplification.

## Source heat
The source may be industrial waste heat, solar thermal heat, hot water, steam/condensate through a rated interface, or another suitable thermal resource. The source is not assumed to contact the acoustic gas directly. A conditioned secondary loop is preferred for temperature control and protection.

## Hot heat exchanger
The hot heat exchanger transfers energy from the conditioned source to the thermoacoustic core. Its role is not simply to be hot; it must transfer the required oscillatory heat flux while controlling pressure drop, thermal shock and material temperature.

## Regenerator
The regenerator provides the cyclic gas-solid thermal interaction required for thermoacoustic amplification. Its geometry must balance thermal coupling against acoustic losses and unwanted conduction.

## Acoustic generation
When the imposed temperature gradient and operating conditions exceed the required onset condition, the thermoacoustic process can sustain or amplify an acoustic field. The generated acoustic power is the useful mechanical/acoustic output of the engine stage.

## Acoustic routing
The generated acoustic power can be routed to a refrigeration section or another compatible acoustic load. Exact power transfer depends on impedance matching and losses in the acoustic path.

## Energy conservation
Heat is not converted with perfect efficiency. Some input energy is rejected, some becomes useful acoustic power, and some is dissipated through viscous, thermal, streaming and structural losses.

## Basic conceptual balance
A simplified engine statement is:

Q_in = W_acoustic + Q_rejected + Q_losses

The exact accounting should be based on measured or modeled energy flows for a specified control volume.

## Temperature gradient
A larger useful source-to-sink temperature difference can increase the available thermodynamic driving potential, but higher source temperature can also increase material and heat-exchanger challenges. Temperature alone is therefore not a sufficient performance predictor.

## Source-temperature sensitivity
The project explored 60–80 °C, 80–120 °C and 120–200 °C bands. The 80–120 °C region was treated as a more favorable initial industrial development range because low-grade operation becomes increasingly sensitive to losses.

## Heat sink
The cold-side or ambient sink is critical. A 60 °C source paired with a 35 °C sink has only a 25 K difference before heat-exchanger approach temperatures and other losses. Identical source temperatures may therefore produce different results in different climates.

## Onset
Thermoacoustic onset means the conditions at which sustained acoustic operation begins. Onset is not the same as useful refrigeration capacity. A system can oscillate acoustically and still deliver inadequate net thermal power.

## Saturation
Increasing heat input indefinitely does not guarantee proportional acoustic output. Nonlinear saturation, increasing losses, streaming and heat-exchanger limitations can reduce the incremental benefit.

## Multiple cores
The architecture may use multiple fixed acoustic modules in parallel or series. Parallel modules can support part-load control and fault tolerance. Series/staged arrangements can increase thermal utilization but complicate impedance matching and control.

## Modularity
A modular design means a failed or degraded core can be isolated while other modules continue at reduced capacity. This is a system-level reliability strategy, not evidence of physical performance.

## Safety
The engine must have independent pressure protection, overtemperature detection, source diversion and a qualified thermal interface. A controller must not be the sole protective layer.

## 1500 °C event
A raw 1500 °C liquid must not enter the THERMA core. If an industrial process can accidentally produce such a stream, a rated high-temperature recovery exchanger and emergency diverter must isolate the core from the event.

## Heat rejection
The engine and refrigeration combination eventually rejects heat to a sink. Waste heat used for useful service can reduce the amount of heat discharged directly, but the total energy balance remains conserved.

## Measurement plan
Prototype engine testing should measure hot-source temperature and flow, heat-sink temperature and flow, acoustic pressure amplitude, frequency, phase, mean gas pressure, gas inventory, and net acoustic power where possible.

## Evidence boundary
Published thermoacoustic engines demonstrate that the physical conversion class is real. They do not validate THERMA's exact geometry, power density, COP, cost or service life.

## Engineering conclusion
The heat engine is the upstream power source for heat-driven THERMA cooling. Its design target is not a generic “more heat equals more cooling” rule, but a stable, efficiently coupled acoustic power source with a measurable thermal-to-acoustic conversion efficiency.
