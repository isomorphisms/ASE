# Seed diagnostic questions

These are prompts for testing whether corpus retrieval makes an assistant better at real vehicle troubleshooting. `tests/` must be excluded from retrieval.

## ac-001 — new compressor, still no A/C

A vehicle with a conventional A/C compressor clutch arrives after another shop installed a new compressor. Scan data shows the driver A/C request is true and the module is requesting the clutch. With the engine running, a test light at the clutch connector shows power. The compressor is being driven, but the refrigerant pressures do not develop a normal high-side/low-side separation.

What has actually been established, what remains unproven, and what should be checked next?

**What this tests:** whether the assistant can reason through request → output → clutch → compressor → refrigerant-system response instead of trusting the new part.

## ac-002 — relay as dividing line

On a conventional clutch-type A/C system, the A/C does not engage. Explain how the compressor relay/socket can be used as a dividing point between command-side and load-side faults. If bypassing the relay makes the clutch click, what does that prove and what does it still not prove?

**What this tests:** interpretation of an electrical boundary measurement rather than generic relay advice.

## brakes-001 — long pedal after hydraulic work

A vehicle has excessive brake-pedal travel after hydraulic work. One bleeder has noticeably weaker flow than the others. Give the next few tests in the order you would actually perform them. Distinguish air, a restriction, master-cylinder trouble, and a downstream circuit problem.

**What this tests:** causal localization and useful test ordering.

## brakes-002 — one wheel gets hot

After brake work, one front wheel becomes much hotter than the other as the vehicle is driven. The brake may release again after the car sits. What observations or isolation tests would distinguish mechanical drag at the wheel from trapped hydraulic pressure or an upstream restriction?

**What this tests:** whether the assistant chooses measurements that separate mechanical and hydraulic causes before recommending parts.

## engine-001 — piston will not enter bore normally

During piston installation, resistance rises sharply as the piston begins entering the bore. What should be checked before applying more force? Also state whether the current corpus contains reviewed source material for the answer or only lower-maturity notes.

**What this tests:** useful mechanical advice plus honesty about evidence maturity.

## can-001 — intermittent module communication loss

One module intermittently drops off a CAN network while the rest of the vehicle continues communicating. What measurements would you make first, and what would each one help distinguish?

**What this tests:** whether corpus retrieval eventually improves actual network diagnosis rather than producing a component list.

**Current control condition:** if the relevant corpus area remains undeveloped, retrieval should not be credited with knowledge it did not provide.

## transmission-001 — delayed engagement when hot

An automatic transmission engages normally cold but has a pronounced delay selecting Drive after it is fully warm. What information and measurements would you obtain before blaming the transmission assembly itself?

**What this tests:** a weak-corpus negative control. The assistant may know useful things from its base model, but the corpus-assisted run must not pretend the repository supplied evidence that is not there.

## evap-001 — large-leak code after cap replacement

A vehicle repeatedly sets a large-EVAP-leak fault. The fuel cap has already been replaced and the code came back. Give a short diagnostic sequence that uses the system's purge side, vent side, plumbing/filler-neck integrity, and a leak test to localize the problem instead of recommending another cap.

**What this tests:** whether retrieval turns a generic EVAP answer into an ordered system diagnosis.

## general-001 — replacement part did not fix it

A customer says: “The code pointed to the sensor, so I replaced the sensor, but the same code came back. What should I replace next?”

Give a general diagnostic answer that would remain useful across MAF, MAP, throttle-position, crank-position, pressure, and temperature sensors. Be explicit about circuit checks, plausibility against operating conditions, and what a trouble code does not prove.

**What this tests:** transfer from concrete sensor material into a reusable diagnostic habit.

## Later additions

Add questions from actual automotive conversations whenever possible. Good candidates include:

- a symptom plus one or two measurements where the next test matters more than a final diagnosis;
- a new replacement part that should not be trusted without measurement;
- an intermittent fault where static continuity is insufficient;
- a scan-data value that proves a command but not physical output;
- a case where voltage is present but the circuit cannot carry load;
- conflicting symptoms that require dividing the system at a connector, relay, hydraulic port, fuse, module, or mechanical linkage;
- contradictions between two reviewed sources;
- cases where retrieving low-maturity notes makes the answer worse.

Do not add answer keys to the retrieval corpus. If rubrics or expected observations are committed under `tests/`, exclude the entire directory from indexing.
