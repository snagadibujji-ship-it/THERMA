# 009 — Architecture Overview

## 1. System boundary
THERMA 3.5 is organized as a fixed-hardware thermoacoustic core surrounded by conditioned thermal interfaces, secondary fluid loops, instrumentation, control and independent safety systems.

## 2. Primary path
The conceptual primary chain is:

source heat or acoustic work → thermal interface → thermoacoustic core → thermal interface → useful cooling/heating load.

## 3. Fixed core
The fixed core contains the hot heat exchanger, regenerator, acoustic resonator/impedance network, cold heat exchanger and pressurized working-gas domain. There is no reciprocating mechanical energy-conversion train.

## 4. Working gas
The working gas remains inside the pressure boundary. Helium is a recurring candidate in the project because of its known thermoacoustic properties, but the final gas remains a design variable until the exact geometry and conditions are validated.

## 5. Thermal interfaces
Hot and cold heat exchangers couple the acoustic gas to secondary fluids. This isolates the process water or industrial heat-transfer fluid from the working gas.

## 6. Secondary loops
Secondary loops can use pumps, valves, reservoirs and piping. These components may physically move fluid but are external balance-of-plant components; they are not the thermoacoustic core's mechanical energy converter.

## 7. Acoustic network
The acoustic network may contain resonator tubes, inertance, compliance, connections and matching elements. Exact topology is not frozen until a reproducible acoustic model is available.

## 8. Cooling architecture
Cooling uses a cold-side loop connected to the user load and a hot-side/rejection loop connected to the sink. The acoustic field provides the work required to move heat from cold to warm.

## 9. Heating architecture
Heating uses a lower-temperature source loop and a higher-temperature delivery loop. The acoustic field supplies the work required to lift heat toward the delivery side.

## 10. Reversal
The same fixed hardware may be routed into different operating states. The transition must use a neutral state and verify pressure, temperatures, flows and other conditions.

## 11. Control architecture
Sensors observe temperature, pressure, flow and acoustic state. The controller selects a valid operating state and may adjust pumps, valves, acoustic drive/routing and auxiliary equipment.

## 12. Safety architecture
Independent protection should include pressure relief, isolation, overtemperature shutdown/bypass, leak detection, controlled charging and emergency thermal diversion.

## 13. Source conditioning
Upstream thermal sources are conditioned before entering the core. This is especially important for industrial sources with spikes, corrosive fluids or very high temperatures.

## 14. 1500 °C scenario
A raw 1500 °C liquid or process stream must never be routed directly into the core. A high-temperature recovery exchanger and emergency diverter must protect the core.

## 15. Modularization
Parallel fixed cores can support part-load operation and fault tolerance. A failed module can be isolated while other modules operate at reduced capacity if the system is designed for that state.

## 16. Rapid mode
The 3.3 rapid-cooling concept separates steady thermal source production from high short-duration cooling power. It may require parallel modules, thermal buffering or another validated rapid-capacity mechanism.

## 17. Thermal rejection
Every mode eventually rejects heat to a sink. The final system must account for useful heat, rejected heat, auxiliary energy and parasitic losses.

## 18. Engineering metrics
Key metrics are cooling capacity, heating capacity, thermal input, acoustic/electrical work, COP with explicit convention, temperatures, flow rates, acoustic pressure, pressure, noise/vibration where applicable, safety margin, maintenance interval and cost.

## 19. Architecture validation
The architecture is only frozen for documentation purposes. Exact component dimensions remain open pending model validation. A generated image must not be used as evidence of a final fabrication geometry.

## 20. Architecture diagram

    ENERGY / HEAT SOURCE
             │
             ▼
      ┌──────────────┐
      │ SOURCE HX /  │
      │ CONDITIONER  │
      └──────┬───────┘
             │
             ▼
      ┌──────────────┐
      │    HOT HX    │
      └──────┬───────┘
             ▼
      ┌──────────────┐
      │ REGENERATOR  │
      └──────┬───────┘
             │
             ▼
      ┌────────────────────┐
      │ ACOUSTIC RESONATOR │
      │ + IMPEDANCE NETWORK│
      └────────┬───────────┘
               │
               ▼
      ┌──────────────┐
      │    COLD HX   │
      └──────┬───────┘
             │
             ▼
         COLD LOOP
             │
        ┌────┴────┐
        ▼         ▼
     COOLING    HEAT-PUMP
       LOAD       ROUTE

## 21. Main design rule
The architecture must remain a thermoacoustic system. A piston-based, Stirling-style or mechanical-compressor substitute must not be inserted merely to make a diagram look familiar.
