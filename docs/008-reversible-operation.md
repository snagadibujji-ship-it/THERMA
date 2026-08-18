# 008 — Reversible Operation

## Objective
THERMA 3.5 is intended as a reversible thermal platform that can support refrigeration and heating using the same fixed thermoacoustic hardware family.

## Cooling direction
In cooling operation, a suitable thermal gradient can generate acoustic power through the heat-engine side, and that acoustic energy is routed to a refrigeration section that removes heat from a cold-side loop.

## Heating direction
In heat-pump operation, acoustic work drives heat transport from a lower-temperature source to a higher-temperature delivery loop. The user-side interface remains a secondary fluid system.

## Why reversibility matters
A reversible platform could adapt to seasonal or site-specific demand. A facility with waste heat and a cooling requirement may use engine-driven refrigeration; a facility with a low-grade source and hot-water demand may use heat-pump operation.

## Fixed hardware requirement
Reversal does not require adding a piston, crankshaft, flywheel or mechanical compressor to the core. The intended mechanism is acoustic-field and thermal-interface routing within fixed geometry.

## Neutral transition
A robust transition should not switch instantly from one mode to another. The preferred sequence is: reduce acoustic excitation or generation, reduce load, isolate/bypass the outgoing thermal path, verify source/sink temperatures, verify pressure and flow, configure the alternate routing, then ramp into the new state.

## Mode-state model
Suggested states are NORMAL-COOL, NEUTRAL, NORMAL-HEAT, ECONOMY, BOOST, DEGRADED and SAFE-SHUTDOWN. Exact state thresholds are open until the physical system is instrumented.

## Thermal routing
Cooling mode routes a cold loop toward the user load and a hot loop toward the sink. Heating mode routes a source loop toward the low-temperature exchanger and a hot-water loop toward the delivery load.

## Acoustic routing
The acoustic field can be controlled through drive frequency, phase, impedance routing and other system variables depending on the selected implementation. Exact methods require detailed acoustic modeling.

## Energy balance
Reversibility does not create energy. The heat-pump relationship remains QH = QC + W for the defined control volume. When a heat engine drives a refrigerator, separate control-volume balances must be used for the engine and refrigeration stages.

## Mode quality
A mode is not successful simply because a temperature changes. The system must maintain a stable operating state, deliver measurable thermal capacity, remain within pressure and temperature limits, and meet the control specification.

## Protection
If the requested mode requires a thermal condition outside the qualified range, the controller should reject the request or enter degraded/safe operation rather than force it.

## Source mismatch
A 60 °C source may be adequate in one environment and inadequate in another because the sink temperature and heat-exchanger approach consume part of the available temperature difference. Reversible control must therefore consider actual source and sink conditions.

## Rapid cooling implication
The 3.3 rapid-cooling problem does not disappear with reversibility. Fast pull-down still needs adequate instantaneous cooling capacity or stored cooling energy. Mode switching cannot substitute for insufficient thermal power.

## Heating implication
Similarly, an 80 °C hot-water target requires enough heat-pump work and source heat. Reversal does not make the temperature lift free.

## Prototype validation
Mode-switch testing should measure transition time, temperature overshoot, pressure stability, acoustic stability, flow stability, recovered thermal output and safe-state behavior.

## Failure cases
Potential reversible-mode faults include valve mis-sequencing, source/sink instability, pressure transients, wrong mode-state selection, insufficient thermal lift and sensor disagreement.

## Independent safety layer
Software-controlled reversibility must be backed by hard physical isolation, pressure relief, overtemperature protection and emergency bypass. A controller should command safe behavior, but the physical system must remain protected if the controller fails.

## Evidence boundary
Published research supports the physical plausibility of reversible thermoacoustic operation. THERMA-specific reversal performance remains a prototype measurement task.
