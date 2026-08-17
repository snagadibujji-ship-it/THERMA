# 08 — Reversible Operation and Mode Switching

## Concept
THERMA 3.5 is intended to serve both cooling and heating through a common fixed thermoacoustic platform. The direction of useful thermal pumping depends on how the acoustic field and thermal interfaces are configured.

## Cooling path
In cooling mode, a heat-driven gradient may create acoustic power for the refrigeration section, or an external acoustic source may drive the refrigerator during controlled testing. The cold heat exchanger removes heat from the load and the warm side rejects it.

## Heating path
In heating mode, externally supplied acoustic work is routed to the heat-pump function. Heat is extracted from the low-temperature source and delivered to the hot-water loop.

## Transition state
A safe mode transition should not instantly reverse valves or acoustic operating conditions. A neutral state is recommended:

1. reduce acoustic amplitude;
2. isolate the current thermal route;
3. verify temperatures and pressure;
4. open or bypass the new route as required;
5. ramp the acoustic state toward the new operating point;
6. verify stability before declaring the new mode active.

## No moving-core requirement
Reversible operation is not accomplished by adding a mechanical piston or crankshaft. The THERMA baseline uses fixed acoustic geometry, a sealed working gas, fixed thermal matrices and external fluid-routing components.

## Control architecture
The controller should track source temperature, load temperature, heat-sink temperature, acoustic amplitude, phase, frequency, pressure and flow. It should reject any requested mode that violates a defined thermal or pressure envelope.

## Failure during switching
Possible faults include residual hot/cold gradients, inadequate flow, acoustic instability, valve disagreement, sensor disagreement, pressure excursions and heat-exchanger thermal shock. A transition failure should return the system to a defined safe state rather than continuing toward an unknown operating condition.

## Validation
Mode switching is a hardware test, not simply a software state change. Acceptance should include repeated cooling-to-neutral-to-heating and heating-to-neutral-to-cooling transitions, measured response time, temperature overshoot, acoustic stability and safe shutdown behavior.
