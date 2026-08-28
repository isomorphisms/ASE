# ElectrArc240 — power electronics notes

ElectrArc240 is Fred Dally's electronics channel. The strongest material for this branch is his power-electronics sequence: MOSFET switching, linear and switching supplies, buck/boost converters, active power-factor correction, wide-bandgap devices, and three-phase permanent-magnet motors.

These are technical study notes, not a transcript. Where possible, the source list uses the presenter's own YouTube video and chapter structure.

## 1. Everything You Need to Know about MOSFETs

Source: https://www.youtube.com/watch?v=ElTTOsj3y-Q

### Main ideas

- A MOSFET is useful as a power switch because its gate is voltage-controlled, but the gate is not electrically "free": the device has capacitances that must be charged and discharged every transition.
- `V_GS(th)` is the beginning of measurable conduction, not the voltage that guarantees a low-resistance fully-on switch. For power design, use the datasheet's specified `R_DS(on)` at a stated gate voltage.
- On-state conduction loss is approximately `I^2 R_DS(on)`.
- The intrinsic body diode matters whenever current commutates through the device. Its direction and reverse-recovery behavior can matter enormously in switching converters and motor drives.
- MOSFET behavior changes with temperature. Thermal resistance from junction to case/ambient is part of the electrical design because junction temperature changes losses and ultimately sets the safe operating limit.
- Gate-source, gate-drain, and drain-source capacitances are not minor details at high switching speed. Gate-drain capacitance creates the Miller region during a transition.
- Package and PCB inductance in the gate, source, and drain paths produces voltage overshoot, ringing, false turn-on, and slower/less predictable switching.
- Kelvin-source connections, compact high-current loops, suitable gate resistance, and deliberate gate-drive layout are practical ways to reduce parasitic trouble.
- The video ends by placing silicon MOSFETs beside IGBTs and GaN devices rather than treating one transistor family as universally best.

### Maintenance/design takeaway

A transistor that looks like a simple three-terminal switch on the schematic can behave very differently once switching speed, current, temperature, and physical wiring are included. The layout is part of the circuit.

## 2. Every Component of a Switch Mode Power Supply Explained

Source: https://www.youtube.com/watch?v=3FyXqNcqvRM

### Main ideas

- The key conceptual move in a switched supply is to move energy through magnetic and electric storage instead of continuously burning the voltage difference in a linear pass element.
- Inductors resist rapid change in current and can store energy in a magnetic field. Switching converters repeatedly store and release that energy.
- Higher switching frequency allows physically smaller magnetic components, but raises switching, magnetic, EMI, and layout problems.
- A practical SMPS is much more than a transistor plus transformer/inductor. The video walks through output filtering, bleeder resistors, current-shunt resistors, input filtering, input protection, Class-Y capacitors, snubbers, and the controller.
- Bleeder resistors give charged capacitors a discharge path after power is removed.
- Current shunts convert current into a small measurable voltage for control/protection.
- Input filters keep switching noise from being conducted back onto the supply and help keep external noise out of the converter.
- Snubbers absorb/damp energy associated with leakage inductance and parasitic ringing rather than allowing large repetitive voltage spikes.
- Class-Y capacitors cross an isolation barrier only when specifically safety-rated for that service; ordinary capacitors are not substitutes.

### Maintenance/design takeaway

When a switching supply fails, divide it into functional blocks: input protection/filtering, rectification/DC bus, switch and drive, magnetic component, secondary rectification/filtering, sensing/feedback, and protection. The schematic symbol for the converter hides several failure mechanisms.

## 3. Every Component of a Linear Power Supply Explained (while building one)

Source: https://www.youtube.com/watch?v=UTetQhGyUVg

### Main ideas

- The video builds the path in order: mains -> fuse/switch -> transformer -> rectification -> smoothing capacitor -> regulator.
- Transformer magnetizing current is limited primarily by inductive behavior, not just the winding's small DC resistance. That is why an AC transformer primary is not equivalent to laying a low-resistance wire directly across the source.
- The transformer provides voltage conversion and galvanic isolation between windings.
- A bridge rectifier makes both AC half-cycles contribute to the same DC polarity.
- A reservoir capacitor charges near waveform peaks and supplies the load between peaks, reducing ripple.
- Increasing capacitance reduces ripple but makes the rectifier/input current more concentrated into high-current pulses. "Bigger capacitor" therefore has costs.
- A Zener/open-loop regulator can establish an approximate voltage, but a closed-loop regulator measures the output error and corrects it, giving much better load and line regulation.

### Maintenance/design takeaway

This is a useful bridge between transformer-and-relay industrial wiring and modern switch-mode electronics: follow energy from source to load, then identify what each stage is doing to voltage, current, isolation, ripple, and regulation.

