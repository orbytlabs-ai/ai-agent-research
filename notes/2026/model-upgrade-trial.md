# A Model Upgrade on a Frozen Dependency Review

A field note from Orbyt Labs Research, by Justin Bartak.

Version 1.0.0, content revised 2026-10-03. Measurement version 1.1.0, collected 2026-09-17 to 2026-10-03.

Canonical page: https://www.orbytlabs.ai/research/model-upgrade-trial

## Claim

On Oct, 3 2026, an agent reviewer accepted 3 of 3 reports generated with Codex configured for gpt-6-astra on Orbyt Labs' frozen dependency review. A subsequent trace check left execution claims unverified in 3 reports. This does not establish a model-upgrade win.

## Measured

Original comparison: Sep, 17 2026. Astra follow-up: Oct, 3 2026.

Sample: 3 Astra follow-up attempts; the earlier comparison retains 3 runs per Sonnet model.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Runs per model | 3 | docs/research/model-upgrade-trial/runs/RESULT.json, trials per model |
| Who performed the substantive reads | agent | docs/research/model-upgrade-trial/runs/RESULT.json, reviewer (absent means founder) |
| Review time clause | not measured: an agent read the reports (Deviations 4) | docs/research/model-upgrade-trial/runs/RESULT.json, review_time_clause |
| Current model | claude-sonnet-4-5-20250929 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.model |
| Current reports accepted by the reviewer | 0 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.human_verdict |
| Current mechanical rejections | 3 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.mechanical_verdict |
| Current unsupported claims found by the reviewer | 12 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.unsupported_claims |
| Current median elapsed minutes | 2.6412833333333334 | docs/research/model-upgrade-trial/runs/RESULT.json, median trials.elapsed_ms / 60000 |
| Current median output tokens | 6513 | docs/research/model-upgrade-trial/runs/&lt;id&gt;/RUN.json, median usage.output_tokens |
| Candidate model | claude-sonnet-5 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.model |
| Candidate reports accepted by the reviewer | 0 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.human_verdict |
| Candidate mechanical rejections | 3 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.mechanical_verdict |
| Candidate unsupported claims found by the reviewer | 14 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.unsupported_claims |
| Candidate median elapsed minutes | 5.590933333333333 | docs/research/model-upgrade-trial/runs/RESULT.json, median trials.elapsed_ms / 60000 |
| Candidate median output tokens | 37456 | docs/research/model-upgrade-trial/runs/&lt;id&gt;/RUN.json, median usage.output_tokens |
| Files changed outside the report lane | 0 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.lane_violations |
| Candidate wins under the pre registered rule | no | docs/research/model-upgrade-trial/runs/RESULT.json, candidate_wins |
| Equal review totals leave the model unchanged | no | docs/research/model-upgrade-trial/runs/RESULT.json, equal_changes_nothing |
| Missing applicable findings | 0 | docs/research/model-upgrade-trial/runs/RESULT.json, trials.missing_findings |
| Block 1 run date, America/Chicago | 2026-09-17 | docs/research/model-upgrade-trial/runs/&lt;id&gt;/RUN.json, earliest startedAt |
| Astra follow-up date, America/Chicago | 2026-10-03 | docs/research/model-upgrade-trial/astra-follow-up/runs/&lt;id&gt;/RUN.json, earliest startedAt |
| Astra follow-up requested model | gpt-6-astra | docs/research/model-upgrade-trial/astra-follow-up/runs/&lt;id&gt;/RUN.json, model_requested |
| Astra follow-up attempts | 3 | docs/research/model-upgrade-trial/astra-follow-up/runs/RESULT.json, trials.length |
| Astra attempts with successful execution and report lane | 3 | docs/research/model-upgrade-trial/astra-follow-up/runs/&lt;id&gt;/RUN.json, success |
| Astra reports accepted by the agent reviewer | 3 | docs/research/model-upgrade-trial/astra-follow-up/runs/RESULT.json, trials.substantive_verdict |
| Astra reports rejected by the original mechanical detector | 3 | docs/research/model-upgrade-trial/astra-follow-up/runs/RESULT.json, trials.mechanical_verdict |
| Astra applicable findings missing in the substantive read | 0 | docs/research/model-upgrade-trial/astra-follow-up/runs/RESULT.json, trials.missing_findings |
| Astra unsupported claims found by the agent reviewer | 0 | docs/research/model-upgrade-trial/astra-follow-up/runs/RESULT.json, trials.unsupported_claims |
| Astra files changed outside the report lane | 0 | docs/research/model-upgrade-trial/astra-follow-up/runs/&lt;id&gt;/RUN.json, lane_violations |
| Astra reported tokens across report attempts, excluding setup and review | 844543 | docs/research/model-upgrade-trial/astra-follow-up/runs/&lt;id&gt;/RUN.json, tokens; cached input is a subset of input |
| Astra median report execution minutes | 5.08 | docs/research/model-upgrade-trial/astra-follow-up/runs/&lt;id&gt;/RUN.json, median elapsed_ms / 60000 |
| Astra substantive reviewer model | claude-sonnet-5 | docs/research/model-upgrade-trial/astra-follow-up/runs/RESULT.json, reviewer_model |
| Astra reports with execution claims unverified in the saved trace | 3 | docs/research/model-upgrade-trial/astra-follow-up/runs/OPERATOR-REVIEW.json, runs.status |
| Astra provider identity in CLI events | not reported; requested configuration recorded | docs/research/model-upgrade-trial/astra-follow-up/runs/&lt;id&gt;/RUN.json, observed_models |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/model-upgrade-trial

