# EXPLORIST.life — Electrical Terminology

Source family: EXPLORIST.life Mobile, Marine & Off-Grid Electrical Academy.

This belongs in the mechatronics branch because it is basic electrical-system vocabulary that transfers directly to controls, sensors, actuators, power supplies, batteries, and troubleshooting.

## Core quantities

- Voltage is electrical potential difference. It is the quantity that drives current through an impedance.
- Current is charge flow. In practical wiring work, current is what drives conductor heating and therefore wire-size and protection decisions.
- Power is the rate of energy transfer. For DC and simple resistive examples, `P = V × I`.
- Energy is power accumulated over time. Watt-hours are therefore a more useful storage/consumption quantity than watts alone.
- Amp-hours are a charge-capacity measure. Converting amp-hours to watt-hours requires voltage: approximately `Wh = V × Ah` for a nominal-voltage estimate.

## Useful rearrangements

From `P = V × I`:

- `P = V × I`
- `I = P / V`
- `V = P / I`

These are useful sanity checks when sizing power supplies, estimating load current, and deciding whether a conductor or fuse is plausible.

Example: a 1200 W load at 12 V is about 100 A, while the same 1200 W at 120 V is about 10 A. The power is the same; the current, conductor requirements, and practical wiring are not.

## AC and DC

- DC maintains one polarity and is typical of batteries, many sensors, control electronics, and low-voltage distribution.
- AC reverses polarity periodically and is typical of utility and industrial power distribution.
- Devices frequently convert between them: rectifiers convert AC to DC; inverters convert DC to AC; DC-DC converters change one DC voltage level to another.

## Basic system components

EXPLORIST.life's introductory system model is useful beyond camper wiring:

- battery: energy storage
- load: device consuming power
- fuse/circuit breaker: protects conductors and equipment from excessive current
- busbar/distribution block: common connection and distribution point
- inverter: DC → AC
- rectifier/charger: AC → DC and battery charging
- DC-DC converter: converts one DC voltage to another
- solar charge controller: a specialized DC power converter and charging controller
- shunt: low-resistance current-sensing element used to infer current from a small voltage drop

In a mechatronics system, the same block thinking applies to 24 VDC control supplies, servo drives, VFD DC links, battery-backed controls, sensors, relays, solenoids, and PLC I/O.

## Diagnostic habits

- Before measuring, decide whether you are looking for voltage, current, resistance/continuity, power, or stored energy.
- Do not confuse a source voltage rating with available current. A supply may be the correct voltage yet unable to provide enough current under load.
- Do not confuse current capacity with actual current draw. A 20 A supply does not force 20 A through a 2 A load.
- Power arithmetic is a fast plausibility check: if a claimed voltage/current pair implies an impossible power level, something in the assumption or measurement is wrong.
- Battery amp-hours by themselves are incomplete without voltage and discharge conditions.

## Scope warning

The EXPLORIST.life lessons intentionally simplify some topics for beginners. The formulas above are exact for DC instantaneous power and resistive/simple cases, but AC motor and industrial power work also introduces phase angle, power factor, reactive power, harmonics, three-phase relationships, and efficiency.

## Sources

- EXPLORIST.life, “Basic Electrical Terminology” — https://explorist.life/basic-electrical-terminology/
- EXPLORIST.life, “Basic Parts of a Mobile, Marine or Off-Grid Electrical System” — https://explorist.life/basic-parts-of-a-mobile-marine-or-off-grid-electrical-system/
- EXPLORIST.life, “Basic Electrical Formulas and Calculations” — https://explorist.life/basic-electrical-formulas-and-calculations/
