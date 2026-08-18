# 002 — Evidence Hierarchy and Source Discipline

## Purpose
This file defines the rules used to distinguish what is known, calculated, hypothesized, simulated, or only measurable by hardware.

## Evidence Level A — Established external evidence
Level A includes published thermoacoustic physics, documented experimental systems, recognized engineering methods, standards, and prior-art documents. A Level A result demonstrates that a class of phenomenon or component has precedent; it does not automatically prove THERMA's implementation.

## Evidence Level B — First-principles calculation
Level B contains calculations derived from stated equations and assumptions. Examples include sensible water-heating energy, energy conservation, Carnot ceilings, and basic heat-load calculations. A calculation can be exact relative to its assumptions while still not predicting a real prototype.

## Evidence Level C — THERMA model
Level C includes screening-model results, design targets, architecture comparisons, assumed COP values, Monte Carlo scenario outputs, lifecycle projections and economic screens. These values are useful for selecting experiments and architectures but remain unvalidated until hardware correlation.

## Evidence Level D — Hardware evidence
Level D requires measured data from a physical THERMA test article with traceable instrumentation, calibration, operating conditions, uncertainty estimates and repeatability. Examples include actual COP, acoustic pressure amplitude, leakage, fatigue, heat-exchanger effectiveness and endurance.

## Reporting rule
Every major result should identify its evidence level. Any unreferenced number is not to be described as a measured THERMA result.

## COP discipline
Thermal-input COP, work-input COP, heating COP and cooling COP are not interchangeable. Every COP value must specify numerator, denominator, temperature conditions and duration.

## Simulation-count discipline
A 1-million or 10-million-case Monte Carlo campaign is a scenario count, not evidence equivalent to one million or ten million independent CFD experiments. Results depend on the distributions and reduced-order model used.

## Geometry discipline
A generated image can illustrate a geometry but cannot validate it. Exact resonator length, cross-sectional area, regenerator geometry, heat-exchanger dimensions, pressure vessel thickness and acoustic impedance must be derived from a reproducible model and checked experimentally.

## Materials discipline
A candidate material name is not a certification. Final grade, processing route, weld procedure, surface condition, fatigue behavior, compatibility and inspection route must be specified for hardware.

## Environmental discipline
Claims about avoided CO2 or global temperature cannot be inferred from local thermal simulations. Such claims require a complete energy-system and emissions model.

## Business discipline
Simulation economics are screens. Real commercial cost requires quotations, fabrication yield, installation, maintenance, energy tariffs, useful-heat valuation and field performance.

## IP discipline
Project chronology helps document development but does not itself establish patent rights. Prior-art analysis and legal claim mapping are separate evidence tasks.

## Adversarial rule
A green result is not automatically a good result if the model is incomplete. The objective is to expose wrong assumptions and quantify uncertainty.

## Regression rule
When a model or architecture changes, previous passing cases must be rerun under the new version. A result is not considered stable merely because a new run is green.

## Uncertainty rule
If data are missing, report the uncertainty. Do not tune a parameter only to make the result pass.

## Prototype correlation rule
The strongest validation pathway is: reproducible model → calibrated instrumentation → prototype measurement → model comparison → error analysis → redesign → repeat.

## Source traceability
Published sources, calculations and THERMA-derived results should be stored separately and linked from the relevant documentation file. Every major claim should be reproducible from its source, equation or dataset.
