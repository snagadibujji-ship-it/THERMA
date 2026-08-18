# 011 — Rapid Cooling 3.3 and Transient Load Design

## Purpose
This document defines the engineering problem behind THERMA 3.3 rapid 0–3 C cooling and separates transient cooling capacity from steady-state efficiency.

## 1. Why 3.3 exists
The project recognized that a heat-driven thermal machine can reach an efficient steady state while still taking hours to cool a warm room or product load. Rapid cooling changes the dominant requirement from energy efficiency to transient power.

## 2. Temperature versus power
A cold-side target of 3 C is a temperature. It does not state how quickly the machine can remove heat. Cooling capacity is a rate, usually watts or kilowatts.

## 3. Basic load energy
For sensible cooling, Qload = m cp (Ti-Tf). This is the first number that must be calculated before claiming a pull-down time.

## 4. 500 kg example
For 500 kg water-equivalent product from 25 C to 3 C, sensible removal is about 12.8 kWh.

## 5. 15-minute requirement
If that 12.8 kWh must be removed in 15 minutes, the average cooling rate is roughly 51 kW before heat leakage and other losses.

## 6. 30 kg example
A 30 kg water-equivalent load requires about 0.77 kWh sensible removal for 25→3 C, making minutes-scale cooling more plausible with several-kilowatt rapid capacity.

## 7. 100 kg example
A 100 kg load requires about 2.56 kWh sensible removal. A few-kilowatt system could still require tens of minutes depending on the actual capacity.

## 8. Container thermal mass
The room structure, shelves, pipes and containers can absorb heat. The load model must include these masses if they are relevant to the application.

## 9. Air load
Cold-room air has lower thermal mass than product but can contribute through infiltration and door events.

## 10. Wall loss
Wall heat gain is driven by area, insulation conductance and temperature difference. It is usually a maintenance load rather than the dominant initial pull-down load.

## 11. Door opening
Door openings introduce warm air and moisture. Frequent events can produce significant transient duty.

## 12. Warm-product entry
Warm product can dominate when food or goods enter throughout the day. The control system should respond to scheduled or measured product entry.

## 13. Rapid module concept
3.3 explored multiple parallel thermoacoustic modules so transient cooling capacity could be accumulated without forcing a single core to operate far beyond its efficient point.

## 14. Parallelization
Parallel cores can share the same thermal loops if hydraulic and acoustic interfaces are engineered. Each core must be isolatable.

## 15. Staging
Staging can improve thermal matching by assigning modules to different temperature ranges. It adds complexity and should be justified with measurable benefit.

## 16. Thermal buffer
Hot thermal buffering can store the driving heat when waste heat is available. This can improve availability during source interruptions but adds thermal loss and capital cost.

## 17. Cold storage caution
Cold storage is also possible but not automatically superior because stored cold leaks to the environment. The buffer must be sized from the actual duty cycle.

## 18. Buffer sizing
Storage energy Ebuffer should be based on desired transient duration multiplied by required missing power, with allowed temperature excursion and thermal loss included.

## 19. Source limitation
If the waste-heat source cannot provide the required instantaneous power, the buffer or an additional source is needed. No control algorithm can create missing source energy.

## 20. Rejection limitation
Rapid cooling pushes more heat into the rejection system. If the rejection side cannot dispose of it, the cold-side capacity will fall or the machine will need to shut down.

## 21. Ambient limitation
Hot ambient conditions reduce the heat-rejection margin. A room that works at 30 C ambient may behave differently at 50 C ambient.

## 22. Thermal sink
A water-cooled rejector can provide stronger thermal rejection than air in some conditions, but it adds water use, pumping and treatment requirements.

## 23. Control challenge
Rapid cooling requires aggressive but bounded control. The system should command additional modules or flow while preserving pressure, temperature and acoustic safety margins.

