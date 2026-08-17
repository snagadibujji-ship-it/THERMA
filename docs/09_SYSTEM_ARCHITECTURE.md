# 09 — THERMA 3.5 System Architecture

## Architecture statement
THERMA 3.5 is a fixed-hardware thermoacoustic thermal platform. Its essential system is the controlled interaction of a working gas, acoustic geometry, thermal matrices, heat exchangers, pressure boundary, external thermal loops, instrumentation, control and safety layers.

## Primary blocks
1. Energy-source interface.
2. Source conditioning and emergency diversion.
3. Hot heat exchanger.
4. Regenerator/stack.
5. Acoustic resonator and impedance network.
6. Cold heat exchanger.
7. Heat-rejection exchanger.
8. Secondary fluid loops.
9. Sensors and DAQ.
10. Controller and independent safety layer.

## Text architecture

HEAT SOURCE
   |
   v
SOURCE CONDITIONER / RECOVERY HX
   |
   v
HOT HX ---> REGENERATOR ---> ACOUSTIC CORE / RESONATOR ---> COLD HX
   |                                                           |
   +-------------------- heat path ---------------------------+

The exact heat path depends on whether the unit is operated as a heat-driven engine/refrigerator configuration or as an externally driven heat pump.

## External interfaces
The user-facing interface is a secondary fluid loop. The acoustic working gas stays inside its pressure boundary. This separation allows the system to connect to hot water, chilled water, process fluids or other compatible loops without exposing the user fluid to the working gas.

## Modularity
Parallel fixed acoustic modules can support load following, redundancy and serviceability. A module may be isolated while others continue at reduced capacity, assuming the hydraulic and acoustic network is designed for that state.

## Fixed hardware
The architecture excludes piston trains, crankshafts, flywheels, reciprocating displacers and mechanical compressors in the thermoacoustic core. Pumps and valves may exist in external secondary loops; those are balance-of-plant components and not the acoustic core.

## Thermal routing
The system must keep source, sink and load temperatures within qualified ranges. Very hot sources should pass through a rated recovery interface. Cold-side delivery should be isolated from hot-side thermal paths with appropriate valves, bypasses and control states.

## Instrumentation
Minimum signals include hot temperature, cold temperature, sink temperature, pressure, flow and state. Development instrumentation should also capture acoustic pressure amplitude, frequency and phase.

## Safety separation
Software control is not the only safety barrier. Independent pressure relief, isolation and thermal trip functions must exist in the physical system.

## Architecture maturity
This is a conceptual architecture. Exact dimensions and power levels require a reproducible acoustic/thermal model and physical validation.
