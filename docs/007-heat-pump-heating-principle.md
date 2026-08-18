# 007 — Thermoacoustic Heat-Pump Heating Principle

## Scope
This file documents the heating direction of THERMA and the conceptual 20 °C to 80 °C water case.

## Heat-pump concept
A heat pump uses supplied work to move heat from a lower-temperature source to a higher-temperature delivery side. In THERMA, the supplied work can be acoustic work generated or driven through a thermoacoustic architecture.

## Water interface
The user should normally interact with a secondary water loop. The pressurized acoustic gas remains inside its pressure boundary and exchanges energy through dedicated heat exchangers.

## 20 °C to 80 °C calculation
For 1 kg, approximately 1 L, of water, using cp ≈ 4.186 kJ/kg-K and ΔT = 60 K:

Q = m cp ΔT
Q = 1 × 4.186 × 60 kJ
Q ≈ 251.2 kJ
Q ≈ 69.8 Wh

This is a standard water-heating calculation. It does not depend on special THERMA physics.

## Historical screening assumption
An earlier project screening case assumed heating COP around 2.1. Under that assumption, work required for 69.8 Wh of hot-side delivery would be about 33.2 Wh, leaving approximately 36.6 Wh supplied by the low-temperature source.

## 1.6 L source-water ratio
If source water enters at 20 °C and is cooled to 0 °C, one litre releases approximately 23.3 Wh of sensible heat. Dividing 36.6 Wh by 23.3 Wh/L gives about 1.57 L, rounded to 1.6 L source water per litre of 80 °C delivery water.

This ratio is conditional on the historical COP assumption, source temperature drop and idealized transfer. It is not a universal THERMA property and is not a measured prototype result.

## Continuous flow interpretation
In a continuous-flow heat exchanger, one litre of 20 °C delivery water can remain approximately one litre after heating, provided the machine transfers the required energy. The required source-side flow depends on source temperature drop, actual COP, heat losses and flow design.

## Heat balance
The first-law heat-pump balance is:

QH = QC + W

where QH is hot-side delivery, QC is heat extracted from the source, and W is supplied work/acoustic energy as defined for the control volume.

## COP
Heating COP is:

COPH = QH / W

The actual THERMA COP must be measured or computed from a validated model under a defined temperature lift and load.

## Temperature lift
A 20 °C source to 80 °C delivery requires a 60 K lift. This is more demanding than 20 °C to 50 °C. The closer the required output temperature is to the practical limit of the heat pump, the more the achievable COP can fall.

## Source choices
Potential low-grade sources include river or ambient water, wastewater, district return water, geothermal water and industrial low-grade heat. The source temperature and flow determine available heat extraction.

## River-water example
A river at 20–30 °C can act as a low-temperature heat source in a heat-pump configuration. Calling this “free heat” is shorthand for low or zero fuel cost at the source; the system still requires acoustic/electrical work and must respect environmental and thermal-discharge constraints.

## Cooling the source
The source water gives up sensible heat if it is cooled across the source heat exchanger. A design that cools the source only slightly requires higher source-water flow than a design that allows a larger source temperature drop.

## House hot-water use
For a house or restaurant, a useful product is a hot-water loop with supply and return temperatures, not simply a single tank temperature. The system can modulate heat delivery according to flow, inlet temperature and demand.

## Restaurant and dairy applications
Restaurants and dairies may have steady hot-water or process-heat demand. Such applications can be attractive if a nearby low-grade source or recoverable heat is available and the required output temperature fits the machine's validated envelope.

## Control
The controller should select a valid operating state based on source temperature, delivery temperature, flow, pressure, sink conditions and acoustic state. It should protect the system when the requested temperature lift becomes infeasible.

## Reversible operation
The same physical core can be used within a controlled reversible architecture. Mode switching should pass through a neutral state with stabilized pressure and temperature conditions.

## Experimental milestone
A credible prototype test should specify inlet water temperature, outlet water temperature, water mass flow, source-side temperature/flow, supplied acoustic/electrical work and steady-state duration. From those measurements, QH, QC and COP can be computed.

## Failure modes
Potential failures include insufficient thermal lift, heat-exchanger approach collapse, acoustic instability, source freezing in very cold cases, control errors, pressure faults, leaks and high-source-temperature excursions.

## 1500 °C protection
A raw 1500 °C industrial stream is not a direct heat-pump input. An upstream high-temperature recovery exchanger and diverter must bring the secondary thermal interface into the qualified THERMA temperature range.

## Evidence boundary
Published thermoacoustic heat-pump demonstrations establish the category. They do not prove the historical COP of 2.1 for THERMA or the 1.6 L/L ratio.

## Design objective
The first physical heating demonstration should focus on a modest, well-instrumented hot-water flow and a source temperature that is safely within the validated prototype envelope. The purpose is to measure the real heat balance, not to force a target number.
