# Public fork audit — September 20, 2026

## Scope and method

Historical snapshot taken before the StartupBros-com fork was created. The counts below describe that inspection, not the current network.

Upstream `kropdx/reflection-engine` at `1a3301c1306ec82499c2ef85a82e52f34ef995a1`. The live repository API reported 12 forks and network size 12. A live request to [the forks endpoint](https://api.github.com/repos/kropdx/reflection-engine/forks?per_page=100&sort=newest) returned 12 entries, all reporting zero subforks. All advertised branches of all 12 repositories were checked through GitHub's branches endpoint, rather than inferring changes from stars or update times. Each list fit on one page.

Ten forks have exactly one advertised branch, pointing to the exact upstream commit. Galligan has two changed topic branches while its main is unchanged. EauDoon has a changed main and three historical topic branches that contain no commits ahead of its main (26, 14, and 3 commits behind, respectively).

This is a dated public-branch snapshot, not a claim about private forks, uncommitted work, deleted branches, tags-only/unadvertised changes, or future updates. The developed fork's documentation and bounded prompt were inspected, not its entire CLI implementation or runtime behavior. This audit is not a security certification of any fork.

## Every visible public fork

| Repository | Created (UTC date) | Advertised branches | Finding |
| --- | --- | ---: | --- |
| [jasonhwest/reflection-engine](https://github.com/jasonhwest/reflection-engine) | 2026-08-23 | 1 | Only `main`, identical to upstream. |
| [icygual/reflection-engine](https://github.com/icygual/reflection-engine) | 2026-08-20 | 1 | Only `main`, identical to upstream. |
| [WojciechHupert/reflection-engine](https://github.com/WojciechHupert/reflection-engine) | 2026-08-14 | 1 | Only `main`, identical to upstream. |
| [marcoreif1970-blip/reflection-engine](https://github.com/marcoreif1970-blip/reflection-engine) | 2026-08-07 | 1 | Only `main`, identical to upstream. |
| [DarnocTruc/reflection-engine](https://github.com/DarnocTruc/reflection-engine) | 2026-08-06 | 1 | Only `main`, identical to upstream. |
| [galligan/reflection-engine](https://github.com/galligan/reflection-engine) | 2026-08-05 | 3 | Unchanged main; two useful unmerged prompt patches. |
| [C2R-Marketing/reflection-engine](https://github.com/C2R-Marketing/reflection-engine) | 2026-08-05 | 1 | Only `main`, identical to upstream. |
| [EauDoon/reflection-engine](https://github.com/EauDoon/reflection-engine) | 2026-08-04 | 4 | Bounded prompt plus offline preparation/review companion; historical branches already contained in main. |
| [paulmars/reflection-engine](https://github.com/paulmars/reflection-engine) | 2026-08-04 | 1 | Only `main`, identical to upstream. |
| [Cromm22/reflection-engine](https://github.com/Cromm22/reflection-engine) | 2026-08-03 | 1 | Only `main`, identical to upstream. |
| [maXXusXYZ/reflection-engine](https://github.com/maXXusXYZ/reflection-engine) | 2026-08-03 | 1 | Only `main`, identical to upstream. |
| [rtalmo/reflection-engine](https://github.com/rtalmo/reflection-engine) | 2026-08-03 | 1 | Only `main`, identical to upstream. |

Full branch SHAs and API locators are in [FORK-SNAPSHOT.json](FORK-SNAPSHOT.json).

## Galligan: the highest-value small patches

[PR #5](https://github.com/kropdx/reflection-engine/pull/5), open and unmerged at inspection; head `f3f5a6c7cfd71afa1242a9bcfdd6a11a1487a773`, branch `harden-corpus-boundary`. One small addition explicitly separates corpus evidence from executable instructions and prohibits source text from authorizing actions or disclosure. Adopt the design principle. A prompt alone is not an enforcement boundary.

[PR #6](https://github.com/kropdx/reflection-engine/pull/6), open and unmerged at inspection; head `b7f2283ca1f30d74b4f5da0b28e5334d99402bf4`, branch `strengthen-evidence-calibration`. Makes the initial thread map provisional; clarifies the evidence hierarchy and provider/channel bias; puts the conclusion before calibration metadata; defines a real insufficient-evidence outcome; and audits repeated answers resting on a single theory. Adopt the substance. Grounded uses neutral instructions rather than the patch's personality-bearing sample conclusion and uses support labels rather than numerical confidence scores.

Neither patch is in Galligan's main. Looking only at default branches would miss both.

## EauDoon: the most developed alternative

[Inspected main](https://github.com/EauDoon/reflection-engine/tree/aadf611823689b9a9d20f9e8a2da3287e62faedb), latest listed push September 18, 2026. The preserved upstream prompt's blob is `13e999a6ba8e05b2d4976156ef067830fb791f5c`. Its [bounded edition](https://github.com/EauDoon/reflection-engine/blob/aadf611823689b9a9d20f9e8a2da3287e62faedb/Reflection-Engine-Bounded.md) adds explicit selected-source scope, source/episode IDs, exclusions, premise rejection, alternative explanations, and observable optional actions. Default question IDs are 4, 11, and 17. Its confidence scores are explicitly editorial judgments rather than probabilities.

The [README](https://github.com/EauDoon/reflection-engine/blob/aadf611823689b9a9d20f9e8a2da3287e62faedb/README.md) documents a Node 22+ standard-library companion for packet construction, literal redaction, selection by dates/domains/questions, report-reference checks, manual review, accepted-excerpt export, integrity receipts, experiment observations, and run comparisons. It describes no package installation, network calls, or model calls; this audit did not independently execute or certify those properties.

Borrow source IDs, explicit run boundaries, small first runs, corrections, and follow-up. Keep its optional CLI as a reference rather than a dependency for this prompt-only version. Source-link validity is not semantic truth, redaction is not guaranteed anonymity, and receipt hashes do not validate a psychological interpretation.

## What this version intentionally does not do

It does not cherry-pick third-party commits or copy their complete prompt bodies into the archive. It implements selected concepts in new text, with attribution. It does not merge code into an existing personal operating system or automatically save a portrait as memory. It does not claim behavioral or clinical validation.

## Provenance caution

Upstream had no LICENSE file in the inspected root, and its API license field was null. EauDoon adds an MIT notice covering named portions and modifications; this audit did not establish an upstream permission grant to relicense the original material. Preserve original authorship and notices and resolve permission before publishing a blanket license or commercially redistributing copied text. See [GitHub's licensing guidance](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository).
