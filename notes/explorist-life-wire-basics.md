# EXPLORIST.life — Wire Basics

This note extracts the parts of EXPLORIST.life's Wire Basics material that transfer cleanly to mechatronics, control panels, mobile machinery, low-voltage controls, and machine wiring.

## 1. Wire type is part of the design

A conductor is not specified by copper area alone. The installation also cares about:

- solid vs stranded construction
- insulation material and temperature rating
- flexibility and vibration resistance
- oil, water, abrasion, and chemical exposure
- approvals/certifications appropriate to the installation

A wire that carries the current electrically may still be the wrong wire mechanically or environmentally.

## 2. Gauge and conductor count

American Wire Gauge runs backward: a smaller AWG number means a larger conductor, until the `0`, `2/0`, `3/0`, `4/0` sizes.

Multi-conductor labels such as `12/2` or `10/3` normally identify conductor gauge followed by the number of current-carrying conductors. Grounding conductors can make the physical count look different from the label.

For machine work, always read the actual cable construction rather than inferring conductor purpose from the shorthand alone.

## 3. Ampacity is conditional

There is no single universal statement like “6 AWG carries X amps.” Allowable current changes with:

- insulation temperature rating
- ambient temperature
- whether the cable is in a hot enclosure or engine space
- whether conductors are bundled, sheathed, or in conduit
- number of current-carrying conductors in a bundle
- applicable code or standard

The physical reason is heat. Copper loss is approximately `I²R`; if heat cannot leave the conductor, allowable current must be reduced.

## 4. Voltage drop can dominate before thermal ampacity

A wire may be thermally capable of carrying a current and still be too small because the load sees excessive voltage drop.

This matters especially in low-voltage DC systems: a small absolute drop is a large percentage of a 12 V or 24 V supply.

Mechatronics examples:

- a 24 VDC solenoid may chatter or fail to shift if its long cable drops too much voltage under coil current;
- a sensor may remain powered but fall outside its specified supply range;
- a motor starter or relay coil may pull in unreliably;
- a controller can reset when a large actuator starts.

## 5. Fuses protect conductors

A fuse is not chosen only from the load's normal current. Its job includes keeping the conductor from reaching a damaging temperature during a fault.

If several smaller conductors are paralleled, a single upstream fuse must still protect each individual conductor under realistic fault conditions. Parallel copper is not automatically equivalent to one large conductor from a protection standpoint.

## 6. Bigger wire is not automatically better

Upsizing can reduce voltage drop and heating, but it can create new problems:

- conductor no longer fits the device terminal;
- lug or ferrule range no longer matches;
- bend radius becomes impractical;
- terminal hardware is mechanically stressed;
- fuse/protection assumptions no longer match the intended design.

Choose the conductor as part of a chain: load → current → run length → environment → derating → voltage drop → protection → terminal compatibility.

## 7. Mobile/marine rules are not industrial rules

EXPLORIST.life frequently works from ABYC and mobile/off-grid practice. Industrial machines may instead fall under NEC, NFPA 79, UL 508A, OEM requirements, or other rules. The physical principles transfer; specific tables and allowed practices may not.

## Practical inspection checklist

When troubleshooting an existing wire run:

1. Identify source and load voltage.
2. Measure load current if safe and appropriate.
3. Read conductor size and insulation markings.
4. Inspect termination type and crimp quality.
5. Look for heat discoloration, hardened insulation, loose strands, corrosion, and damaged insulation.
6. Measure voltage drop while the load is actually energized.
7. Check fuse/breaker rating against the conductor, not only against the load nameplate.
8. Account for bundling, enclosure heat, and neighboring power conductors.

## Sources

- EXPLORIST.life, “Understanding Wire Types” — https://explorist.life/understanding-wire-types/
- EXPLORIST.life, “Understanding Wire Sizes” — https://explorist.life/understanding-wire-sizes/
- EXPLORIST.life, “Max Amps a Wire Can Handle...” — https://explorist.life/max-amps-a-wire-can-handle/
- EXPLORIST.life, “Common Wire Choice Mistakes” — https://explorist.life/common-wire-mistakes/
