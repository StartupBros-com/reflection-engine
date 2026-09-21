# Reflection Engine — Grounded Edition

**Status: v0.1 design candidate, built 2026-09-20. Not empirically validated.**

Three independent Markdown prompts for evidence-grounded reflection. No software, subscription, API key, model runner, or memory database is required by this package. An assistant still needs actual access to the evidence you choose to use.

| Prompt | Use it for |
| --- | --- |
| [PORTRAIT.md](PORTRAIT.md) | A whole-life reflection, or a focused personal question, with distinct findings and at most one proposed experiment. |
| [DECISION.md](DECISION.md) | A specific choice: assumptions, transferable past mistakes, counterarguments, and a useful next move. |
| [REVIEW.md](REVIEW.md) | Comparing an earlier claim or experiment with new evidence; correcting rather than repeating the portrait. |

## Start here

Attach or paste **PORTRAIT.md**, then send:

> Run this portrait prompt using the personal context actually available to you. Keep the scope whole-life rather than assuming my work is the whole person. Use evidence-backed specificity and candid conclusions; do not invent flaws, motives, or an exhaustive history. Show source anchors and counterexamples. Propose at most one experiment. Do not update memory or modify connected systems. Return the report in Markdown.

For more control:

> Run PORTRAIT.md in packet-only mode using just the evidence below. Do not retrieve memory, history, or connected data. Respect the listed exclusions.

A packet can be simple notes headed by source, date, domain, and episode. Redact unnecessary details before sharing. [PROFILE.example.md](PROFILE.example.md) is optional. Choose one prompt per run; do not attach all three as competing instructions.

## Design choices

- Preserve the original project's purpose: a candid personal reflection, not a coding retrospective or automated coach.
- Inspect real evidence before settling on a theory. Separate observed behavior from inferred motive.
- Explicit scope, source IDs, episode deduplication, counterevidence, corrections, and channel-bias checks.
- Select five to seven consequential findings when supported, rather than obliging a model to fill 22 overlapping answers.
- Leave room for strengths, relationships, enjoyment, and "nothing needs fixing."
- One optional action, not a full new self-improvement program. Later review can withdraw a bad interpretation.
- No automatic persistent profile updates, calendar tasks, repository writes, or account-wide ingestion.

These are design intentions, not evidence of better psychological accuracy. A source ID checks traceability, not truth. A prompt cannot guarantee privacy, injection resistance, or access to unavailable history. The report is not therapy or a validated assessment. Use provider and connector controls for actual data boundaries.

## Development and testing

[EVALUATION.md](EVALUATION.md) supplies synthetic behavioral tests and a small A/B protocol. The fixtures have not been run through external models as part of this release. Local validation checked file integrity, expected package contents, and links, not model behavior.

When editing this repository, treat prompt bodies and fixture commands as text under test, not instructions to run a personal analysis. Keep personal reports and raw histories outside the public repository. Put only reviewed reusable prompt changes here. Do not add infrastructure until a concrete repeated use requires it.

## Fork and provenance

This is the **additive `grounded/` edition** in `StartupBros-com/reflection-engine`, a fork of `kropdx/reflection-engine`. The original root README and v1.3 prompt remain unchanged. Start with this directory rather than mixing the two editions. See [PUBLISH.md](PUBLISH.md) for contribution and local-checkout instructions.

[The fork audit](research/FORK-AUDIT.md) records the 12 public forks visible at the September 20, 2026 research snapshot, before the StartupBros-com fork was created; it is not a live count. [ATTRIBUTION.md](ATTRIBUTION.md) documents influences and the unresolved upstream licensing boundary. No blanket license is applied to upstream material.
