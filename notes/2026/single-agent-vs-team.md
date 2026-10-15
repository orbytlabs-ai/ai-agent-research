# A Single Agent and a Research Team on Equal Ceilings

A field note from Orbyt Labs Research, by Justin Bartak.

Author: Justin Bartak, ORCID [0009-0005-2615-3624](https://orcid.org/0009-0005-2615-3624), Wikidata [Q139551829](https://www.wikidata.org/wiki/Q139551829). Organization: Orbyt Labs, Wikidata [Q139551916](https://www.wikidata.org/wiki/Q139551916), https://www.orbytlabs.ai.

Version 1.0.1, content revised 2026-10-08. Measurement version 1.0.0, collected 2026-09-17.

Canonical page: https://www.orbytlabs.ai/research/single-agent-vs-team

## Claim

On 2026-09-17, the single agent resolved 1 of 6 briefs and the team resolved 0 of 6. Team retained under the pre registered rule: no.

## Measured

6 paired briefs and 12 attempts, measured 2026-09-17.

Sample: 6 briefs and 12 attempts on the same hypothetical feature.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Paired briefs | 6 | docs/research/single-agent-vs-team/runs/RESULT.json, briefs.length |
| Assigned attempts | 12 | docs/research/single-agent-vs-team/runs/RESULT.json, trials.length |
| Who performed the substantive reads | agent | docs/research/single-agent-vs-team/runs/RESULT.json, reviewer (absent means founder) |
| Human time clause | not measured: an agent read the reports (Deviations 5) | docs/research/single-agent-vs-team/runs/RESULT.json, human_time_clause |
| Single agent briefs resolved | 1 | docs/research/single-agent-vs-team/runs/RESULT.json, arrangements.single.resolved |
| Single agent accepted findings | 9 | docs/research/single-agent-vs-team/runs/RESULT.json, arrangements.single.accepted_findings |
| Single agent list price cost in USD | 7.84 | docs/research/single-agent-vs-team/runs/RESULT.json, arrangements.single.total_cost_usd |
| Single agent sessions stopped by the ceiling | 0 | docs/research/single-agent-vs-team/runs/RESULT.json, trials.sessions, executed sessions with a budget or cost ceiling stop_clause |
| Team briefs resolved | 0 | docs/research/single-agent-vs-team/runs/RESULT.json, arrangements.team.resolved |
| Team accepted findings | 16 | docs/research/single-agent-vs-team/runs/RESULT.json, arrangements.team.accepted_findings |
| Team list price cost in USD | 16.98 | docs/research/single-agent-vs-team/runs/RESULT.json, arrangements.team.total_cost_usd |
| Team sessions stopped by the ceiling | 0 | docs/research/single-agent-vs-team/runs/RESULT.json, trials.sessions, executed sessions with a budget or cost ceiling stop_clause |
| Briefs the team resolved and the single agent left open | 0 | docs/research/single-agent-vs-team/runs/RESULT.json, briefs.team_resolved_what_single_left_open |
| Team retained under the pre registered rule | no | docs/research/single-agent-vs-team/runs/RESULT.json, team_retained |
| Team preserves every single agent resolution | no | docs/research/single-agent-vs-team/runs/RESULT.json, clauses.preserves_single_resolutions |
| Team resolves a brief the single agent left open | no | docs/research/single-agent-vs-team/runs/RESULT.json, clauses.resolves_additional_brief |
| Team cost does not exceed single agent cost | no | docs/research/single-agent-vs-team/runs/RESULT.json, clauses.cost_not_increased |
| Team human time does not exceed single agent time | no | docs/research/single-agent-vs-team/runs/RESULT.json, clauses.human_minutes_not_increased |
| Registered pool in list price USD | 72.00 | docs/research/single-agent-vs-team/runs/RESULT.json, single session ceiling_usd times trials.length |
| Per attempt ceiling in list price USD | 6.00 | docs/research/single-agent-vs-team/runs/RESULT.json, single session ceiling_usd |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/single-agent-vs-team

## Method

- The unblinded result joins locked verdicts, accepted findings and session costs. The reviewer was the agent. The human time clause was not measured: an agent read the reports (Deviations 5).
- The single agent used 7.84 USD at list price with 9 accepted findings. The team used 16.98 USD at list price with 16 accepted findings.
- The team resolved 0 briefs the single agent left open. The retention rule also requires preserving every single agent resolution without increasing cost or human time. Finding count does not decide retention.

## Limitations

- A single product, a single hypothetical feature and 6 briefs. Customer outcomes and later consequences are not yet observed.
- The ceilings use CLI list price estimates. No cash moved on the subscription plan. A session stops after the call that crosses its ceiling, so a crossing call can overshoot.
- The founder did not perform the substantive reads. The reviewer was an agent of a different model family from the reports' authors, reading in a copy of the repository with the letter map and the named run directories removed, retrieving each cited source over the web. No human minutes were recorded, so the human time clause in the pre registered rule was not measured and reads as not met.

## Evidence

Every record behind this note, with a SHA-256 hash per file: https://www.orbytlabs.ai/research/single-agent-vs-team/evidence-2026-10-08/MANIFEST.json

## How to cite

Bartak, J. (2026). A Single Agent and a Research Team on Equal Ceilings. Orbyt Labs Research, measurement version 1.0.0. https://www.orbytlabs.ai/research/single-agent-vs-team

```bibtex
@misc{bartak2026singleagentvsteam,
  author    = {Bartak, J.},
  title     = {{A Single Agent and a Research Team on Equal Ceilings}},
  year      = {2026},
  publisher = {Orbyt Labs Research},
  note      = {Measurement version 1.0.0},
  url       = {https://www.orbytlabs.ai/research/single-agent-vs-team}
}
```

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

Corrections: report an error at https://www.orbytlabs.ai/contact. A corrected record is published as a new version, and its changelog names what changed.

## Changelog

- 1.0.1, content revised 2026-10-08 (patch): changed: claim; measured. Declared: presentation: dates rendered as ISO 8601; citation metadata added
- 1.0.0, content revised 2026-10-08 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
