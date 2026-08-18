# 008 — Thermal Loops, Cooling, Heating and Reversibility

## Purpose
This document defines the external thermal circuits that connect THERMA's fixed thermoacoustic core to practical cooling and heating loads.

## 1. Why secondary loops exist
The pressurized acoustic gas should not directly circulate through user equipment. A secondary loop provides a controlled thermal interface using water or another suitable fluid.

## 2. Cooling loop
The cooling loop transports heat from the load to the THERMA cold exchanger. Its flow rate, inlet temperature, outlet temperature and pressure drop determine delivered cooling power.

## 3. Heating loop
The heating loop transports useful heat from the hot exchanger to domestic, commercial or industrial loads. It can supply a hot-water tank, process stream or distribution loop.

## 4. Flow equation
Thermal power in a fluid loop can be estimated from Qdot = m_dot cp DeltaT. Flow measurement and temperature measurement are therefore foundational instrumentation.

## 5. Reservoir role
A reservoir can decouple flow dynamics and provide thermal buffering. It does not create free cooling; heat stored in a reservoir can leak to ambient over time.

## 6. Pump role
Pumps provide circulation in external loops. Their electrical power must be included in system energy accounting and operating cost.

## 7. Valve role
Valves can isolate, bypass, mix, regulate or reverse flow. A mode-switching architecture must use defined valve states and transition sequences.

## 8. Filter role
Filters protect heat exchangers and pumps from contamination. Filter pressure drop must be included in the loop model.

## 9. Expansion control
Water and thermal fluids expand with temperature. Expansion volume and pressure control need to be sized for the chosen loop.

## 10. Insulation
Insulation reduces unwanted thermal leakage from hot and cold pipes. Its performance depends on material, thickness, ambient conditions and moisture.

## 11. Cold-room interface
A cold room can exchange heat through an air cooler, liquid loop, cold plate or another product interface. The room load must include walls, infiltration and product entry.

## 12. 0–3 C objective
The project uses 0–3 C as a cold-side target for selected applications. The exact load temperature and allowable swing should be specified for the actual application.

## 13. Pull-down
Rapid pull-down requires sufficient instantaneous cooling capacity. The room's thermal mass is usually much greater during startup than during steady maintenance.

## 14. Maintenance load
Once the room reaches setpoint, the steady thermal demand can fall substantially. A correctly sized control system should reduce THERMA output rather than operate at maximum continuously.

## 15. Door events
Door openings introduce warm air and moisture. The daily load model should include frequency, duration and ambient conditions.

## 16. Warm product entry
Product entering above setpoint can dominate the cooling requirement. The correct capacity should be derived from product mass, specific heat, target temperature and entry schedule.

## 17. Internal electrical loads
Fans, lights, pumps and controls inside the cold enclosure eventually become heat load. The model should include their electrical power.

## 18. Thermal bridges
Structural penetrations and pipe supports can conduct heat into a cold room. They are small individually but important in high-performance insulation systems.

## 19. Heating load
A hot-water system has its own demand profile: occupancy, process batch size, tank losses, pipe losses and delivery temperature.

## 20. 20 to 80 C case
The conceptual case heats water from 20 C to 80 C. The standard sensible heat requirement is about 69.8 Wh per litre.

## 21. Flow rate example
At 1 L/min, 20 to 80 C requires approximately 69.8 Wh/min, or 4.19 kW of useful heating. The actual source and work inputs are higher because COP is finite.

## 22. Continuous heating
For continuous loads, storage may be unnecessary if the heat source and THERMA output can follow demand. For intermittent loads, storage can improve utilization.

## 23. Domestic use
Domestic hot water requires temperature control, scald protection, hygiene and local plumbing compliance. THERMA output should interface with a conventional hot-water safety architecture.

## 24. Restaurant use
Restaurants can have simultaneous hot-water and refrigeration loads. A reversible or multi-module platform could potentially allocate thermal resources according to demand.

