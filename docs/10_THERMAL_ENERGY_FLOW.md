# 10 — Thermal Energy Flow and System Balances

## Purpose
Track where thermal energy enters, where acoustic work is generated or supplied, where useful heat is removed or delivered, and where final rejection occurs.

## Cooling chain
For heat-driven cooling, the conceptual chain is:

heat input → thermoacoustic engine action → acoustic power → refrigeration action → cold-side heat removal → warm-side rejection.

The cooling load receives useful removal QC. The final rejection side must dispose of QC plus the energy introduced into the refrigeration process.

## Heating chain
For heat-pump heating:

low-temperature source → heat-pump action → high-temperature delivery loop.

The hot-side output QH satisfies QH = QC + W for a work-driven heat pump.

## Sensible water heating
For one litre of water, approximate mass is one kilogram. Using cp≈4.186 kJ/kg-K:

Q = m cp ΔT.

For 20→80 °C:
Q≈251.2 kJ≈69.8 Wh.

## Energy bookkeeping
Every model run should track:
- source thermal input;
- acoustic work or electrical driver work;
- cold-side heat extraction QC;
- hot-side heat delivery QH;
- rejected heat;
- auxiliary pumps/fans/electronics;
- thermal losses;
- parasitic acoustic losses.

## Why single COP values are dangerous
The project history included different COP conventions. A heat-driven system may report cooling per thermal driving heat, while a compressor system normally reports cooling per electrical input. These are not interchangeable.

## Temperature versus power
A cold-side target such as 3 °C says nothing about capacity. The rate of heat removal is needed to size a cold room. Similarly, an 80 °C hot-water outlet temperature says nothing about useful hot-water flow without a heat-rate value.

## Diagram

      SOURCE HEAT
          │
          ▼
   THERMOACOUSTIC ENGINE
          │ acoustic power
          ▼
    REFRIGERATION CORE
       │           │
       │ Qc        │ rejection
       ▼           ▼
   COLD LOAD    HEAT SINK

      OR REVERSED

 LOW-T SOURCE ─► HEAT PUMP ─► HOT WATER
       QC              + W          QH

## Model outputs
A useful simulation report should include instantaneous and time-integrated energy, not only temperatures. Daily and annual simulations should integrate power over time and add source outages, maintenance, ambient variation and load variability.

## Prototype requirement
Instrumented physical tests must close the energy balance within a defined uncertainty before performance claims are accepted. A large unexplained residual is a measurement or model problem, not a reason to tune the model until it disappears.
