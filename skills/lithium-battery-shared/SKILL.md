---
name: lithium-battery-shared
description: Internal shared-reference support package for installed Nature Skills, including lithium-battery-writing, lithium-battery-polishing, lithium-battery-response, lithium-battery-reader, and lithium-battery-paper2ppt. Do not invoke it as a standalone user workflow. Load only the specific core or journal-format file requested by another Nature skill.
---

# Nature Shared References

Use this package only as a dependency of another installed Nature skill.

- Load the exact referenced file; do not preload the whole package.
- Treat `core/` and `journal-formats/` as shared definitions, not standalone workflows.
- Use `journal-formats/nature.md` only for the flagship journal Nature and
  `core/research-compliance.md` only when its specialist applicability gate is
  triggered.
- Use `journal-formats/nature-machine-intelligence.md` for exact NMI article
  types, limits, initial-submission files, data/code duties and production
  requirements; do not import flagship Nature or Nature Communications limits.
- Use `core/main-text-discipline.md` for result placement, main-text compression,
  revision accretion, caption/SI allocation, and claim-repetition checks.
- Use `core/nature-results-discussion.md` for corpus-derived Nature-style
  Results claim escalation, evidence-bound local interpretation, and Discussion
  synthesis; do not present it as official journal policy.
- Use `core/discussion-argument-language.md` for journal-general Discussion
  function sequencing, reverse-funnel control, evidence-calibrated modality,
  claim-specific limitations, and uncertainty-driven future work.
- Use `core/nature-introduction.md` for corpus-derived Nature-style problem
  funnels, exact knowledge gaps, literature tension, question-first novelty,
  and Introduction–Results alignment; do not present it as official journal
  policy.
- Use `core/nature-abstract.md` for corpus-derived Nature-style
  discovery-centred abstract compression, claim hierarchy, selective numeric
  support, and field-level payoff; do not present it as official journal policy.
- Return to the requesting skill for task logic, output format, and final QA.

## Lithium-ion battery state-estimation variant

When this skill handles lithium-ion battery SOC, SOH, capacity, degradation, or RUL work, read [the battery domain overlay](core/battery-domain-overlay.md) and apply only the branch relevant to this skill's task. Preserve this skill's original workflow and source requirements; the 48-paper writing guide is corpus-derived and does not replace the target journal's current author instructions.