## 24. Boost state
A THERMA boost state can temporarily enable additional fixed cores or thermal resources. It should have explicit entry, exit and fault conditions.

## 25. Load prediction
If product entry or occupancy is predictable, pre-cooling can reduce the instantaneous peak.

## 26. Pre-cooling
Waste heat can be used earlier to prepare thermal conditions. The goal is to move energy in time rather than pretend the core can suddenly multiply power.

## 27. Cold-start
A cold-start machine may need an initial thermal establishment period before the acoustic engine reaches useful output. That startup time must be included in realistic scheduling.

## 28. Rapid restart
After a stop, stored thermal gradients may remain or disappear depending on insulation and time. Restart performance should be measured rather than assumed.

## 29. Refrigeration cascade
Multiple fixed thermoacoustic stages can be used to improve temperature matching. Each additional stage adds interfaces and losses.

## 30. Temperature staging
A staged system can split a large temperature lift into smaller steps. This can improve thermodynamic matching but complicates control and hardware.

## 31. Product target
A rapid application must define product type, mass, initial temperature, target temperature, allowable gradient, allowable freeze damage, and maximum pull-down time.

## 32. Food safety
For food applications, thermal history can matter as much as final temperature. The control and logging system should preserve temperature history.

## 33. Cold-room sizing
Room volume alone is insufficient for design. Product load, door schedule, insulation, ambient temperature, internal heat and required recovery time are needed.

## 34. 1000 L screening case
The project's representative 1000 L cold room with 35–55 C ambient and approximately 25 C initial product was used as a framework, not a validated plant design.

## 35. Maintenance mode
After pull-down, the machine should reduce to the heat-leak load. A constant maximum-power assumption wastes source energy.

## 36. Cycling
Repeated rapid boosts can stress thermal interfaces and increase average auxiliary power. Duty cycle must be considered.

## 37. Acoustic stress
High acoustic amplitude can increase nonlinear losses and structural vibration. Rapid mode should remain inside the validated acoustic envelope.

## 38. Regenerator stress
Temperature and pressure cycling can affect the regenerator matrix. The rapid mode requires endurance testing at its actual duty profile.

## 39. Heat-exchanger stress
Fast thermal ramps can create thermal shock and fatigue. Exchanger flow and source ramps may need limits.

## 40. Sensor latency
Rapid control is only possible if sensors and DAQ respond quickly enough. Slow temperature sensors alone cannot control high-frequency acoustic dynamics.

## 41. Control hierarchy
Fast acoustic control should operate separately from slower thermal-loop control. A supervisory layer can coordinate both.

## 42. Failure response
If one module fails, the controller should isolate it and reduce the commanded target if the remaining capacity is insufficient.

## 43. Capacity reserve
A practical system should not run at the absolute limit continuously. Reserve capacity improves recovery from disturbances.

## 44. Scaling law
Adding modules can increase capacity, but hydraulic network losses, heat rejection, controls and manufacturing cost also grow. Simple multiplication is not a complete scale model.

## 45. Validation experiment
Prototype tests should measure pull-down time for defined masses and compare actual Qc(t) with the load model.

## 46. Acceptance criteria
A rapid-cooling prototype needs an explicit maximum pull-down time for defined load cases, plus pressure, temperature and stability limits.

## 47. Simulation audit
Any earlier claim of “15-minute cooling” must be tied to a stated load. The number is not universal for THERMA.

## 48. What 3.3 changed
3.3 shifted the project toward modular rapid capacity, transient buffering and load-aware control while keeping the no-moving-core thermoacoustic principle.

## 49. What 3.3 did not prove
It did not experimentally demonstrate a universal minutes-scale pull-down or prove a specific commercial cooling capacity. Those remain prototype measurements.

## 50. Closing principle
Rapid refrigeration is a power-density and transient-control problem. The right target is a measurable load case with a calculable heat-removal requirement, validated THERMA capacity, sufficient rejection and a controlled recovery path.
