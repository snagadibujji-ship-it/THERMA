# 003 — Thermoacoustic Core Physics

## Purpose
This document defines the physical reasoning used to interpret the THERMA fixed-core thermoacoustic process. It distinguishes gas oscillation, acoustic power, thermal exchange, resonator behavior, regenerator behavior, and parasitic mechanisms.

## 1. Working gas motion
The working gas oscillates about an equilibrium position. The particles do not need to circulate through the entire machine as a one-way stream. Pressure and velocity vary in time and space.

## 2. Pressure field
A thermoacoustic resonator supports an acoustic pressure field p'(x,t) superimposed on mean pressure. The spatial structure depends on geometry, boundary conditions, gas properties and losses.

## 3. Velocity field
Particle velocity u'(x,t) is phase-related to pressure. The relation between pressure and velocity determines acoustic impedance and the direction of time-averaged acoustic power flow.

## 4. Acoustic power
For a locally modeled acoustic field, the time-averaged power flow is related to the average product of pressure and velocity over an area. The exact expression depends on the selected acoustic model and conventions.

## 5. Acoustic impedance
Z relates pressure amplitude to volume-flow amplitude. Matching source and load impedance is important because an acoustic engine may generate pressure oscillation without transferring useful power if the load is badly matched.

## 6. Resonance
Resonance occurs when geometry, gas properties and boundary conditions create a natural mode near the drive or thermoacoustic oscillation frequency. Resonance is not synonymous with high efficiency; losses and coupling determine useful output.

## 7. Standing-wave versus traveling-wave behavior
Thermoacoustic systems can use standing-wave-like or traveling-wave-like acoustic configurations. THERMA architecture decisions must select one exact regime rather than mixing incompatible assumptions.

## 8. Thermal boundary layer
Gas adjacent to a solid experiences oscillatory thermal diffusion. The thermal penetration depth determines the distance over which the gas temperature follows the wall during an oscillation.

## 9. Viscous boundary layer
Momentum diffusion near walls produces viscous losses. Small hydraulic dimensions can increase losses substantially, while large dimensions can reduce thermal interaction area.

## 10. Phase relationship
A useful thermoacoustic process depends on the phase relationship between pressure, velocity and temperature. Heat transport is not caused by the wave simply carrying heat down a tube.

## 11. Regenerator role
The regenerator provides a structured solid surface that stores and releases thermal energy during gas oscillation. It must preserve the intended temperature gradient while allowing adequate acoustic transport.

## 12. Thermal conductivity tradeoff
Too much axial conduction through the matrix can short-circuit the gradient. Too little thermal capacity can reduce heat exchange effectiveness. The optimum lies between these extremes.

## 13. Heat capacity ratio
The gas and solid heat capacities relative to oscillation frequency affect the thermodynamic phasing and thermal penetration behavior. The exact optimization is geometry-specific.

## 14. Hydraulic radius
Regenerator channel hydraulic radius affects acoustic resistance and thermal penetration. Pore size cannot be selected independently of frequency and gas properties.

## 15. Acoustic streaming
Oscillatory motion can produce nonlinear mean flows known as streaming. Streaming can transport heat in unintended directions and reduce system efficiency.

## 16. Gedeon streaming
Looped thermoacoustic configurations can show a mean mass flow that crosses components and creates parasitic heat transfer. Suppression or isolation must be considered in loop architectures.

## 17. Jetting and minor losses
Sudden area changes, ports, bends, manifolds and openings can create nonlinear losses. Exact-geometry pressure-drop accounting is therefore necessary before hardware.

## 18. Nonlinear saturation
Increasing thermal input or drive amplitude does not guarantee proportional acoustic power. Nonlinear losses can grow and flatten output response.

## 19. Temperature gradient threshold
A thermoacoustic engine may require a minimum useful thermal gradient before self-amplifying oscillation becomes established. This threshold depends on exact geometry and dissipation.

## 20. Engine onset
The onset point should be identified experimentally by monitoring acoustic amplitude, phase, frequency, temperature and input heat. A simple threshold model is not sufficient to certify operation.

## 21. Heat-driven engine chain
For the heat-driven mode, thermal energy enters the hot side, establishes a gradient through the regenerator, generates acoustic power, and is then delivered through an acoustic network to the refrigeration section.

## 22. Refrigerator chain
The refrigerator section uses acoustic work to pump heat from the cold exchanger toward a warmer exchanger. The useful output is cold-side heat removal, not merely a low measured temperature.

## 23. Heat-pump chain
The reverse configuration uses acoustic work to move heat from a low-temperature source toward a higher-temperature delivery side. Heating output includes both extracted source heat and supplied work.

