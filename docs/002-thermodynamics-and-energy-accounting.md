# 002 — Thermodynamics and Energy Accounting

## 1. Purpose
This document establishes the thermodynamic accounting framework for GHIA THERMA. It is not a claim of validated THERMA performance.

## 2. First-law foundation
Every THERMA operating mode must satisfy conservation of energy. Heat and work can be transferred, converted, rejected, or stored; they are not created by the machine.

## 3. Sensible heating equation
For a fluid or product load undergoing a temperature change without phase change, the starting relation is Q = m cp DeltaT. Water near room temperature is commonly approximated with cp about 4.186 kJ/kg-K for screening calculations.

## 4. One-litre example
For approximately 1 kg of water heated from 20 C to 80 C, DeltaT is 60 K. Q is approximately 251.2 kJ, or 69.8 Wh. This calculation is independent of the THERMA concept.

## 5. Heating balance
For a heat pump, QH = QC + W. QH is useful heat delivered at the hot side, QC is heat extracted from the source side, and W is supplied work.

## 6. Cooling balance
For a refrigerator, the cold-side heat removal QC plus supplied work W appears as heat rejected at the warm side: QH = QC + W.

## 7. Cooling COP
When work input is the denominator, COPC = QC/W. A heat-driven architecture may instead be reported using cooling output per unit thermal driving heat, so the denominator definition must always be stated.

## 8. Heating COP
COPH = QH/W when W is the externally supplied work to the heat-pump process. For THERMA, the effective work may be acoustic work generated internally or supplied electrically for a development configuration.

## 9. Carnot ceiling
For a heat pump between absolute temperatures TC and TH, reversible heating COP is TH/(TH-TC). This is an upper bound, not a THERMA prediction.

## 10. Cooling Carnot ceiling
For a refrigerator, reversible COP is TC/(TH-TC), using absolute temperatures. Real thermoacoustic systems incur irreversible acoustic, thermal, viscous, streaming, heat-exchanger, and finite-temperature-difference losses.

## 11. Temperature lift
The temperature lift between source and delivery or cold load and sink strongly affects achievable COP. A smaller lift generally provides a more favorable reversible ceiling, but exchanger approach temperatures and practical losses remain important.

## 12. Heat-source interface
TH's heat-driven mode should treat the industrial source through a controlled secondary thermal interface. The interface limits the core temperature, stabilizes flow, and provides protection from extreme transients.

## 13. Heat rejection
Cooling systems must reject the sum of removed load heat and supplied work. A cold room is therefore not a heat sink; the rejected heat must reach ambient, a water loop, or another useful load.

## 14. Secondary thermal loops
A secondary water or thermal-fluid loop decouples the user-facing load from the sealed working gas. This supports cold rooms, hot-water systems, process loads, and district networks.

## 15. 20 C to 80 C source screening case
The historical screening case used 1 L of 20 C output water raised to 80 C. The required useful heat is about 69.8 Wh.

## 16. Historical COP assumption
A previous conversational model assumed COPH = 2.1. Under that assumption, W = 69.8/2.1 ≈ 33.2 Wh. The remaining approximately 36.6 Wh would be extracted from the lower-temperature source.

## 17. Historical 1.6 L ratio
If the source water is cooled from 20 C to 0 C, each litre can surrender approximately 23.3 Wh of sensible heat. 36.6/23.3 gives about 1.57 L, rounded to 1.6 L per litre of 80 C product water.

## 18. Conditional nature of that ratio
The 1.6 L/L value is not a THERMA material constant or experimental result. It changes with COP, source temperature drop, target temperature, heat losses, auxiliary loads, and actual heat-exchanger behavior.

## 19. Rapid cooling energy
For a load of mass m cooled from Ti to Tf, Qload ≈ m cp (Ti-Tf) before phase-change, heat-leak and container corrections.

## 20. 500 kg rapid example
The v1 dossier uses 500 kg water-equivalent product from 25 C to 3 C. Sensible energy removal is about 12.8 kWh. To achieve this in 15 minutes, the average cold-side capacity must be roughly 51 kW before losses.

## 21. Pull-down versus maintenance
Initial pull-down is often much larger than steady maintenance. Once a cold room is at setpoint, THERMA primarily offsets wall conduction, infiltration, door events, product ingress, internal electrical loads and other gains.

## 22. Maintenance-load model
A simple steady model can approximate Qmaintenance as wall loss + infiltration + internal load + product ingress. The machine should be sized from the peak and transient requirements, not from maintenance load alone.

## 23. Heat exchanger approach temperatures
A heat exchanger cannot generally transfer heat at zero temperature difference. Finite approach temperatures reduce the useful temperature span available to the acoustic core and affect system COP.

## 24. Acoustic losses
Useful acoustic power is lower than ideal wave energy because of viscous losses, thermal boundary-layer effects, impedance mismatch, leakage, acoustic streaming, and nonlinear effects.

## 25. Regenerator losses
The regenerator must provide thermal storage and exchange without creating unacceptable pressure drop or axial thermal conduction that shorts the desired gradient.

