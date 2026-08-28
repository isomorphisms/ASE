# Seed questions

These are deliberately diagnostic rather than trivia questions. `tests/` must be excluded from retrieval when they are run.

## A7-001 — request, output, clutch, compressor

A vehicle with a conventional A/C compressor clutch arrives after another shop installed a new compressor. Scan data shows the driver A/C request is true and the module is requesting the clutch. With the engine running, a test light at the clutch connector shows power. The compressor is being driven, but the refrigerant-pressure readings do not develop a normal high-side/low-side separation.

What has actually been established, what remains unproven, and what should be checked next? Do not assume the new compressor is good merely because it is new.

**Purpose:** test whether the corpus improves boundary-by-boundary diagnosis rather than parts replacement.

## A7-002 — relay as a diagnostic boundary

On a conventional clutch-type A/C system, explain how the compressor relay/socket can be used to divide the problem into command-side and load-side faults. State what a successful clutch click proves and, just as importantly, what it does **not** prove.

**Purpose:** test transfer of a diagnostic method to a generic vehicle.

## A5-001 — long or spongy brake pedal

A vehicle has excessive brake-pedal travel after hydraulic work. One bleeder appears to have weak flow. Give an efficient diagnostic sequence that distinguishes air, restriction, master-cylinder problems, and downstream circuit problems. Explain how circuit isolation at the master cylinder can help and why pedal feel by itself is not a complete bleeding oracle.

**Purpose:** test causal localization rather than a generic brake-system checklist.

## A5-002 — hot wheel after brake repair

After brake work, one front wheel becomes abnormally hot and the pedal behavior changes as the vehicle is driven. Before replacing another part, what observations and isolation tests would you use to distinguish a mechanically dragging brake from trapped hydraulic pressure or an upstream hydraulic restriction?

**Purpose:** test whether the corpus helps connect a symptom to a sequence of discriminating tests.

## A1-001 — source-maturity control

During piston installation, resistance rises sharply as the piston enters the bore. What should be checked before applying more force? Separate general engine-building knowledge from anything that can honestly be claimed to have been learned from reviewed material in the current ASE corpus.

**Purpose:** A1 currently contains useful study notes whose own status says they were grouped from titles/metadata rather than extracted from reviewed videos. A RAG answer should not launder those notes into transcript-derived evidence.

## A2-001 — empty-corpus negative control

An automatic transmission has delayed engagement only after it is fully warm. Give a diagnostic approach, and explicitly state whether the current ASE repository supplied useful A2 evidence for your answer.

**Purpose:** the A2 branch currently has no developed topic corpus. The RAG condition should not manufacture repository support or show a fake gain merely because retrieval was enabled.

## A6-001 — empty-corpus negative control

A vehicle intermittently loses communication with one module on the CAN network while the rest of the network continues to operate. Describe a sensible diagnostic approach, and explicitly state whether the current A6 branch provided evidence for it.

**Purpose:** another negative control for false attribution when the target exam branch is undeveloped.

## Later additions

As transcript-reviewed material grows, add paired questions that test:

- exact source recall versus transfer to a changed vehicle or symptom;
- choosing the next measurement from several plausible choices;
- identifying what a measurement rules out and what it cannot rule out;
- contradictions between two sources;
- uncertainty when the transcript is incomplete;
- whether retrieval can make an answer worse by surfacing low-maturity notes.

Do not add an answer key to the retrieval corpus. If answer keys or grading rubrics are committed under `tests/`, the retrieval index must exclude the entire directory.
