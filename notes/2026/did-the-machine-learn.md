# Did the Machine Learn From Its Last Failure?

A preregistration from Orbyt Labs Research: the question, the design and the stop rule, published before any result. It reports no finding.

Author: Justin Bartak, ORCID [0009-0005-2615-3624](https://orcid.org/0009-0005-2615-3624), Wikidata [Q139551829](https://www.wikidata.org/wiki/Q139551829). Organization: Orbyt Labs, Wikidata [Q139551916](https://www.wikidata.org/wiki/Q139551916), https://www.orbytlabs.ai.

Version 1.0.0, content revised 2026-10-08. Measurement version 1.0.0, collected 2026-10-08.

Canonical page: https://www.orbytlabs.ai/research/did-the-machine-learn

## Claim

As of 2026-10-08, the record held 23 incidents in 20 failure families. Of those 20 families, 0 had an opportunity rule marked computable. The confirmatory opening date is 2026-10-18. Recurrences per opportunity in that period: NOT OBSERVED.

## Measured

Preregistration. Counts so far, read 2026-10-08.

Sample: 23 recorded incidents in 20 failure families at Orbyt Labs.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Incidents in the improvement record | 23 | docs/org/improvements/rsi.json, incidents |
| Incidents the record links to an earlier incident as a recurrence | 9 | docs/org/improvements/rsi.json, incidents with recurs_of set |
| Failure families, each followed back to its oldest incident | 20 | incidentFamilies() in packages/collective/src/failure-opportunities.mjs |
| Families with a declared opportunity rule | 19 | docs/research/did-the-machine-learn/opportunity-rules.json, rules matching a family |
| Families with an opportunity rule marked computable | 0 | docs/research/did-the-machine-learn/opportunity-rules.json, rules with status computable |
| Recurrences detected inside the exploratory period so far | 9 | docs/org/improvements/rsi.json, recurrences by detection date in the exploratory window |
| Opportunity events counted in the exploratory period | NOT OBSERVED | node packages/collective/src/failure-opportunities.mjs --root . --rsi docs/org/improvements/rsi.json --rules docs/research/did-the-machine-learn/opportunity-rules.json --from &lt;exploratory opens&gt; --to &lt;confirmatory opens&gt; |
| Unique opportunity events counted in the confirmatory period | NOT OBSERVED | node packages/collective/src/failure-opportunities.mjs --root . --rsi docs/org/improvements/rsi.json --rules docs/research/did-the-machine-learn/opportunity-rules.json --from &lt;confirmatory opens&gt; --to &lt;freeze&gt; |
| Recurrence per opportunity, confirmatory period | NOT OBSERVED | same run; a rate needs counted opportunities, and the row above refuses the first one |
| Exploratory period opens, 00:00 UTC | 2026-09-12 | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 1 |
| Confirmatory period opens, 00:00 UTC (the exploratory period ends) | 2026-10-18 | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 1 |
| Freeze: the confirmatory period closes, 00:00 UTC | 2026-10-31 | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 2 |
| Preregistration date | 2026-10-17 | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 2 |
| Result publication target | 2026-11-06 | docs/research/did-the-machine-learn/PROTOCOL.md, Outcome measures |
| Stop rule: fewest unique opportunity events for an informative result | 30 | docs/research/did-the-machine-learn/PROTOCOL.md, Acceptance rule, stop rule |
| Families replayed in the raw record against condensed lesson experiment | 3 | docs/research/did-the-machine-learn/PROTOCOL.md, Comparator |
| Paired repetitions per replayed family | 3 | docs/research/did-the-machine-learn/PROTOCOL.md, Configuration |
| Planned experiment attempts, both arms | 18 | families x paired repetitions x 2 arms, checked against the protocol's stated total |
| Experiment attempts run | NOT OBSERVED | docs/research/did-the-machine-learn/runs does not exist |
| Interval method | 95% Wilson score, descriptive | docs/research/did-the-machine-learn/PROTOCOL.md, Outcome measures |
| Research ceiling, weekly Claude Max allowance | 10% | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 5 |
| Research ceiling, weekly Codex allowance | 20% | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 5 |
| License for the sanitized evidence and analysis | CC BY 4.0 | docs/research/did-the-machine-learn/PROTOCOL.md, Decisions item 8 |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/did-the-machine-learn

## Method

- This preregistration sets the question, design and stop rule before confirmatory collection. This note reports no study result. I will publish results at this URL and record version numbers and changes in the revisions table.
- I am testing whether a failure returns after it becomes a lesson and a guard, relative to the chances it has to return. A family follows the record's recurrence links back to the oldest incident. An opportunity is a recorded event where that failure could happen again, including failed attempts.
- The exploratory period runs from 2026-09-12 to 2026-10-18. The confirmatory period runs from 2026-10-18 to 2026-10-31. Each starts at midnight UTC on its first date and ends at midnight UTC on its last, so the two never overlap. The data freezes on 2026-10-31. Anything detected after that publishes separately, with its detection date.
- Of 19 declared opportunity rules, 0 are marked computable. The current records count agent runs, not the events where a failure could recur. Before confirmatory collection, I must record those events and independently check that the record is complete, including failed attempts. I will not mark a rule computable just to reach the minimum sample.
- What would count as evidence of learning: within a family, fewer linked recurrences per observed opportunity while a guard was in effect than while it was not, with both counted, plus a frozen guard that catches a variant of its failure it has never seen without blocking the healthy case. A guard that blocks everything does not count. Even a favorable result describes this record. It does not prove what caused it.
- I plan to replay the original task for 3 eligible families. Each replay compares the raw incident record with the condensed lesson, with 3 paired repetitions per family and 18 planned attempts if all families qualify. Both arms use the same task, model, tools, acceptance rule and resource ceiling. A reviewer scores the outputs before seeing the arm labels.
- Stop rule: if fewer than 30 unique opportunity events are observed across the confirmatory families by 2026-10-31, I publish the method and the counts as an uninformative result, in those words. Negative, mixed and uninformative results publish under the same rule as favorable ones. The target date is 2026-11-06. Intervals are 95% Wilson score, descriptive.
- Research is capped at 10% of the weekly Claude Max allowance and 20% of the weekly Codex allowance. When either share is used, research waits. The current allowance and token weights must be checked before launch. Research does not borrow the Machine's operating quota. The counter is packages/collective/src/failure-opportunities.mjs. Its rules are docs/research/did-the-machine-learn/opportunity-rules.json. Sanitized evidence and analysis will publish under CC BY 4.0.

## Limitations

- This note reports no study result. The figures include recorded counts and planned study sizes, read 2026-10-08. None is evidence that the Machine learns.
- This study uses this organization's recorded failures. Missing failures, late detection and incomplete event records can bias a rate. Missing exposure data does not mean zero exposure.
- Guards are added after failures, not at random, so guarded and unguarded periods are not a controlled comparison. A hard family may simply attract more guards.
- Families can share an event, so their counts are never added as independent trials. The 18 experiment attempts are repetitions on 3 task families, not 18 independent families.
- Reaching 30 events does not make any family's estimate precise. A stored lesson is not changed behavior, and a quiet month is not a recurrence rate.

## How to cite

Bartak, J. (2026). Did the Machine Learn From Its Last Failure?. Orbyt Labs Research, measurement version 1.0.0. https://www.orbytlabs.ai/research/did-the-machine-learn

```bibtex
@misc{bartak2026didthemachinelearn,
  author    = {Bartak, J.},
  title     = {{Did the Machine Learn From Its Last Failure?}},
  year      = {2026},
  publisher = {Orbyt Labs Research},
  note      = {Measurement version 1.0.0},
  url       = {https://www.orbytlabs.ai/research/did-the-machine-learn}
}
```

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

Corrections: report an error at https://www.orbytlabs.ai/contact. A corrected record is published as a new version, and its changelog names what changed.

## Changelog

- 1.0.0, content revised 2026-10-08 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
