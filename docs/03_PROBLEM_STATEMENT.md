# 03 — Problem Statement and Engineering Motivation

## Core problem
Industrial sites can reject substantial heat while cooling loads simultaneously require energy. The project question is whether a useful fraction of a suitable thermal gradient can be converted through thermoacoustic processes into acoustic work and then useful refrigeration.

## Reverse problem
A similar fixed thermoacoustic platform can be used in heat-pump mode, where acoustic work moves heat from a lower-temperature source toward a higher-temperature delivery loop.

## Practical constraints
The problem is not merely achieving a temperature target. The system must balance:
- cooling/heating capacity;
- source and sink temperatures;
- heat-exchanger approach temperatures;
- acoustic power density;
- regenerator losses;
- streaming and nonlinear losses;
- pressure boundary requirements;
- leakage and thermal cycling;
- control stability;
- serviceability;
- capital and operating cost.

## Why 0–3 °C matters
The project repeatedly uses 0–3 °C as a refrigeration target for chilled products and cold-storage applications. A temperature target is not a cooling-capacity claim. The engineering model must independently calculate the rate of heat removal.

## Why 20–80 °C matters
The heating research uses 20 °C source water to 80 °C delivery water as a conceptual case. One litre of water requires approximately 69.8 Wh of sensible heat for that change, independent of the special THERMA physics.

## Product-level question
The commercial question is whether the THERMA architecture can provide a meaningful advantage over mature compressor, absorption, adsorption, and industrial heat-pump systems. The likely strongest early niche is a site with abundant low-marginal-cost waste heat and a nearby cooling demand.

## Engineering thesis
A credible development path is:

problem → physical model → exact geometry → component models → coupled model → adversarial analysis → prototype → measurement → model correction → next prototype.

The project is strongest when the model is predictive and falsifiable rather than when it simply produces green status tables.
