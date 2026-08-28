# A5 — Brakes

Official 2026 ASE weighting:

| Area | Scored questions | Weight |
|---|---:|---:|
| Hydraulic, power-assist, and parking-brake systems | 19 | 43% |
| Drum brakes | 5 | 11% |
| Disc brakes | 11 | 24% |
| ABS, traction control, and electronic stability control | 10 | 22% |
| **Total** | **45** | **100%** |

Official source: https://www.ase.com/uploads/ASE_Automobile_Study_Guide_2026.pdf

A5 is mostly a diagnosis problem. Start by separating four things that people often mix together:

1. **pedal travel** — how far the pedal moves;
2. **pedal effort** — how hard it is to push;
3. **brake force** — how much a wheel actually slows the vehicle;
4. **release** — whether that brake lets go when pressure is removed.

A booster primarily changes effort. Hydraulic/mechanical faults can change travel, force, and release. That distinction prevents a lot of bad diagnosis.

## Pedal-feel map

### Hard pedal

Think inadequate assist before assuming air in the hydraulic system. Depending on the vehicle: vacuum supply/check valve/booster, hydraulic boost, electric assist, or an assist-control problem. A restriction can also create unusual effort, so confirm rather than guessing.

### Long or low pedal

Possible families include:

- air or vapor in hydraulic fluid;
- excessive shoe/pad-to-rotor clearance;
- rear drum adjustment problem;
- pad knockback from rotor/hub/bearing movement or runout;
- hydraulic leak;
- master-cylinder problem;
- excessive mechanical travel somewhere in the system.

The first question is whether **pumping changes it**.

### Pedal pumps up firmer/higher

That points toward a travel/clearance/compressibility problem more than a simple lack of boost. Air/vapor, excessive clearance, poor drum adjustment, or pad knockback are examples.

### Pedal slowly sinks under steady force

Think hydraulic pressure is not being held. Internal master-cylinder bypass is a classic cause, but external leakage or faults elsewhere in the hydraulic circuit must be ruled out.

### Spongy pedal

Compressible gas in a system intended to be essentially incompressible is the classic mechanism. Air, overheated fluid producing vapor, or sometimes hose expansion can create the feel.

## Keep booster testing separate from hydraulic testing

A basic vacuum-booster check on a conventional vacuum system:

1. engine off;
2. pump pedal several times to exhaust stored vacuum;
3. hold steady pedal force;
4. start engine;
5. normal assist should make the pedal move somewhat as assist appears.

That test asks whether assist arrives. It does **not** by itself explain a long pedal that pumps up, a dragging wheel, or a hydraulic leak.

## Brake pull

The vehicle generally yaws toward the side producing **more** braking force. That means a pull can be caused either by a stronger/grabbing brake on the pull side or by a weak brake on the opposite side.

This is why "seized caliper" is not a complete diagnosis. A caliper can fail in different ways:

- piston/slides bind so the brake cannot apply normally → that side may be weak;
- piston/slides bind applied → that side drags and overheats;
- hose/restriction limits pressure going in → weak application;
- hose/restriction traps pressure on release → drag.

The symptom tells you which failure mode is plausible; the part name alone does not.

## Brake drag / one hot wheel

A wheel much hotter than its mate is strong evidence that energy is being dissipated at that corner. Possible causes include:

- caliper piston binding;
- caliper slide/pad binding;
- flexible hose acting as a one-way restriction;
- parking-brake mechanism not releasing;
- drum hardware/shoe problem;
- hydraulic pressure being held upstream;
- less commonly, another friction/rotating fault such as a badly failing bearing.

### High-value discriminator: release with the bleeder

With the vehicle safely supported and the brake confirmed dragging, opening that wheel's bleeder can distinguish **trapped hydraulic pressure** from **mechanical binding**:

- brake releases when pressure is vented → pressure was trapped upstream of the bleeder; investigate hose, valve, master-cylinder/booster pushrod/compensation path, etc.;
- brake remains mechanically stuck → investigate caliper piston/slides/pads, drum/parking-brake hardware, or other wheel-end binding.

This is a diagnostic procedure, not permission to drive a vehicle with a compromised brake system. Brake fluid handling, support, and bleeding afterward must follow proper service procedure.

## Heat can create a second fault

A dragging brake can overheat the rotor/drum, pad/shoe, caliper, and fluid. If brake fluid near the hot corner reaches a condition where vapor forms, pedal travel can suddenly become long/spongy because vapor compresses. Thus **one original drag fault can produce both a hot wheel and a later hydraulic-feel symptom**.

Do not assume that is the only explanation. Air, leakage, knockback, master-cylinder faults, or multiple simultaneous faults remain possible until tested.

## Disc-pad wear patterns

Pad wear is evidence about relative movement and force:

- one pad much thinner than its mate can point toward piston/slide/caliper movement problems;
- tapered wear suggests the pad/caliper is not remaining square and free through its travel;
- both pads worn evenly but rapidly suggests a different problem from one pad hanging up.

Exact inboard/outboard interpretation depends on caliper design. Avoid memorizing a single rule without identifying whether the caliper is fixed or floating and how its slides/pistons act.

A useful historical note from OldSchoolNoe's A5 discussion is that brake drag/pull were covered, while tapered pad wear and inner-vs-outer wear deserved additional study. That is a good warning not to stop at "caliper bad."

## Rotor/runout/thickness reasoning

Keep these distinct:

- **lateral runout**: rotor face wobbles side-to-side as it turns;
- **thickness variation**: rotor thickness changes around its circumference;
- **surface finish/hot spots/deposits**: friction conditions vary even if geometry measures differently.

Runout can contribute to pad knockback and can generate thickness variation over time. Thickness variation can create periodic pedal/brake-force pulsation. Measure before replacing parts by habit.

## ABS / TCS / ESC

The official A5 test gives electronic brake control 22% of scored questions, so it cannot be treated as an appendix.

Core diagnostic chain:

**wheel motion → wheel-speed sensor/tone target → wiring/module input → control decision → hydraulic modulator/pump/valves → wheel brake pressure**.

When a warning light or unwanted activation occurs, determine whether the module saw bad information, made a bad decision, or could not execute the requested hydraulic action. Scan data and circuit/mechanical tests should agree.

## Exam-question habit

For Technician A / Technician B questions, evaluate each statement independently as true or false. Do not assume the two technicians are arguing or that only one can be right.

For every diagnosis question, rewrite it mentally as:

**symptom + conditions → candidate causes → one test that separates them**.

That is more durable than memorizing answer-key associations.
