# 05 — Heat-Engine Mode

## Function
The heat-engine side of THERMA is intended to use an imposed thermal gradient to generate acoustic power. The heat source does not directly refrigerate the load; it first establishes the conditions for thermoacoustic power generation.

## Energy chain

heat source → conditioned thermal loop → hot heat exchanger → regenerator/stack → acoustic field → acoustic routing → refrigeration section

The architecture is therefore a conversion chain rather than a single heat exchanger.

## Thermal gradient
A useful gradient must exist across the thermoacoustic active region. The source temperature alone is insufficient because the achievable gradient depends on ambient/sink temperature, heat-exchanger approach temperatures, losses and thermal conduction through the structure.

## Acoustic generation
The thermal gradient interacts with gas motion and gas-solid heat transfer to amplify a compatible acoustic mode. The generated acoustic field has pressure and particle-velocity components whose phase determines how much useful acoustic power is available.

## Impedance matching
The acoustic engine must be matched to the downstream load. If the refrigeration section, resonator and engine sections have incompatible acoustic impedance, a large thermal input may not translate into useful delivered acoustic power.

## Saturation and losses
Increasing thermal input indefinitely does not guarantee proportional refrigeration. Nonlinear saturation, streaming, regenerator losses, heat-exchanger limitations, structural thermal leakage and acoustic dissipation can reduce marginal output.

## Heat-driven refrigeration implication
The likely best use case is a hot source whose heat would otherwise be rejected. A controlled secondary loop should prevent raw plant exhaust or extreme-temperature fluid from reaching the thermoacoustic core.

## 1500 °C event
A raw 1500 °C stream must never be routed directly to the core. It must pass through a rated high-temperature recovery exchanger and/or emergency diverter so that the core sees only a qualified secondary-loop temperature.

## Control variables
The engine mode must observe at least source temperature, source-side flow, sink temperature, acoustic pressure, mean pressure, frequency and system state. Additional variables may be required after exact geometry is selected.

## Prototype measurement
The proof-of-physics prototype should measure thermal input, acoustic amplitude, frequency, phase, pressure, source/sink temperatures and useful cooling/heating output. These measurements establish whether the modeled conversion chain actually works as predicted.

## Boundary of claim
A heat-driven thermoacoustic engine is an established technology category. THERMA-specific thermal-to-acoustic efficiency and power density remain prototype measurements, not established facts.
