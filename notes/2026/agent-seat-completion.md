# What an Agent Seat Actually Completes

A field note from Orbyt Labs Research, by Justin Bartak.

Version 1.0.0, content revised 2026-09-26. Measurement version 1.10.0, collected 2026-09-11 to 2026-09-26.

Canonical page: https://www.orbytlabs.ai/research/agent-seat-completion

## Claim

Across 106 recorded runs of 9 AI agent seats operating Orbyt Labs between Jul, 21 2026 and Sep, 26 2026, 91 passed the workflow's completion gate (86%), 15 were refused by it, and 73 files an agent changed outside its lane were erased before commit; the frozen Q3 2026 baseline was 80.0% on 30 runs.

## Measured

106 runs across 9 seats, Jul, 21 2026 to Sep, 26 2026, read Sep, 26 2026.

Sample: 106 recorded runs of 9 seats in one organization.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Recorded runs | 106 | public/autonomy-ledger.json, current.perSeat, sum of runs |
| Seats with a run ledger | 9 | same file, perSeat length |
| Runs whose output passed the completion gate | 91 | same file, sum of completions |
| Completion rate | 86% | completions / runs |
| Runs the guards refused | 15 | same file, sum of failures |
| Rows where no run happened (skip, halted, infrastructure) | 4 | same file, excluded from both sides of the rate |
| Files an agent changed outside its lane, erased before commit | 73 | same file, sum of discards |
| First recorded run | 21 July 2026 | same file, earliest firstRun |
| Last recorded run | 26 September 2026 | same file, latest lastRun |
| Frozen Q3 2026 baseline completion rate | 80.0% | same file, baseline.totals (frozen 2026-08-11, never regenerated) |
| Runs in the frozen baseline | 30 | same file, baseline.totals.runs |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/agent-seat-completion

## Method

- Every figure is read from the organization's committed per-seat run ledger (docs/org/stats/&lt;seat&gt;.jsonl, aggregated into public/autonomy-ledger.json by generate-stats.cjs at every commit). A run is one scheduled or dispatched execution of a seat's workflow; the ledger row is written by the workflow itself, not by the agent.
- Completion means the run's output survived the workflow's completion gate (a check of how the agent's run ended: its exit, its result and its turns against its cap), the guard gauntlet, and the commit. Since decision D-0061, in September 2026, the completion line a seat prints is recorded as its claim rather than required; runs before that decision also had to print it. A run whose output the guards refused is a failure. Rows recording that no run happened (skip: nothing to do; halted: a kill switch; infrastructure: the org could not run) are counted separately and sit on neither side of the rate.
- A discard is a file the agent changed outside its effective keep set, erased before the commit rather than shipped. It is an aggregate counter across runs and a different unit from a failure: it says the agent reached outside its lane, not that its work was rejected.
- The baseline is the ledger as first published on Aug, 11 2026 (30 runs, 80.0% completion), frozen on purpose and never regenerated, so every later reading is measured against the same origin rather than against a moving average.
- Failures are printed, never netted out. The rate is completions divided by runs, and both numbers are on the page.

## Limitations

- One organization, nine seats, one workflow shape. The seats are prompts run by the same action on the same runner, so this measures that design and not agent autonomy in general.
- Passing the completion gate is not the same as the output being good. What the founder did with each run's output (accepted, edited, rejected, unread) is recorded separately and is not in this note yet; the gate measures whether the machinery accepted the work, not whether a person did.
- Small numbers. Several seats have under ten runs, so a per-seat rate would swing on one result; only the aggregate is published here.
- The ledger records what the workflow wrote. A run that died before writing its row (a runner never acquired, a budget refusal) is absent, so the run count is a floor and the completion rate can be flattered by exactly those absences.
- No trend is claimed from the baseline comparison. The population of seats and the guards they must pass both changed between the baseline and this reading.

## Cite this

Bartak, J. (2026). What an Agent Seat Actually Completes. Orbyt Labs Research, version 1.10.0. https://www.orbytlabs.ai/research/agent-seat-completion

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

## Changelog

- 1.0.0, content revised 2026-09-26 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