## Method

- The Astra follow-up used the original packet, task prompt, answer key and substantive acceptance rule. Each attempt began in a fresh directory, and file hashes checked the frozen inputs and permitted report lane.
- Codex requested gpt-6-astra with high reasoning effort. Its arguments requested disabled network access, web search, apps and subagents. Provider identity in its CLI events: not reported; requested configuration recorded.
- The substantive reviewer was a fresh claude-sonnet-5 agent session. It received shuffled report letters, the frozen evidence and the acceptance rule in a separate reading directory. Verdicts were locked before the letter map was opened.
- The reviewer recorded 0 missing applicable findings and 0 unsupported claims. Successful executions with a report and no write-lane violation: 3 of 3. Files changed outside that lane: 0.
- On Sep, 17 2026, the original comparison's reviewer accepted 0 of 3 claude-sonnet-4-5-20250929 reports and 0 of 3 claude-sonnet-5 reports. Its recorded candidate win remains no; those reports were not rerun or rescored for this follow-up.

## Limitations

- One task at one organization, with 3 Astra attempts. The historical Sonnet runs are context, not a contemporaneous control. This does not establish that one model is better across other tasks or companies.
- Codex and Claude use different built-in instructions and tool implementations. This follow-up used Codex shell and patch tools, high reasoning effort and a process timeout; the original comparison used Claude file tools and a turn limit. A difference cannot be attributed to the model alone.
- The reviewer also changed: an OpenAI agent reviewed the original Claude reports, while a Claude agent reviewed the Astra reports. Differences between the recorded verdicts can reflect the reviewer as well as the report author.
- The founder did not perform the substantive reads. Human review minutes and the original attention-saving requirement were not measured. Agent acceptance does not authorize replacing the seat's model.
- The unchanged mechanical detector has known formatting false positives. Its rejection count is reported separately from the agent's substantive verdicts. An agent reviewer can also make mistakes.
- After the review was locked, the operator found that 3 reports described a failed subagent launch whose call and error were absent from the saved CLI events. The reviewer did not flag those execution claims. They remain unverified; their absence from this event format does not prove fabrication. The locked scores are retained, and the runs are not presented as fully verified autonomous operation.
- Token totals are the Codex CLI's reported input plus output for report attempts only, with cached input counted once. They exclude setup and review and are not a cross-provider cost or quota comparison.
- The temporary workspaces restrict writes and network access; they are not filesystem jails. The task prohibits outside reads, and the recorded tool activity must be checked separately from file hashes.
- The first compatibility control failed before reaching the model because Codex could not initialize inside the outer sandbox. That attempt is retained. A permitted infrastructure retry passed the control before report generation began.
- A second comparison block, the current model against claude-opus-5-5 on the same frozen packet under the same rule, is pre registered and partly run, and none of its reports has been read, so it has no result yet.

## Cite this

Bartak, J. (2026). A Model Upgrade on a Frozen Dependency Review. Orbyt Labs Research, version 1.1.0. https://www.orbytlabs.ai/research/model-upgrade-trial

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

## Changelog

- 1.0.0, content revised 2026-10-03 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
