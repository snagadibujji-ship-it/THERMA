# 06 — Thermoacoustic Refrigeration Mode

## Functional objective
THERMA's refrigeration mode is intended to move heat out of a cold load using thermoacoustic acoustic work. The user-side output is a cold secondary-fluid loop that can serve a refrigerated enclosure, storage system, process load or other suitable thermal sink.

## Target temperature
The project has consistently used **0–3 °C** as the principal cooling target. This is a temperature target, not a power claim. Cooling capacity must be reported as a rate of heat removal.

## Thermal path
The simplified path is:

cold load → cold-side secondary loop → cold heat exchanger → thermoacoustic refrigerator → warm-side heat rejection loop.

The acoustic process moves thermal energy against the natural temperature gradient while the system ultimately rejects the absorbed heat plus input work to the warmer side.

## Pull-down versus maintenance
A cold room has two very different workloads. Initial pull-down of warm product can require many kilowatts of cooling, while steady maintenance may require only enough cooling to offset wall conduction, infiltration, door events, fan heat and other leakage.

## Rapid cooling
The 3.3 work established that minutes-scale cooling is an instantaneous-power problem. For a 500 kg water-equivalent load cooling from 25 °C to 3 °C, the sensible energy alone is about 12.8 kWh. A 15-minute pull-down would therefore require roughly 51 kW average cooling before losses.

## Why modularity matters
A fixed-core thermoacoustic architecture can be divided into parallel modules. This allows different operating states and provides partial capacity if one module is unavailable. The architecture should not assume that a single tiny core can deliver arbitrary rapid cooling.

## Heat rejection
Refrigeration does not eliminate heat. The load heat, acoustic input and system losses must ultimately be rejected through a hot-side heat exchanger and suitable sink. Heat rejection capacity must therefore be included in the design from the beginning.

## Cooling COP
COP conventions must be stated carefully. For work-driven refrigeration, COPC = QC/W. For heat-driven refrigeration, cooling may instead be reported relative to thermal driving input. Results using different denominators are not directly comparable.

## Control variables
Important signals include load temperature, cold-loop flow, hot-side temperature, source temperature, acoustic amplitude, mean pressure, frequency and pressure safety state.

## Prototype acceptance
A refrigeration prototype must demonstrate measured cold-side capacity, source heat input, hot-side rejection, water-loop flow and temperature measurements, and an uncertainty budget. Reaching 3 °C by itself does not prove a useful refrigerator unless the heat-removal rate and energy input are also known.
