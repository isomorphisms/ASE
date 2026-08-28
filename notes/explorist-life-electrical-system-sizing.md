# EXPLORIST.life — electrical system sizing

This note keeps the transferable electrical reasoning from EXPLORIST.life's Electrical System Sizing lessons inside the mechatronics branch. The source context is mobile/marine/off-grid power, but the useful ideas are broader: measure loads, distinguish power from energy, account for duty cycle, avoid sizing from nameplate maximums alone when actual measurements are available, and size conductors/protection/conversion hardware from the real load profile.

## Core method

A useful load study starts with each device separately, then rolls the devices up into a system-level power audit.

- **Power** is an instantaneous rate, usually watts.
- **Energy** is power accumulated over time, usually watt-hours or kilowatt-hours.
- For a steady load: `Wh = W × hours`.
- For minutes: `Wh = W × minutes / 60`.
- For cycling loads, include duty cycle rather than pretending the load is continuously at full power.
- For devices whose draw changes substantially with operating state, direct measurement over a representative interval is better than using only the maximum nameplate rating.
- If the device has an internal battery, one workable estimate is the battery's watt-hour capacity times the number of equivalent full recharges per day.
- Small loads can be negligible individually but material when many of them are accumulated into one audit.

## Lessons and transferable points

### Coffee maker / intermittent resistive loads

The coffee-maker lesson uses both the quick estimate from rated watts and elapsed time and a plug-in energy meter for a more realistic result. The important distinction is between a high instantaneous load and the actual watt-hours consumed during a short duty period.

Mechatronics connection: heaters, solenoids, brake resistors, pumps, and other intermittent loads should not all be treated as continuous full-load devices when estimating energy use or thermal duty.

### Cell phones and other rechargeable devices

The phone lesson estimates energy from internal battery capacity and recharge frequency. This is useful when the load is difficult to characterize instantaneously but its stored energy is known.

Mechatronics connection: battery-backed sensors, handheld instruments, portable HMIs, radios, and small autonomous nodes can be budgeted from stored energy and recharge cycles.

### Computers and variable electronic loads

The computer lesson contrasts estimation from internal battery capacity with measurement using an AC energy meter. It explicitly recommends measuring over a representative work period when the load varies.

Mechatronics connection: IPCs, industrial PCs, HMIs, switches, vision systems, and controls electronics often have variable rather than fixed draw. A representative energy measurement can be more useful than multiplying the PSU's maximum rating by 24 hours.

### TV / game console as an example of state-dependent loads

This lesson is useful because the load changes substantially between idle, menus, loading, and active operation. EXPLORIST therefore favors measuring accumulated energy instead of trying to model every state separately.

Mechatronics connection: variable-state equipment such as robots, conveyors, pumps, compressors, servo systems, and machine tools should be measured over a representative production cycle when practical.

### Space heater / high continuous loads

The heater lesson shows how a seemingly ordinary load becomes enormous in daily energy terms when it operates for many hours. Instantaneous watts alone do not communicate the full burden.

Mechatronics connection: continuous heaters, ovens, enclosure heaters, process heating, and long-duty resistive loads dominate energy budgets rapidly.

### Air conditioner / cycling loads

The A/C lesson explicitly uses duty cycle in the energy estimate rather than assuming the compressor runs continuously.

Mechatronics connection: refrigeration, compressed-air systems, hydraulic power units, coolant pumps, extraction fans, and thermostatically controlled equipment often require duty-cycle-based estimates.

### LED lighting

The lighting lesson uses `Watts × Minutes / 60 = Wh` and notes that long-duration low-power loads still accumulate meaningful energy.

Mechatronics connection: panel lighting, machine lights, indicators, auxiliary cooling, and other low-power loads should still be included in a complete machine or cell load audit.

### Water pump and vent fan

These lessons reinforce the same principle: estimate or measure operating power, determine realistic daily run time or operating states, and convert that into watt-hours.

Mechatronics connection: pumps and fans are common auxiliaries; their real duty cycle matters as much as their nameplate watts when estimating total energy consumption.

## Full power audit

The system-level method is to list every load and record either measured daily watt-hours or an estimate from watts, run time, and duty cycle. The current EXPLORIST power-audit calculator also separates simultaneous AC load from total daily energy because inverter capacity and battery/energy capacity answer different questions.

That distinction transfers directly to machines:

- **Peak/simultaneous load** determines whether a supply, inverter, transformer, feeder, contactor, or generator can support the instantaneous demand.
- **Accumulated energy** determines battery capacity, backup-runtime requirements, energy consumption, and thermal/operational duty over time.
- **Surge/inrush** may impose a still larger short-duration requirement and should not be confused with either steady-state power or daily energy.

## Useful measurement habit

When a load is variable, measure it over a representative cycle rather than constructing an unnecessarily detailed theoretical model from every state. Then compare the measured result with a first-principles estimate as a sanity check.

For mechatronics this becomes a general diagnostic pattern:

1. Read the nameplate/specification.
2. Predict the expected range.
3. Measure actual current/power/energy under representative operating conditions.
4. Compare expected and actual behavior.
5. Investigate large discrepancies rather than automatically trusting either the nameplate or the meter.

## Source pages reviewed

- EXPLORIST.life Electrical System Sizing lessons for coffee maker, cellphone, computer, TV/game console, space heater, air conditioner, LED lighting, water pump, and vent fan.
- EXPLORIST.life Power Audit Calculator and power-audit guide.

These are source-derived study notes, not a transcript. Mobile/marine/off-grid sizing conventions should not be copied blindly into an industrial control panel or machine design.