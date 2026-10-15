# 96 Ways the Agents Were Confidently Wrong

A field note from Orbyt Labs Research, by Justin Bartak.

Author: Justin Bartak, ORCID [0009-0005-2615-3624](https://orcid.org/0009-0005-2615-3624), Wikidata [Q139551829](https://www.wikidata.org/wiki/Q139551829). Organization: Orbyt Labs, Wikidata [Q139551916](https://www.wikidata.org/wiki/Q139551916), https://www.orbytlabs.ai.

Version 1.0.1, content revised 2026-10-07. Measurement version 2.23.0, collected 2026-08-27 to 2026-10-07.

Canonical page: https://www.orbytlabs.ai/research/confidently-wrong

## Claim

Of 96 distinct engineering failures logged by an AI-run organization as of 2026-10-07, 68 of 96 (71%) raised no error at all and were found only because someone checked an artifact directly, and 72 of 96 (75%) have a named automated countermeasure that exists in the repository.

## Measured

Census of the logged failure corpus, 2026-10-07.

Sample: 96 logged failures in one repository.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Distinct failures logged | 96 | docs/lessons-learned.md, numbered entries |
| Failures that raised NO error (silent) | 68 of 96 (71%) | SILENT in scripts/refresh-research-notes.ts over each entry |
| Failures with a countermeasure that exists in the tree | 72 of 96 (75%) | public/failure-corpus.json, field `mechanized_count` |
| Automated guards now in the repository | 118 | ls scripts/check-*.cjs \| wc -l |
| Average length of a logged failure | 491 words | mean word count across the entries |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/confidently-wrong

## Method

- A census of one corpus, counted by parsing the numbered entries of the failure log on the date shown, not by recalling how many there are.
- The silent-failure count matches entries describing a failure that produced no error, no exception and no red test: a green suite, an exit code of zero, a report rendering clean, or a job concluding success while performing no work. From 2.0.0 the classifier is committed code (SILENT in scripts/refresh-research-notes.ts) rather than a hand read, so the number is reproducible and its false negatives are inspectable.
- The countermeasure count is the repository's own failure corpus (public/failure-corpus.json, field mechanized_count): an entry is mechanized only when the check, test or guard it names exists in the tree at generation time. Version 1.0.0 counted entries that named a guard in prose; from 2.0.0 the count is a checkable fact about the tree, and it is a lower bound on remediation because some failures were fixed by deleting the capability rather than guarding it.
- Both counts come from text matching over the corpus and are reported as such. They classify how a failure was DESCRIBED, which is a proxy for how it behaved.
- The corpus is append-only and each entry carries its own receipt: the command, the log line, or the query that established it.

## Limitations

- These are the failures that were CAUGHT and written down, so the share published here is the silent share among LOGGED failures. The rate across all failures, noticed or not, is unknown, and this corpus cannot bound it in either direction: a failure nobody noticed is not necessarily one that raised no error, because it may have errored somewhere nobody was reading, and a corpus that only holds what was found says nothing about the shape of what was not.
- Text matching classifies prose, not behaviour. An entry that fails to use the word silent is counted as not silent even where the failure was.
- One organization, one codebase, one set of tools. Nothing here establishes that these failure shapes generalize.
- A guard existing is not a guard working. This project separately requires every detector to prove it can stay quiet on a clean input, which is a different measurement published separately.
- No trend is claimed. The changelog carries every refresh, but a rising count is a growing log, not a rising failure rate.

## How to cite

Bartak, J. (2026). 96 Ways the Agents Were Confidently Wrong. Orbyt Labs Research, measurement version 2.23.0. https://www.orbytlabs.ai/research/confidently-wrong

```bibtex
@misc{bartak2026confidentlywrong,
  author    = {Bartak, J.},
  title     = {{96 Ways the Agents Were Confidently Wrong}},
  year      = {2026},
  publisher = {Orbyt Labs Research},
  note      = {Measurement version 2.23.0},
  url       = {https://www.orbytlabs.ai/research/confidently-wrong}
}
```

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

Corrections: report an error at https://www.orbytlabs.ai/contact. A corrected record is published as a new version, and its changelog names what changed.

## Changelog

- 1.0.1, content revised 2026-10-07 (patch): changed: claim; measured. Declared: presentation: dates rendered as ISO 8601; citation metadata added
- 1.0.0, content revised 2026-10-07 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
