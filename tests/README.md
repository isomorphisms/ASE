# Assistant automotive competence tests

This directory tests whether the corpus makes an AI assistant better at real automotive diagnosis and explanation. It is not an ASE exam-prep test suite.

## Core experiment

For each question, run the **same model twice** with the same system prompt, user question, decoding settings, and tool permissions.

1. **Baseline** — answer without ASE corpus retrieval.
2. **Corpus-assisted** — answer with retrieval from the automotive corpus.

The useful measurement is the paired difference.

## Keep the comparison clean

- Exclude `tests/` from retrieval. Questions, grading notes, and answer keys are not automotive evidence.
- Record the exact model/version and relevant settings.
- Record the exact corpus commits or branch heads.
- Save the retrieved chunks, not just the final answer.
- Do not give the corpus-assisted run extra browsing, tools, hints, or a different prompt.
- Prefer questions that look like real troubleshooting conversations: symptoms, previous repairs, scan data, electrical measurements, pressures, temperatures, noises, intermittent behavior, and requests for the next test.
- Avoid trivia and exam-question mimicry unless it tests a diagnostic concept that transfers to real work.
- Include weak-corpus controls. Retrieval should be able to produce no gain when the repository contains nothing useful.

## Source maturity

Every retrieved artifact should make its evidence level clear. At minimum distinguish:

- URL/title/playlist metadata only;
- notes not derived from reviewed source content;
- partial source review;
- transcript/captions reviewed end to end;
- corroborated against service information or another strong source.

A model should never launder metadata or generic notes into claims that a source was actually reviewed.

## What to save for every run

- question ID and exact user wording;
- model/version and settings;
- baseline answer;
- corpus commit(s) or branch head(s);
- retrieved file paths and chunks;
- corpus-assisted answer;
- grading result;
- grader notes, including any new hallucination introduced by retrieval.

## Grading dimensions

Use a small ordinal scale.

1. **Technical correctness** — are the claims right?
2. **Causal diagnosis** — does the answer reason from the symptoms rather than list generic possibilities?
3. **Next-test quality** — does it choose a discriminating measurement or inspection?
4. **Boundary reasoning** — does it say what a measurement proves and what remains unproven?
5. **Parts-cannon resistance** — does it avoid replacing components before localizing the fault?
6. **Evidence discipline** — does it separate observation, inference, suspicion, and source maturity?
7. **Transfer** — can it use a learned diagnostic pattern on a different vehicle or system architecture?
8. **Calibration** — does it avoid fake certainty?

A strong corpus-assisted answer should be not merely longer, but more useful: fewer irrelevant branches, better test ordering, clearer interpretation of measurements, and fewer unjustified replacements.

## Suggested record layout

```text
tests/
  README.md
  questions.md
  runs/
    <question-id>/
      baseline.md
      corpus.md
      retrieval.md
      grade.md
```

Do not commit fake runs. `runs/` should contain actual model outputs and retrieval traces only.
