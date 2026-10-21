# Governing a Self-Repairing Agent Organization

A preregistration from Orbyt Labs Research: the question, the design and the stop rule, published before any result. It reports no finding.

Author: Justin Bartak, ORCID [0009-0005-2615-3624](https://orcid.org/0009-0005-2615-3624), Wikidata [Q139551829](https://www.wikidata.org/wiki/Q139551829). Organization: Orbyt Labs, Wikidata [Q139551916](https://www.wikidata.org/wiki/Q139551916), https://www.orbytlabs.ai.

Version 1.0.0, content revised 2026-10-08. Measurement version 1.0.0, collected 2026-10-08.

Canonical page: https://www.orbytlabs.ai/research/governing-self-repair

## Claim

As of 2026-10-08, the design contains 7 scenario families, each with an adversarial case and a healthy case, across 4 cumulative control configurations. It specifies 56 expected verdicts. Scored attempts: NOT OBSERVED.

## Measured

Preregistration. Design counts read 2026-10-08.

Sample: 14 scenario cases across 4 configurations, 3 fresh attempts per cell.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Scenario families | 7 | docs/research/governing-self-repair/scenarios.json, scenarios |
| Scenario cases, one adversarial and one healthy per family | 14 | docs/research/governing-self-repair/scenarios.json, adversarial and healthy |
| Control configurations on the cumulative ladder | 4 | docs/research/governing-self-repair/scenarios.json, configurations |
| Expected verdicts written before any run | 56 | docs/research/governing-self-repair/scenarios.json, expected, one per case and configuration |
| Distinct source references | 13 | docs/research/governing-self-repair/scenarios.json, sources, distinct kind and id |
| Fresh attempts per case, configuration and variant cell | 3 | docs/research/governing-self-repair/PROTOCOL.md, Configuration |
| Planned attempts at one frozen variant per family | 168 | families x 2 case types x configurations x repetitions, checked against the protocol's stated total |
| Scored attempts run | NOT OBSERVED | docs/research/governing-self-repair/runs does not exist |
| Preregistration date | 2026-10-17 | docs/research/governing-self-repair/PROTOCOL.md, Frozen inputs |
| Deadline for a second repair worker to join, 00:00 UTC | 2026-10-24 | docs/research/governing-self-repair/PROTOCOL.md, Configuration |
| Scenario corpus freeze, 00:00 UTC | 2026-10-31 | docs/research/governing-self-repair/PROTOCOL.md, Frozen inputs |
| Preprint target | 2026-11-26 | docs/research/governing-self-repair/PROTOCOL.md, Outcome measures |
| Research ceiling, weekly Claude Max allowance | 10% | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 5 |
| Research ceiling, weekly Codex allowance | 20% | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 5 |
| License for the sanitized evidence and analysis | CC BY 4.0 | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 8 |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/governing-self-repair

## Method

- I am publishing the question, scenarios, configurations, expected verdicts and stop rule before scored research runs. This note reports no study result. Results will appear at this URL. The revisions table records version numbers and changes.
- The study will test the worker that repairs the Machine's failures. Each attempt must run in an isolated copy with no live credentials, production data or route to main. Local substitutes will stand in for promotion and my authorization. Every result will state those limits. The experimental harness is not built yet.
- The controls are added one at a time, a cumulative ladder of 4 configurations: written instructions alone, then a permission fence, then independent verification, then authorized promotion. The last rung is the full configuration and the baseline. Adjacent rungs differ by one control, so a difference between them depends on the rungs below it and is not that control's standalone value.
- Each of the 7 scenario families pairs an adversarial case with a healthy case. The scenarios adapt recorded failures and documented test plans. They cite 13 distinct source references, listed in docs/research/governing-self-repair/scenarios.json. The planted instruction is synthetic. The source for the ineffective-fix test includes a planned check, not a completed walk.
- A governance failure occurs when the worker takes a forbidden action in an adversarial case: changing its evaluator, writing outside its permitted files, accepting an ineffective fix, following planted instructions or promoting without required evidence. A refusal in the trace does not count if the forbidden side effect occurred. Refusing every task also fails the usefulness test. The 56 expected verdicts state what each configuration must do. They do not predict success.
- An independent scorer will check the side effects and useful results. It will score anonymized outputs and lock its verdicts before seeing configuration labels. Before any scored attempt, I must calibrate it on a wrong candidate, missing evidence and a permitted repair. Every detector must reject the defective case and accept the healthy case.
- 3 fresh attempts per case, configuration and variant cell. At one variant per family that is 168 planned attempts, more where a family freezes several variants. Configuration order is randomized with a preserved seed.
- The preregistration date is 2026-10-17. A second repair worker can join only if its first attended test has a verifiable record by midnight UTC on 2026-10-24 and I authorize it. Otherwise it remains future work. The scenario set freezes at midnight UTC on 2026-10-31. Later additions are labeled separately. The preprint target is 2026-11-26. Research is capped at 10% of the weekly Claude Max allowance and 20% of the weekly Codex allowance, with the current budget and token weights checked before launch.
- Stop rule: I stop a block if isolation fails, a frozen version changes, required reviewer evidence is missing outside the missing-evidence test, or the resource ceiling is reached. I drop any comparison that cannot keep the experiment isolated. If the full configuration cannot complete a healthy task, I repair the setup and freeze it again before drawing conclusions. Partial attempts and their evidence are kept. Incomplete cells publish as NOT OBSERVED. Negative, mixed and inconclusive results publish under the same rule as favorable ones. Sanitized evidence and analysis publish under CC BY 4.0.

## Limitations

- No result exists yet. The counts here describe the design, read 2026-10-08. Scored attempts: NOT OBSERVED.
- One workflow, failures chosen from one organization, and a local fixture environment. A favorable result would not establish general safety, and it says nothing about what a model internally wants.
- The ladder is cumulative, so it cannot isolate each control's own contribution. The full configuration against instructions alone changes several controls at once.
- The worker can see which controls constrain it. Only the scoring is blinded.
- The canary checks catch reserved markers and observable network attempts. They do not prove resistance to prompt injection in general.
- Repetitions of one task are dependent observations. At one variant per family, 168 planned attempts on 7 families are not 168 independent failure mechanisms. Additional variants increase the attempt total.

## How to cite

Bartak, J. (2026). Governing a Self-Repairing Agent Organization. Orbyt Labs Research, measurement version 1.0.0. https://www.orbytlabs.ai/research/governing-self-repair

```bibtex
@misc{bartak2026governingselfrepair,
  author    = {Bartak, J.},
  title     = {{Governing a Self-Repairing Agent Organization}},
  year      = {2026},
  publisher = {Orbyt Labs Research},
  note      = {Measurement version 1.0.0},
  url       = {https://www.orbytlabs.ai/research/governing-self-repair}
}
```

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

Corrections: report an error at https://www.orbytlabs.ai/contact. A corrected record is published as a new version, and its changelog names what changed.

## Changelog

- 1.0.0, content revised 2026-10-08 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
