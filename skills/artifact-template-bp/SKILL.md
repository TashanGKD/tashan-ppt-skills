---
name: artifact-template-bp
description: "Use when a user asks to adapt a PowerPoint or BP to an authorized organ-chip or organoid template, especially when a prior deck supplies the visual master."
metadata:
  version: "2.1.0-public"
---

# Organ-chip BP template adapter

This skill is the template adapter for the organ-chip / organoid BP workflow. Use it together with `presentation-craft` for reasoning, copy, evidence, diagrams, and layout, and with the host environment's PowerPoint tool for file creation and rendering.

This public package contains no internal source deck or proprietary template file. The user must provide an authorized PPTX as the visual source.

## Relationship to other skills

1. Start with `presentation-craft` for the page question, conclusion, evidence, visual center, and interactive input clarification.
2. Use this skill to preserve the user-provided template's background, title hierarchy, fonts, colors, separators, logo, page numbers, and footer.
3. Use the host PowerPoint tool for editing, rendering, and export.
4. Use `references/bp-production-rules.md` and `references/bp-production-checklist.md` for template-specific boundaries and delivery gates.

## Choose the visual source

Ask the user to identify whether the supplied PPTX is:

- a visual template;
- a content source;
- a layout example;
- a cumulative deck to extend.

Do not infer this from the filename. Copy the user-authorized source before editing. If the user provides no template, continue with `presentation-craft` and create a separate visual direction instead of claiming template fidelity.

## Template-specific checks

Measure or copy from the actual reference page:

- page size and background;
- top-left section label;
- centered title and typography;
- divider line, logo, footer and folio;
- body, subtitle, caption and bilingual font hierarchy.

Red-gray colors alone do not prove template fidelity. Do not cover a whole source slide with a screenshot and call the result editable.

## Delivery

Before formal layout, keep `source_manifest`, `style_tokens`, `page_spec`, and `asset_ledger`. Keep original files and alternative layouts separate. Mark outputs as draft or review unless the user explicitly approves a particular version.
