# The Cache-Read Tax

A field note from Orbyt Labs Research, by Justin Bartak.

Version 1.0.0, content revised 2026-09-26. Measurement version 1.23.0, collected 2026-08-27 to 2026-09-26.

Canonical page: https://www.orbytlabs.ai/research/agent-token-economics

## Claim

Across 344 AI agent sessions and 45,876 turns measured on Sep, 26 2026, cache reads accounted for 78.1% of cost-weighted token spend and generated output for 10.6%, against an average of 341,348 tokens of context re-read on every single turn.

## Measured

344 sessions and 45,876 turns, measured Sep, 26 2026.

Sample: 344 sessions, 45,876 turns, one organization.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Sessions measured | 344 | node packages/collective/src/token-efficiency.mjs --json |
| Turns measured | 45,876 | same run |
| Average context re-read per turn | 341,348 tokens | same run, avgCtx |
| Cost-weighted spend: cache read | 78.1% | output 5x, cache-write 1.25x, cache-read 0.1x vs base input |
| Cost-weighted spend: cache write | 11.3% | same weighting |
| Cost-weighted spend: generated output | 10.6% | same weighting |
| Generated output by RAW token count | 0.27% | unweighted counts, the misleading figure |
| Worst single session, cost-weighted burn | 170,298,489 | same run, session c653d1f1 |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/agent-token-economics

## Method

- Every figure is one run of the repository's own measurement tool over its local agent session transcripts, read on the date shown. Nothing is estimated and nothing is carried forward from an earlier measurement.
- Cost weighting is applied because the raw counts answer a different question than the one that matters. Generated output is weighted 5x, cache writes 1.25x and cache reads 0.1x against base input, reflecting how those token classes are actually priced.
- The headline is the gap between two correct measurements of the same data. By raw count, generated output is 0.27% of tokens, which reads as noise and suggests that shortening what an agent writes is pointless. Cost-weighted, it is 10.6%, which is not noise. Both numbers are true; only one of them describes the bill.
- This organization's own always-loaded engineering guidance carried the raw-count framing and drew the conclusion that optimizing output addresses a third of a percent of the problem. That conclusion does not survive weighting, and the measurement tool now says so in its own output.
- Context re-read dominates under both measurements, which is the finding that holds either way: an agent turn pays for the whole conversation so far, every time, so cost scales with context size multiplied by turn count rather than with anything the agent produces.

## Limitations

- One organization's sessions on one tool. Session shapes differ enormously between teams, and a team that clears context aggressively would produce a very different distribution.
- A reading on the date shown. The tool also grades this corpus against thresholds this project set for itself, and a grade is a comparison against thresholds this project set for itself, not an industry benchmark.
- The weighting factors are the ones this project uses. They approximate a real price list but they are not a quotation, and a different weighting moves the 10.6% figure.
- Cost-weighted share is not the same as opportunity. Output being 10.6% of spend does not establish that shortening output is the most effective available saving; it only refutes the claim that it is negligible.
- No causal claim is made. This measures where tokens went, not which practices caused it.

## Cite this

Bartak, J. (2026). The Cache-Read Tax. Orbyt Labs Research, version 1.23.0. https://www.orbytlabs.ai/research/agent-token-economics

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

## Changelog

- 1.0.0, content revised 2026-09-26 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