## 25. Dairy use
Dairy applications may have both refrigeration and warm/process-water requirements. Hygiene and cleaning cycles become additional thermal loads.

## 26. Industrial process heat
Industrial users may need specific temperatures and stable flow. A controlled secondary loop can provide these without exposing process water to the acoustic gas.

## 27. Heat source diversity
The source loop may be supplied by industrial waste heat, solar thermal, hot process water, engine heat, steam-condensate recovery or other suitable thermal resources.

## 28. Source conditioning
Source-conditioning heat exchangers and buffers protect THERMA from temperature spikes and unstable supply.

## 29. 60 C source
At 60 C, the usable gradient may be small depending on the sink. The control system should reduce demand or move to another mode when the source cannot sustain the required gradient.

## 30. 80 to 120 C source
This range is the historical preferred development region because it offers a more comfortable thermal head than very low-grade heat while remaining less demanding than extreme high-temperature operation.

## 31. 120 to 200 C source
High-temperature recovery can support larger gradients but increases material, exchanger and safety requirements.

## 32. 1500 C source
A raw 1500 C liquid must never directly enter THERMA. The source must be diverted or processed through a qualified high-temperature recovery system.

## 33. Cooling-mode thermal path
In cooling mode, thermal source input creates acoustic work; the refrigeration section removes heat from the cold loop; the rejection loop carries total rejected heat to the sink.

## 34. Heating-mode thermal path
In heating mode, acoustic work moves heat from the low-temperature source to the hot loop. The hot output includes heat extracted plus supplied work.

## 35. Reversible routing
The platform can conceptually route the acoustic and thermal interfaces toward cooling or heating. The actual switching method must be chosen and validated for the exact geometry.

## 36. Neutral state
A neutral state reduces acoustic amplitude and stabilizes pressure/temperature before a new routing state is enabled.

## 37. Control states
Useful states include normal, economy, boost, degraded, neutral/transition, and safe shutdown. Each state should have entry conditions and exit conditions.

## 38. Load following
The controller can reduce acoustic activity or thermal flow when load falls. This avoids unnecessary source consumption and auxiliary power.

## 39. Source following
If waste-heat availability falls, THERMA should derate rather than pretending the same cooling output remains available.

## 40. Sink following
Ambient temperature and cooling-water temperature influence the rejection-side capacity. Hot ambient conditions can force derating even when the source temperature is unchanged.

## 41. Thermal storage
Hot storage can shift heat-driven operation away from the exact time of waste-heat availability. Cold storage can support short high-demand periods but incurs thermal leakage.

## 42. Buffer sizing
Buffer size should be based on the mismatch between source availability and load demand, including allowable temperature swing and maximum charging/discharging power.

## 43. Network loops
A factory-to-community concept can distribute hot water to local THERMA nodes. The network should keep pressure, temperature and contamination boundaries controlled.

## 44. Pipe losses
Pipe heat loss scales with temperature difference, insulation, surface area and distance. Pumping energy also increases with distance and pressure drop.

## 45. Return loop
A two-pipe supply/return network allows controlled recirculation. Return temperature affects the source-side thermal head and should be part of the control model.

## 46. Fault isolation
Each local node should be isolatable so a failed module does not disable the entire thermal network.

## 47. Water quality
Hardness, corrosion, dissolved gases and biological growth affect heat exchangers and pumps. Water treatment may be needed depending on the application.

## 48. Condensation
Cold loop surfaces below dew point can condense moisture. Insulation, vapor barriers and drainage are required.

## 49. Practical integration
THERMA should be presented as a thermal platform that interfaces with conventional pumps, valves, tanks, heat exchangers and building/process equipment. Its differentiating conversion core is thermoacoustic, not every surrounding component.

## 50. Closing principle
The practical product is the complete thermal system: fixed thermoacoustic core plus controlled secondary loops, measured thermal interfaces, control, safety and heat rejection. A useful outlet temperature without capacity, flow, stability and operating cost is not a complete engineering result.