## 26. Gedeon and mean streaming
Thermoacoustic loops can exhibit mean mass flow that transports heat parasitically. THERMA design analysis must account for this rather than assuming purely oscillatory zero-mean behavior.

## 27. Energy-routing concept
In heat-driven cooling mode, useful thermal input creates acoustic work, and the acoustic network supplies refrigeration work. In heating mode, supplied acoustic work moves additional heat from a lower-temperature source to the hot side.

## 28. Reversible neutral state
When switching modes, the machine should not be treated as an instantaneous sign change. Acoustic amplitude, pressure, and thermal routing need controlled transition through a neutral verified state.

## 29. Source temperature does not map linearly to cooling
Higher heat-source temperature can increase available thermodynamic driving force, but the final cooling capacity depends on acoustic impedance, exchanger effectiveness, regenerator performance, heat sink, and losses.

## 30. 60 C challenge
A 60 C source against a 35 C sink has only about 25 K gross difference before heat-exchanger approaches and other irreversibilities. This makes low-grade operation sensitive to every loss mechanism.

## 31. 80–120 C development window
The historical project selected approximately 80–120 C as a more practical initial industrial-development range because it offers a larger thermal head than the lowest-temperature branch while remaining more accessible than very high-temperature systems.

## 32. 120–200 C range
Higher-temperature sources may be attractive for heat recovery, but material compatibility, thermal shock, pressure-vessel design, heat-exchanger life, and safe source conditioning become more demanding.

## 33. Extreme 1500 C event
A raw 1500 C industrial fluid must not directly enter the core. It should be isolated or diverted, and a dedicated high-temperature recovery stage should condition the energy before it reaches the controlled THERMA thermal interface.

## 34. Source-flow accounting
Thermal power from a moving source stream can be estimated from m_dot cp DeltaT. The source-side temperature drop must therefore be coupled to flow rate; a temperature alone does not specify available thermal power.

## 35. Hot-water output power
For a hot-water loop, QdotH = m_dot cp DeltaT. A 1 L static example only describes energy per litre and does not define a practical flow rate.

## 36. Cooling water output
The cold-loop duty similarly depends on mass flow and temperature rise across the load-side exchanger. Output temperature and cooling capacity are separate engineering quantities.

## 37. Auxiliary power
Pumps, fans, controls, sensor electronics, actuators, data acquisition, and heat-rejection devices consume power. A complete system COP must state whether these auxiliaries are included.

## 38. Thermal-input accounting
For heat-driven operation, thermal input should be integrated from source flow and temperature, not inferred from a source temperature label alone.

## 39. Annual energy
For a steady or scheduled load, Eyear = integral P(t) dt. A one-year model should account for seasonality, outages, maintenance, degradation, and source availability.

## 40. Economic energy boundary
The economic comparison must use the same system boundary for THERMA and the reference system. Comparing THERMA process heat alone against a compressor's whole electrical consumption is not meaningful unless all auxiliary loads and rejected heat are treated consistently.

## 41. Waste-heat marginal cost
Industrial waste heat can have low marginal fuel cost if it would otherwise be rejected. Its economic value still includes recovery heat exchangers, piping, controls, maintenance, and opportunity cost.

## 42. Electrical heating as input
Using electricity to produce heat and then using that heat to drive refrigeration is generally less attractive than direct electric compression. It may only be justified where a co-product or unusual system constraint adds value.

## 43. Fuel-generated heat
LPG, natural gas, diesel, biomass, and other fuels are upstream heat sources. THERMA should see a controlled thermal interface rather than direct combustion products unless a specifically qualified exchanger arrangement is engineered.

## 44. Heat-source diversity
Potential sources include industrial exhaust recovery, hot water, steam/condensate, solar thermal, engine waste heat, biomass, geothermal water, wastewater, and other hybrid sources.

## 45. River or ambient water in heating mode
A 20–30 C water body can serve as a low-temperature heat source for a heat-pump configuration. It is not an unlimited free-energy source; the source water gives up some sensible heat while THERMA supplies work.

## 46. Environmental balance
THERMA does not erase heat. The value proposition is avoiding additional electricity or fuel production by reusing thermal energy that would otherwise be rejected, where the total system is energetically and economically favorable.

## 47. Final accounting rule
Every simulation result in the repository must show: source temperature, sink temperature, target temperature, input thermal power, acoustic/electrical work, output thermal power, duration, COP definition, auxiliary power, and model fidelity.

## 48. What remains unproven
No equation in this document establishes a measured THERMA COP, cooling capacity, acoustic power density, pressure integrity, lifetime, leak rate, or commercial cost. Those require exact-geometry simulation and hardware validation.

## 49. Prototype role
The first prototype exists to establish those missing terms experimentally. The preferred strategy is single-core, heavily instrumented, with a narrow operating point selected for a favorable heat source.

## 50. Closing statement
THERMA's thermodynamic proposition is therefore well-defined but not yet experimentally quantified: use a suitable thermal gradient to produce acoustic work for refrigeration, or use acoustic work to pump heat toward a higher-temperature load. The engineering task is to convert that physically established principle into a specific, reproducible, safe and economically defensible implementation.
