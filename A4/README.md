# A4 — Suspension and Steering

Official 2026 ASE weighting:

| Area | Scored questions | Weight |
|---|---:|---:|
| Steering systems diagnosis and repair | 12 | 30% |
| Suspension systems diagnosis and repair | 12 | 30% |
| Wheel alignment diagnosis, adjustment, and repair | 11 | 28% |
| Wheel and tire diagnosis and service | 5 | 12% |
| **Total** | **40** | **100%** |

Official source: https://www.ase.com/uploads/ASE_Automobile_Study_Guide_2026.pdf

The useful way to learn A4 is not as a bag of component names. Treat the wheel as the end of a mechanism. Ask which point moved, which angle changed, whether it changed statically or only while the suspension travels, and what measurement would distinguish one cause from another.

## Alignment geometry

### Camber

Wheel tilt from vertical viewed from the front/rear.

- top outward: positive camber
- top inward: negative camber

Large camber error can create shoulder wear. Side-to-side camber difference can contribute to pull; the exact result interacts with caster, tire conicity, road crown, ride height, and suspension design.

### Caster

Fore/aft tilt of the steering axis viewed from the side. Positive caster places the upper steering-axis point behind the lower point in the usual convention.

Caster strongly affects straight-line stability, steering return, and steering effort. A side-to-side difference can create pull. Caster by itself is not usually the classic direct tire-wear angle the way toe and camber are.

### Toe

Difference in wheel pointing viewed from above.

Toe error scrubs tread because the tires are being forced to travel slightly sideways while the vehicle moves forward. It is often the alignment angle with the fastest tire-wear consequence.

A useful distinction: **static toe** is what the alignment rack reports at rest; **dynamic toe change** while the suspension moves is the mechanism behind bump steer.

### Steering-axis inclination (SAI)

The inward tilt of the steering axis from vertical viewed from the front. On many vehicles it is not an ordinary adjustment. That is exactly why it is diagnostically useful: an abnormal value can point toward bent or displaced structural/suspension parts rather than an adjustment simply being out.

Hunter alignment equipment explicitly measures SAI and included angle as secondary/advanced diagnostic measurements.

### Included angle

A combined steering-axis/camber measurement used to help localize bent or displaced parts. The familiar shorthand is SAI plus signed camber, but use the alignment machine's sign convention and OEM information rather than doing blind arithmetic from absolute values.

If camber is wrong while included angle remains plausible, think differently than when both camber and included angle are displaced. The diagnostic value is in comparing the geometry, not memorizing one universal failed-part lookup table.

### Thrust angle

Direction the rear wheels/axle push the vehicle relative to the vehicle centerline. A nonzero thrust angle can leave the steering wheel off-center and make the vehicle appear to travel slightly sideways even when front toe has been adjusted.

## Three steering symptoms that should not be collapsed together

### Bump steer

Uncommanded steering/toe change as the suspension moves through jounce and rebound. The root idea is geometry: the steering link and suspension links trace different arcs, so a bad relationship between their pivots or a displaced/bent component can make toe change with ride height.

### Memory steer

The steering does not freely return from a turn and seems to "remember" the last direction. Think **binding** before thinking alignment number: strut mount/bearing, ball joint, tie-rod end, steering shaft/U-joint, steering gear, or another articulating point can resist return. Which components apply depends on the vehicle architecture.

### Torque steer

A steering disturbance that appears under drive torque, especially on front-wheel-drive layouts. It is not bump steer and not memory steer. Driveshaft geometry, compliance, tire traction differences, engine/transaxle movement, alignment, and suspension geometry can all contribute.

## Steering linkage

Know both broad families because diagnostic questions often depend on recognizing which parts even exist:

- rack-and-pinion: rack, inner/outer tie rods, steering shaft and assist hardware;
- parallelogram/recirculating-ball layouts: steering gear, pitman arm, center/relay link, idler arm, tie rods, plus architecture-specific links.

Free play is not a diagnosis. Watch each joint while steering load reverses and locate where motion is lost.

## Suspension diagnosis by geometry

When a bushing, ball joint, control arm, strut, spring, or mounting point wears or bends, ask:

1. Which locating point can now move?
2. In which direction can it move under load?
3. Which alignment angle(s) must therefore change?
4. Does the angle change at rest, under braking/acceleration, or over bumps?
5. What physical inspection or alignment measurement can expose that movement?

This is safer than memorizing "part X always changes angle Y" because suspension layouts differ.

### Ball joints

Do not assume every lower ball joint is load-carrying or that every upper joint is a follower. Determine where the spring loads the control arm/knuckle, then follow the OEM inspection procedure. Some joints must be unloaded before checking play; others are checked under a specified load and direction.

### Ride height first

Spring sag, bent parts, load, and incorrect ride height can move alignment geometry. Correct/verify ride height and damaged parts before treating an alignment adjustment as the repair.

## Tires and wheels

### Size notation

For `205/60R16`:

- `205` = nominal section width in millimetres;
- `60` = sidewall section height as a percentage of section width;
- `R` = radial construction;
- `16` = nominal wheel/rim diameter in inches.

### Inflation

Use the vehicle manufacturer's specified cold inflation pressure for the vehicle/load condition. The tire sidewall maximum is a tire limit, not the ordinary target pressure.

### Date code

The final four digits of a modern DOT tire identification number encode manufacturing week and year, e.g. `4614` means week 46 of 2014. Age is one inspection input; condition and manufacturer guidance still matter.

### Wear is evidence

- both shoulders: commonly underinflation/overload pattern;
- center: commonly overinflation pattern;
- one shoulder: camber/toe/loaded-geometry possibilities;
- feathering: strong toe clue;
- cupping/scalloping: investigate damping, looseness, balance/runout, and alignment rather than assigning one cause from appearance alone.

A tire itself can create a pull through conicity/radial force variation. Swapping tires side-to-side when permitted can therefore be a discriminating test instead of immediately changing alignment.

## Recovered study prompts

Historical study/search records show explicit attention to:

- alignment angles;
- SAI and included angle;
- toe links;
- track bars;
- bump steer;
- memory steer;
- steering linkage;
- tire size;
- front-suspension wear and angle changes;
- ball-joint loading/tests.

Those are retained here because they form one connected geometric problem rather than isolated vocabulary.
