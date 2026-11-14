# What an Agent Seat Actually Completes

A field note from Orbyt Labs Research, by Justin Bartak.

Author: Justin Bartak, ORCID [0009-0005-2615-3624](https://orcid.org/0009-0005-2615-3624), Wikidata [Q139551829](https://www.wikidata.org/wiki/Q139551829). Organization: Orbyt Labs, Wikidata [Q139551916](https://www.wikidata.org/wiki/Q139551916), https://www.orbytlabs.ai.

Version 1.1.0, content revised 2026-11-12. Measurement version 2.0.0, collected 2026-09-11 to 2026-11-12.

Canonical page: https://www.orbytlabs.ai/research/agent-seat-completion

## Claim

Across 209 recorded runs of 11 AI agent seats operating Orbyt Labs between 2026-07-21 and 2026-11-11, 192 passed the workflow's completion gate (92%), 17 were refused by it, and 135 paths were reset before commit: 112 were the seat's own proposed lesson, held back by the closed lessons gate, and 23 fell outside anything the run may keep; the frozen Q3 2026 baseline was 80.0% on 30 runs.

## Measured

209 runs across 11 seats, 2026-07-21 to 2026-11-11, read 2026-11-12.

Sample: 209 recorded runs of 11 seats in one organization.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Recorded runs | 209 | public/autonomy-ledger.json, current.perSeat, sum of runs |
| Seats with a run ledger | 11 | same file, perSeat length |
| Runs whose output passed the completion gate | 192 | same file, sum of completions |
| Completion rate | 92% | completions / runs |
| Runs the guards refused | 17 | same file, sum of failures |
| Rows where no run happened (skip, halted, infrastructure) | 15 | same file, excluded from both sides of the rate |
| Paths reset before commit, outside the run's effective keep set | 135 | same file, sum of discards (paths as git status lists them; a rename counts its destination only) |
| Of those, the seat's own proposed lesson, held by the closed lessons gate | 112 | same file, sum of lessonsGated (one path per gated run) |
| Of those, paths outside anything the run may keep | 23 | discards minus heldLessons |
| First recorded run | 2026-07-21 | same file, earliest firstRun |
| Last recorded run | 2026-11-11 | same file, latest lastRun |
| Frozen Q3 2026 baseline completion rate | 80.0% | same file, baseline.totals (frozen 2026-08-11, never regenerated) |
| Runs in the frozen baseline | 30 | same file, baseline.totals.runs |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/agent-seat-completion

## Method

- Every figure is read from the organization's committed per-seat run ledger (docs/org/stats/&lt;seat&gt;.jsonl, aggregated into public/autonomy-ledger.json by generate-stats.cjs at every commit). A run is one scheduled or dispatched execution of a seat's workflow; the ledger row is written by the workflow itself, not by the agent.
- Completion means the run's output survived the workflow's completion gate (a check of how the agent's run ended: its exit, its result and its turns against its cap), the guard gauntlet, and the commit. Since decision D-0061, in September 2026, the completion line a seat prints is recorded as its claim rather than required; runs before that decision also had to print it. A run whose output the guards refused is a failure. Rows recording that no run happened (skip: nothing to do; halted: a kill switch; infrastructure: the org could not run) are counted separately and sit on neither side of the rate.
- Three words carry the discard count. The lane is the set of paths a seat's agent may write while it runs, declared in the seat's spec (fence.lane_paths). The keep set is the narrower set the workflow commits from the run: the seat's keep paths, plus its proposed lesson only once the ladder opens the lessons gate. A held lesson is that proposed lesson while the gate is closed: inside the lane, outside the keep set, so it is reset and counted. A discard is any path the run changed outside its effective keep set (the book journal excepted), counted from git status before the reset. It is an aggregate counter across runs and a different unit from a failure, and it counts paths, not who wrote them.
- The baseline is the ledger as first published on 2026-08-11 (30 runs, 80.0% completion), frozen on purpose and never regenerated, so every later reading is measured against the same origin rather than against a moving average.
- Failures are printed, never netted out. The rate is completions divided by runs, and both numbers are on the page.

## Limitations

- One organization, nine seats, one workflow shape. The seats are prompts run by the same action on the same runner, so this measures that design and not agent autonomy in general.
- Passing the completion gate is not the same as the output being good. What the founder did with each run's output (accepted, edited, rejected, unread) is recorded separately and is not in this note yet; the gate measures whether the machinery accepted the work, not whether a person did.
- Small numbers. Several seats have under ten runs, so a per-seat rate would swing on one result; only the aggregate is published here.
- The ledger records what the workflow wrote. A run that died before writing its row (a runner never acquired, a budget refusal) is absent, so the run count is a floor and the completion rate can be flattered by exactly those absences.
- No trend is claimed from the baseline comparison. The population of seats and the guards they must pass both changed between the baseline and this reading.
- A reset path outside the keep set is not proof an agent wrote outside its lane. The ledger records the count, not the path or its writer: a workflow step can change a file before the agent starts, and a tool the agent runs can leave one behind. Where a run's transcript or log survives, the changelog's 2026-11-12 correction names what it shows.

## How to cite

Bartak, J. (2026). What an Agent Seat Actually Completes. Orbyt Labs Research, measurement version 2.0.0. https://www.orbytlabs.ai/research/agent-seat-completion

```bibtex
@misc{bartak2026agentseatcompletion,
  author    = {Bartak, J.},
  title     = {{What an Agent Seat Actually Completes}},
  year      = {2026},
  publisher = {Orbyt Labs Research},
  note      = {Measurement version 2.0.0},
  url       = {https://www.orbytlabs.ai/research/agent-seat-completion}
}
```

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

Corrections: report an error at https://www.orbytlabs.ai/contact. A corrected record is published as a new version, and its changelog names what changed.

## Changelog

- 1.1.0, content revised 2026-11-12 (minor): changed: citation; claim; collection end; description; limitations; measured; measurement version from 1.10.0 to 2.0.0; measurement "Recorded runs" from 106 to 209; measurement "Seats with a run ledger" from 9 to 11; measurement "Runs whose output passed the completion gate" from 91 to 192; measurement "Completion rate" from 86% to 92%; measurement "Runs the guards refused" from 15 to 17; measurement "Rows where no run happened (skip, halted, infrastructure)" from 4 to 15; measurement "Paths reset before commit, outside the run's effective keep set" added: 135; measurement "Of those, the seat's own proposed lesson, held by the closed lessons gate" added: 112; measurement "Of those, paths outside anything the run may keep" added: 23; measurement "Last recorded run" from 2026-09-26 to 2026-11-11; measurement "Files an agent changed outside its lane, erased before commit" removed; method; published on; revision date from 2026-09-26 to 2026-11-12; sample size
- 1.0.1, content revised 2026-09-26 (patch): changed: claim; measured; measurement "First recorded run" from 21 July 2026 to 2026-07-21; measurement "Last recorded run" from 26 September 2026 to 2026-09-26; method. Declared: presentation: dates rendered as ISO 8601; citation metadata added
- 1.0.0, content revised 2026-09-26 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
