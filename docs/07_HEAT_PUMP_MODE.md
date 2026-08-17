# 07 — Heat-Pump Heating Mode

## Purpose
THERMA 3.5 can be routed as a heat pump in which acoustic work drives the movement of heat from a lower-temperature source to a higher-temperature delivery loop. The user-facing product can therefore be useful for hot water or process heat rather than only refrigeration.

## Source and delivery loops
A low-temperature source loop can be water, wastewater, geothermal water, river water or another compatible fluid. A separate delivery loop carries useful heat to a house, restaurant, hospital, industrial process or hot-water tank.

## 20 °C to 80 °C case
The project has used 20 °C source water and 80 °C delivery water as a conceptual target. Heating 1 L of water through that range requires approximately 69.8 Wh of sensible heat. The system must supply this heat at a rate determined by the desired hot-water flow.

## Energy balance
For a heat pump:

Q_H = Q_C + W

COP_H = Q_H / W

where Q_C is heat extracted from the low-temperature source, W is the supplied work, and Q_H is useful hot-side heat.

## River or ambient-water source
A river around 20–30 °C can serve as a source of low-grade thermal energy in a heat-pump configuration. The heat is not 'free' in the thermodynamic sense because work is still required to lift it to a higher temperature, and the source water experiences a thermal change.

## Historical 1.6 L/L calculation
Under the historical screening assumption COP_H≈2.1 and a source-water drop from 20 °C to 0 °C, the model produced about 1.6 L of source water per 1 L of 80 °C product water. This is conditional on the assumed COP and temperature drop, not a universal THERMA property.

## Flow-rate example
If the hot-water side needs 10 L/min from 20 °C to 80 °C, the sensible heating demand is approximately 10 × 69.8 Wh per minute, or about 41.9 kW. Real input requirements are higher according to the actual COP and heat losses.

## Practical controls
The controller must prevent unstable operation as source temperature, delivery temperature or flow changes. Hot-side and source-side temperature, flow, pressure, acoustic amplitude and system state should be monitored continuously during development.

## Prototype proof
A heating prototype must measure source heat extraction, hot-side delivery, acoustic/electrical work, flow rates, temperatures and COP under defined steady-state conditions. A single hot-water outlet temperature is insufficient evidence of system performance.