## 24. Reversible operation
Reversal can be achieved by changing thermal routing, acoustic drive state, frequency or other system variables depending on the exact architecture. THERMA must select a controlled reversible mechanism for its frozen geometry.

## 25. Neutral transition
A transition state should reduce acoustic amplitude and stabilize temperature and pressure before changing thermal routing. This is safer than an instantaneous command flip.

## 26. Acoustic frequency
Frequency affects thermal penetration depth, resonator dimensions, viscous losses and component tolerances. Frequency should be solved together with geometry and gas pressure.

## 27. Mean pressure
Mean gas pressure can raise available acoustic power density but increases pressure-vessel and leak requirements. Higher pressure is therefore an optimization variable.

## 28. Working-gas candidates
Helium is a recurring candidate in project history. Nitrogen and other gases may be considered, but the selection must use actual geometry, pressure, frequency, thermal properties and compatibility.

## 29. Gas purity
Gas composition and contamination can affect acoustic properties, heat transfer and long-term stability. Prototype charging should therefore use controlled gas handling.

## 30. Pressure boundary
The acoustic gas must remain inside a qualified pressure boundary. The pressure system is separate from user-facing secondary fluids.

## 31. Heat-exchanger coupling
The gas-side thermal node and external-fluid node are connected through a finite exchanger. The exchanger design controls the practical temperature approach and heat-transfer rate.

## 32. Oscillatory heat transfer
Published thermoacoustic heat-exchanger research shows that oscillatory-flow behavior cannot simply be represented by steady-flow correlations. Geometry-specific validation is necessary.

## 33. Hot heat exchanger
The hot exchanger must transfer source-side thermal power into or out of the thermoacoustic core while maintaining pressure integrity and acceptable acoustic losses.

## 34. Cold heat exchanger
The cold exchanger must remove the intended refrigeration load with sufficiently small approach temperature and pressure loss.

## 35. Heat rejection exchanger
The rejection side must dispose of QH. Air-cooled, water-cooled or process-coupled rejection architectures can be considered according to site conditions.

## 36. Acoustic transmission network
The acoustic network between heat-engine and refrigerator sections must preserve usable acoustic power while controlling phase and impedance.

## 37. Inertance
An inertance element contributes frequency-dependent acoustic reactance. Its value must be derived from exact geometry, gas properties and target frequency rather than copied from an unrelated system.

## 38. Compliance
A compliance volume stores acoustic potential energy. It works with inertance to shape acoustic phase and resonance.

## 39. Loss resistance
Real acoustic networks have resistive losses from viscosity, turbulence, fittings, exchangers and imperfect walls. The network must be modeled with these effects.

## 40. No mechanical power train
The core architecture does not require a piston, crankshaft, flywheel, connecting rod or mechanical compressor. The working gas oscillation is fluid/acoustic motion.

## 41. Secondary-loop pumps
Pumps may exist outside the core to circulate water or another thermal fluid. They are auxiliary subsystem components, not part of the thermoacoustic conversion core.

## 42. Acoustic measurements
Development instrumentation should measure pressure amplitude, frequency, phase relationship, and potentially multiple spatial pressure nodes to identify actual acoustic behavior.

## 43. Thermodynamic measurements
Temperature and flow must be measured at each relevant hot, cold and rejection boundary so that actual thermal power can be calculated.

## 44. Correlation strategy
A credible model should predict measured acoustic and thermal behavior within a declared uncertainty band. Model corrections must be tied to physical causes.

## 45. Literature validation strategy
Before claiming THERMA performance, the computational approach should reproduce at least one published experimental geometry with known conditions. This separates solver/model errors from THERMA design effects.

## 46. Exact-geometry requirement
A generated concept image does not supply enough information to solve the acoustic field. Tube lengths, diameters, volumes, porosity, pressure, gas properties and exchanger geometry must be frozen numerically.

## 47. Model hierarchy
A practical hierarchy can include: first-law energy balance, lumped acoustic network, linear thermoacoustic model, exact-geometry solver, coupled thermal-fluid model, and finally prototype correlation.

## 48. Uncertainty
Uncertainty should be carried on heat-flow measurements, temperatures, flow rates, pressure, frequency, phase and material properties. A narrow-looking simulation output with poorly known inputs is not high confidence.

## 49. Main research question
Can a fixed thermoacoustic architecture deliver sufficient stable acoustic work or heat-pump transfer at the selected temperature gradients after realistic losses are included?

## 50. Closing principle
The THERMA core is a wave-and-thermal machine, not a mechanically reciprocating engine. The design challenge is to engineer the pressure/velocity/temperature field, solid thermal matrix and heat exchangers so that the desired net energy flow survives real losses.
