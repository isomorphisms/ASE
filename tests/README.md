# ASE corpus tests

This directory tests whether the repository actually improves answers, rather than merely accumulating links and prose.

## Core experiment

For each test question, run the **same model twice** with the same system prompt, question, decoding settings, and tool permissions.

1. **Baseline** — no ASE repository material is supplied or retrieved.
2. **RAG-assisted** — the model may retrieve from the ASE study corpus relevant to the question.

This is a retrieval comparison, not a claim that the model has been trained or fine-tuned on the repository.

## Keep the comparison clean

- Exclude `tests/` from the retrieval corpus. Questions, grading notes, and answer keys must not become RAG evidence.
- Record the exact model/version and relevant inference settings.
- Record the exact repository commit(s) or branch head(s) used as the corpus.
- Save the retrieved chunks, not just the final RAG answer. A better answer is not evidence that retrieval caused the improvement unless we can see what was retrieved.
- Do not silently give the RAG run extra tools, browsing, hints, or a different prompt.
- Prefer diagnostic or transfer questions that require connecting observations, not questions that can be answered by copying one sentence.
- Include some questions for weak or empty branches. A good test suite should be able to show **no improvement** when the corpus has nothing useful to contribute.

## Source maturity matters

Repository material should carry an evidence status. At minimum distinguish:

- raw URL/title/playlist metadata;
- notes not derived from a reviewed source;
- partial source review;
- transcript/caption reviewed end to end;
- corroborated against service information or another strong source.

RAG results should report which level they actually relied on. A polished summary built only from video titles is not equivalent to transcript-reviewed material.

## What to save for every run

A test record should contain:

- question ID and question text;
- target ASE area/topic;
- model/version and settings;
- baseline answer;
- corpus branch/commit;
- retrieved file paths and chunks;
- RAG-assisted answer;
- grading result;
- grader notes, including any new hallucination introduced by retrieval.

## Grading dimensions

Use a small ordinal scale for each dimension rather than pretending to have precision we do not have.

1. **Technical correctness** — are the claims right?
2. **Diagnostic ordering** — does the answer isolate causes efficiently instead of firing a parts cannon?
3. **Evidence discipline** — does it distinguish observed facts, inference, and unresolved possibilities?
4. **Coverage** — does it notice the important branches of the diagnosis?
5. **Transfer** — can it apply the material to a new but structurally similar case?
6. **Calibration** — does it avoid claiming more certainty than the corpus supports?

The useful result is the paired difference, plus the retrieved evidence that explains that difference.

## Suggested record layout

```text
tests/
  README.md
  questions.md
  runs/
    <question-id>/
      baseline.md
      rag.md
      retrieval.md
      grade.md
```

Do not commit fake runs. `runs/` should contain actual model outputs and retrieval traces when experiments are performed.
