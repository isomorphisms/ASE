# Front-end diagnostic patterns

This file is the reusable layer distilled from reviewed A4 sources. It is meant to improve real troubleshooting answers, not memorize test facts.

## A wheel shake is an input, not a diagnosis

The common hand tests are useful because they load several joints, but the clock position alone does not identify the failed part.

When a wheel moves, watch the boundaries:

- **tie rod end:** does the stud/socket or tie rod move late relative to the knuckle when steering input reverses?
- **ball joint:** does the knuckle move relative to the control arm at the joint?
- **hub/bearing:** does the wheel/rotor/hub move relative to the knuckle or bearing housing?
- **control-arm bushing:** does the arm translate excessively relative to its chassis mount under load?

The question is always: **where is the lost motion?**

This prevents the lazy rule “3-and-9 means tie rod, 12-and-6 means bearing.” Those positions are useful starting inputs, not component oracles.

## Loading matters

Ball joints are especially easy to inspect incorrectly because suspension architectures carry spring load differently.

Do not assume every lower joint is the load-carrying joint or that every upper joint is merely a follower. Determine the design and use the vehicle procedure. A joint that is still loaded by spring force can appear tight even when it has wear; an incorrectly unloaded design can also produce misleading motion.

A generic video demonstration is therefore best treated as a way to recognize **relative looseness**, not as a universal lifting procedure or wear specification.

## Noise needs a reproducing condition

“Clunk,” “rattle,” and “groan” are not parts names.

Useful conditions to preserve:

- knock/rattle mainly over small bumps → inspect links, bushings, mounts, ball joints, tie rods, and anything that can reverse load rapidly;
- sway-bar-link diagnosis becomes much stronger when the link can be moved by hand, its joint separates, or it visibly strikes nearby structure;
- groan/hum that changes as the vehicle is gently loaded left/right → wheel bearing becomes plausible, but confirm at the hub rather than replacing from the road test alone;
- repeated bouncing, float, excessive brake dive, or poor body control → damping problem becomes plausible; inspect shocks/struts and mounts.

Try to reproduce the symptom in a way that loads the suspected component, then inspect while that load is applied.

## Shock/strut fluid: distinguish weepage from leakage

A little oil film is not the same thing as a failed damper.

Monroe's service guidance distinguishes acceptable light weepage from real leakage. A unit that is broadly wet, dripping, physically damaged, or accompanied by degraded damping is a much stronger failure case than a faint film around the seal.

This is a useful correction to simplistic videos that say any visible oil means replacement.

## Alignment is downstream of mechanical condition

Do not use an alignment rack to hide looseness, sag, or bent parts.

Before treating toe/camber/caster adjustment as the repair:

1. verify tire condition and pressure;
2. inspect steering and suspension joints for looseness or binding;
3. verify ride height when relevant;
4. repair loose, worn, bent, or sagged components;
5. then measure and adjust alignment.

Tie-rod replacement directly changes toe and normally calls for alignment. Control-arm, strut, knuckle, cradle, or ride-height changes can also alter alignment depending on architecture.

## Separate free articulation from free play

Ball-and-socket joints must articulate. Movement through the designed angle is not itself a defect.

The defect is lost motion inside the joint: the input reverses but the connected part does not immediately follow, the stud shifts axially/radially beyond specification, or the socket rattles instead of moving with controlled resistance.

That distinction matters for tie rods, ball joints, and many sway-bar links.

## Better answer shape for suspension questions

When given a symptom, avoid dumping a parts list. A better response is:

1. name the most useful reproducing condition;
2. say which component boundary to watch or measure;
3. say what relative motion/noise would implicate that component;
4. say what the test does **not** rule out;
5. choose the next boundary if the first one is tight.

Example structure:

> Rock the wheel while watching the outer tie-rod joint itself. If the knuckle changes direction before the tie rod takes up motion, that joint has play. If the tie rod follows immediately, keep the same input but watch the hub/knuckle and ball-joint/control-arm boundaries rather than replacing the tie rod because the wheel moved.

That is the kind of reasoning this branch should reinforce.
