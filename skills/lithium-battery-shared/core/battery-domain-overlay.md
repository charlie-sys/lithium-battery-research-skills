# Lithium-ion battery state-estimation overlay

Use this overlay only when the user's actual subject is lithium-ion battery SOC, SOH, capacity, degradation, or remaining-useful-life estimation. It adds domain terminology and evidence boundaries to the requesting skill; it does not change that skill's task, output type, source requirements, or authorization rules. A task outside this domain follows the original skill unchanged.

The detailed, corpus-derived reference is [battery-state-estimation-writing-style.md](battery-state-estimation-writing-style.md). It is based on the user's 48-paper collection. Its descriptions of journal habits are observations, not official journal instructions. For a named target journal, check its current author guide and article type before applying formatting or submission requirements.

## Load only what the task needs

| Requesting skill | Domain reference to use |
|---|---|
| `lithium-battery-writing`, `lithium-battery-polishing`, `lithium-battery-response` | Read the relevant sections of the detailed guide for the requested manuscript section. For abstract, introduction, methods, results, discussion, or conclusion, use Sections 2–8 and 10–11 as needed. Retain the requesting skill's drafting or revision workflow. |
| `lithium-battery-reviewer`, `lithium-battery-statistics`, `lithium-battery-data`, `lithium-battery-figure` | Consult Sections 2, 7, and 8 when evaluating claim strength, experimental units, metric wording, uncertainty, or figure labels. Read other sections only when auditing prose. Do not convert writing preferences into scientific or statistical requirements. |
| `lithium-battery-academic-search`, `lithium-battery-citation`, `lithium-battery-ref-verifier`, `lithium-battery-downloader`, `lithium-battery-literature-pipeline`, `lithium-battery-paper-card`, `lithium-battery-paper-xray`, `lithium-battery-reader` | Consult Section 2 for search/reading terminology and Section 8 when evaluating what an article actually validates. Preserve the source paper's own terminology in bibliographic records and quotations. Do not select sources merely because they use the guide's preferred words. |
| `lithium-battery-paper-trans`, `lithium-battery-image2ppt` | Use Section 2 only to resolve ambiguous domain terminology in translated or newly written text. Preserve source meaning, equations, labels, and layout according to the requesting skill; do not rewrite reproduced source text into a new English style. |
| `lithium-battery-paper2ppt`, `lithium-battery-experiment-log`, `lithium-battery-paper-to-patent`, `lithium-battery-proposal-writer` | Use Sections 2 and 8 for newly authored domain summaries and evidence limits. Use Sections 5–7 only when English academic prose is part of the requested output. Keep presentation, logging, patent, and proposal conventions. |
| `lithium-battery-social-science` | Its normal scope remains social science. If a legitimate interdisciplinary battery task invokes it, use Sections 2 and 8 for technical claims only; do not route an ordinary battery engineering paper to this skill. |
| `lithium-battery-shared` | Provide this overlay and the detailed guide to another Nature skill; do not act as a standalone user workflow. |

## Domain checks for authored text

- Distinguish SOC, SOH, capacity, degradation trajectory, and RUL. Define the target quantity, units, reference condition, and prediction horizon when they affect the claim.
- Tie every accuracy, robustness, generalization, transfer, uncertainty, real-world, or real-time claim to the tested data, metric, conditions, and system level.
- Separate independent cells or packs from cycles and time windows. Check train/validation/test boundaries, possible leakage, target-domain labels, baseline comparability, and hardware context before strengthening a result sentence.
- Distinguish observation, supported interpretation, and mechanism. Ablations or feature attribution alone do not establish an electrochemical cause.
- Never invent missing experiments, numerical results, citations, code/data access, statistical tests, or mechanisms. Flag material gaps for the author.