## 4. How Buck, Boost & Buck-Boost DC-DC Converters Work

Source: https://www.youtube.com/watch?v=PgTR7226sHU

### Main ideas

- PWM controls how long the switching state is applied during each cycle.
- Capacitors store energy in an electric field; inductors store energy in a magnetic field. The three basic converter families rearrange the switch/diode/inductor relationship to change the output behavior.
- Buck: output voltage lower than input.
- Boost: output voltage higher than input.
- Buck-boost: can produce a magnitude above or below the input; the simplest classical topology inverts polarity.
- Flyback is an isolated relative of buck-boost; forward conversion is an isolated relative of buck operation.
- Continuous-current operation means inductor current never falls to zero during a switching cycle; discontinuous operation changes the equations and stresses.
- Synchronous rectification replaces a diode with a controlled MOSFET to reduce conduction loss when that extra complexity is worthwhile.
- The ideal voltage relationships are primarily set by duty cycle, but real designs also need switching frequency, inductance, capacitance, ripple, current rating, losses, and control-loop stability.

### Maintenance/design takeaway

Many seemingly different power supplies reduce to a small set of energy-transfer patterns. Recognizing the topology is often faster than tracing every component individually.

## 5. Fixing the Full Bridge Rectifier's Big Flaw — Active Power Factor Correction

Source: https://www.youtube.com/watch?v=eI_LQWrQam4

### Main ideas

- A bridge rectifier followed by a large DC capacitor does not necessarily draw a sinusoidal current from a sinusoidal voltage source.
- The capacitor is replenished mainly when the instantaneous line voltage rises above the capacitor voltage, so current arrives in narrow pulses around the voltage peaks.
- Those current pulses create harmonics and poor distortion power factor even when the load is not simply an inductive lagging load.
- Power factor is about how effectively RMS current is converted into real power; waveform distortion matters as well as phase shift.
- Active PFC adds a controlled switching stage so the input current can be shaped to follow the input voltage while also regulating a DC bus.
- A boost-type PFC stage is a common implementation because it can draw controlled current from the rectified line and raise/regulate the DC bus.

### Maintenance/design takeaway

Do not infer line-current waveform from the DC load alone. Rectifiers, capacitors, and switching controls reshape current substantially.

## 6. A Brief Explanation of Permanent Magnet AC Motors

Source: https://www.youtube.com/watch?v=wxKT9TRKfFQ

### Main ideas

- A PMSM has a permanent-magnet rotor and a three-phase stator.
- Three phase currents establish a rotating stator magnetic field; the rotor magnets align with and follow that field.
- Useful torque therefore depends on controlling the stator field relative to rotor position rather than merely applying arbitrary AC.
- Modern high-power machines often need deliberate stator and rotor thermal management because electrical and magnetic losses ultimately become heat.
- PMSM construction differs from the common squirrel-cage induction motor even though both use a rotating three-phase stator field.

### Maintenance/design takeaway

For motor-control troubleshooting, keep the motor and inverter conceptually separate: the machine supplies electromagnetic/mechanical dynamics, while the drive synthesizes the phase currents and frequency/angle needed to create torque.

## 7. Everything is Better: GaN vs Silicon Power Supplies

Source: https://www.youtube.com/watch?v=vgmqUhvQlww

### Main ideas

- GaN's value is not simply "replace a silicon MOSFET and everything gets better." Faster devices change the whole converter design.
- Lower switching loss and lower parasitic charge can permit higher switching frequency, which allows smaller magnetics and filters and therefore higher power density.
- Faster edges make PCB layout, EMI, gate drive, isolation capacitance, and thermal design more demanding, not less.
- The benefit is system-level: transistor technology, magnetics, rectification, packaging, cooling, and control must be designed together.

## Cross-video map

- **MOSFET video:** what the switching element really does.
- **Buck/boost video:** the basic energy-transfer topologies.
- **SMPS video:** all the supporting parts needed around a practical converter.
- **Linear supply video:** the older, slower baseline that makes the switched approach easier to compare.
- **PFC video:** what the converter looks like from the AC source side.
- **PMSM video:** where controlled three-phase power becomes mechanical torque.
- **GaN video:** how faster semiconductor technology changes the rest of the design.

## Questions worth carrying into later notes

1. In a failed converter, is the transistor damage the primary fault or the consequence of a bad gate-drive/snubber/load condition?
2. Where is the high-current switching loop physically located on the PCB?
3. What controls peak current and what shuts the converter down on overcurrent?
4. Which capacitors can remain charged after input power is removed?
5. Is a motor fault truly a motor fault, or is the drive producing a bad phase waveform/current?
6. When a supply has poor input current quality, is the problem displacement power factor, harmonic distortion, or both?
