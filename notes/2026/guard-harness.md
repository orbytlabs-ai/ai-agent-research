# Every Guard Must Prove It Can Stay Silent

A field note from Orbyt Labs Research, by Justin Bartak.

Author: Justin Bartak, ORCID [0009-0005-2615-3624](https://orcid.org/0009-0005-2615-3624), Wikidata [Q139551829](https://www.wikidata.org/wiki/Q139551829). Organization: Orbyt Labs, Wikidata [Q139551916](https://www.wikidata.org/wiki/Q139551916), https://www.orbytlabs.ai.

Version 1.0.1, content revised 2026-09-25. Measurement version 2.17.0, collected 2026-08-27 to 2026-09-25.

Canonical page: https://www.orbytlabs.ai/research/guard-harness

## Claim

As of 2026-09-25, the Orbyt Labs repository enforces 118 automated guard scripts, of which 16 block a commit outright, and 104 of 104 (100%) guard test suites assert that the detector stays silent on a clean input rather than only firing on a bad one.

## Measured

Point-in-time census of the repository, 2026-09-25.

Sample: 118 guard scripts and 104 guard test suites in one repository.

## Measurements

| Metric | Value | Source in Orbyt's internal record |
| --- | --- | --- |
| Guard scripts in the repository | 118 | ls scripts/check-*.cjs \| wc -l |
| Blocking a commit outright | 16 | node "$ROOT/scripts/check-&lt;name&gt;.cjs" \|\| exit 1 lines in scripts/pre-commit |
| Carrying a STRICT promotion switch | 93 | grep -l _STRICT scripts/check-*.cjs \| wc -l |
| Guard test suites | 104 | ls __tests__/scripts/check-*.test.ts \| wc -l |
| Test suites proving the guard stays SILENT | 104 of 104 (100%) | node scripts/check-doc-claim-parity.cjs, check 6 |
| Audit dimensions in the roster | 100 | app/(site)/founder/building-in-public/audit-dims.json, field `total` |
| Logged failures with a guard built in response | 67 | public/failure-corpus.json, field `mechanized_count` |

The sources name commands and files in Orbyt's private repository. They are records of how each number was taken, not links; the canonical page carries the published evidence: https://www.orbytlabs.ai/research/guard-harness

## Method

- A census of one repository on one date, taken by running each command in the source column and reading its output, not by reading documentation that describes the repository.
- A guard is any executable at scripts/check-*.cjs. Blocking means the pre-commit hook runs it as `node "$ROOT/scripts/check-<name>.cjs" || exit 1`; the hook invokes no guard through an npm script, so that one form is the whole population.
- A STRICT switch means the guard reads a &lt;NAME&gt;_STRICT environment variable, which promotes it from reporting to blocking. Most guards are report-only by default and can be promoted per run.
- The stays-silent figure uses the repository's own detector rather than a definition written for this entry. Check 6 of check-doc-claim-parity.cjs scans every __tests__/scripts/check-*.test.ts for absence idioms (.toBe(0), .toBe(false), .not.to, not.toMatch, not.toContain, toEqual([]), toHaveLength(0), toEqual({})) and warns on any file with none.
- The rule being measured exists because four detectors misfired on a single day in July 2026, every one of which passed its own test suite, because each suite only ever proved the detector could be LOUD.

## Limitations

- One repository, one team, one date. There is no control group and no comparison against other codebases, so this describes a practice rather than demonstrating that the practice works better than an alternative.
- A census, refreshed on a schedule, not a controlled time series. The changelog carries every refresh with its deltas, but a rising count can mean growth or reclassification, and no trend is claimed from it.
- An absence idiom in a test file is evidence that a negative case was written, not proof that the negative case is a good one. A test can assert zero findings against an input that could never have produced any.
- The stays-silent detector is deliberately conservative and its author documents two earlier drafts that were wrong in opposite directions, one matching loose prose and one omitting toEqual([]). It is a warning rather than a blocking gate for that reason.
- Counting guards is not measuring defects caught. This entry does not claim the 118 guards prevented 118 problems.

## How to cite

Bartak, J. (2026). Every Guard Must Prove It Can Stay Silent. Orbyt Labs Research, measurement version 2.17.0. https://www.orbytlabs.ai/research/guard-harness

```bibtex
@misc{bartak2026guardharness,
  author    = {Bartak, J.},
  title     = {{Every Guard Must Prove It Can Stay Silent}},
  year      = {2026},
  publisher = {Orbyt Labs Research},
  note      = {Measurement version 2.17.0},
  url       = {https://www.orbytlabs.ai/research/guard-harness}
}
```

License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse it with attribution.

Corrections: report an error at https://www.orbytlabs.ai/contact. A corrected record is published as a new version, and its changelog names what changed.

## Changelog

- 1.0.1, content revised 2026-09-25 (patch): changed: claim; measured. Declared: presentation: dates rendered as ISO 8601; citation metadata added
- 1.0.0, content revised 2026-09-25 (initial): first version of this record

---

Generated from the records the canonical site renders. Files listed in `.orbyt-research-distribution.json` are rewritten on every sync; edit the source, not this copy.
