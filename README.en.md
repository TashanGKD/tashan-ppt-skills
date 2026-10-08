<!-- Tashan Association logo -->
<p align="center">
  <a href="https://tashan.ac.cn" target="_blank" rel="noopener noreferrer">
    <img src="docs/assets/tashan.svg" alt="Tashan Logo" width="280" />
  </a>
</p>

<p align="center">
  <strong>Tashan Presentation Craft Skills</strong><br>
  <em>Reusable skills for evidence-grounded PPT and BP production</em>
</p>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#quick-start">Quick Start</a> •
  <a href="#component-relationship">Components</a> •
  <a href="#interactive-input-flow">Input Flow</a> •
  <a href="#examples-and-anti-patterns">Examples</a> •
  <a href="#ecosystem-position">Ecosystem</a> •
  <a href="README.md">中文</a>
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> Reusable PPT and BP skills that start from rough input, identify missing information, organize evidence, select layouts, adapt authorized templates, and deliver reviewable presentation files.

---

## Overview

Tashan Presentation Craft Skills provide the method layer for presentation workflows. They separate content reasoning, visual layout, template adaptation, and file rendering so that different projects can use their own materials and visual systems while sharing a consistent production method.

Core ideas:

- **Interactive intake**: users may start with a sentence, a rough brief, an old deck, or a reference image. The skill identifies knowns, gaps, and conflicts before production.
- **Content and visual separation**: the content manuscript decides what to say, the visual source decides how to lay it out, and original evidence decides what can be claimed.
- **Investor readability**: body copy explains the claim, pain or judgment comes before numbers, and visuals support the argument.
- **Semantic diagrams**: nodes and arrows are defined by responsibility and relationship before visual styling.
- **Template portability**: the generic method does not impose a color scheme; a template adapter is loaded only when the user provides an authorized template.

---

## Quick Start

### Prerequisites

- An Agent Skills-compatible environment such as Codex or Cursor;
- A PPT creation and rendering tool supplied by the host environment;
- User-provided content, template, or visual references. They may be incomplete.

This repository does not include internal BP source decks, proprietary data, or private project files.

### Install locally

```bash
git clone https://github.com/TashanGKD/tashan-ppt-skills.git
mkdir -p ~/.codex/skills
cp -R tashan-ppt-skills/skills/presentation-craft ~/.codex/skills/
cp -R tashan-ppt-skills/skills/artifact-template-bp ~/.codex/skills/
```

### Minimal request

```text
Use presentation-craft to help me make a PPT.
Start by identifying what is known and missing. If the layout is ambiguous, show up to three low-fidelity options in chat before creating the formal deck.
```

For the organ-chip BP adapter:

```text
Use presentation-craft and load artifact-template-bp.
I will provide a content manuscript and an authorized template deck. First distinguish the content source, visual source, and evidence sources.
```

---

## Component relationship

```text
presentation-craft
├── general reasoning, writing, evidence, diagrams, layouts, and interaction
├── uses the host presentations tool for file operations
└── loads a template adapter when needed
        └── artifact-template-bp
```

| Component | Responsibility | Use it when |
|---|---|---|
| `presentation-craft` | General PPT reasoning, interaction, evidence, layout, and examples | Every PPT / BP task |
| `artifact-template-bp` | Organ-chip BP template adaptation and boundaries | An authorized organ-chip / organoid template is provided |
| `presentations` | PPT reading, editing, rendering, and export | Supplied by the host environment; not bundled here |

---

## Interactive input flow

```text
rough request
  ↓
identify knowns, gaps, and version conflicts
  ↓
ask a small number of blocking questions
  ↓
show up to three low-fidelity options when needed
  ↓
user selects a direction
  ↓
produce PPTX, PDF, PNG, and notes
  ↓
render review and user feedback
```

Typical inputs are the audience, use case, content manuscript, template, page list, evidence, claim boundaries, and delivery format. See [`preflight-inputs.md`](skills/presentation-craft/references/preflight-inputs.md).

---

## Examples and anti-patterns

The casebook covers covers, market change, structural pain points, definitions, workflows, architectures, dry–wet loops, technical matrices, moats, teams, roadmaps, financing, ecosystem walls, and high-density pages.

Start with:

- [`wording-and-examples.md`](skills/presentation-craft/references/wording-and-examples.md): 12 categories of Chinese slide-copy guidance with before/after examples, covering direct statements, complete sentences, meaningful numbers, terminology, review commentary, and claim boundaries.

- [`investor-readable-deck.md`](skills/presentation-craft/references/investor-readable-deck.md)
- [`visual-casebook.md`](skills/presentation-craft/references/visual-casebook.md)
- [`cases.md`](skills/presentation-craft/references/cases.md)

Common anti-patterns include isolated giant numbers, mechanical card grids, arrows without semantics, AI shown only as a terminal feedback box, planned capabilities written as current facts, and complex logo networks implying unverified partnerships.

---

## Directory structure

```text
.
├── README.md
├── README.en.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── docs/assets/tashan.svg
└── skills/
    ├── presentation-craft/
    │   ├── SKILL.md
    │   ├── agents/
    │   ├── references/
    │   └── assets/
    └── artifact-template-bp/
        ├── SKILL.md
        ├── agents/
        ├── references/
        └── assets/
```

---

## Key documents

| Document | Path | Purpose |
|---|---|---|
| General entry point | `skills/presentation-craft/SKILL.md` | General PPT production entry point |
| Preflight inputs | `skills/presentation-craft/references/preflight-inputs.md` | Identify missing inputs before production |
| Investor-readable deck | `skills/presentation-craft/references/investor-readable-deck.md` | Copy, numbers, and hierarchy |
| Wording and examples | `skills/presentation-craft/references/wording-and-examples.md` | 12 wording categories, examples, and exceptions |
| Visual casebook | `skills/presentation-craft/references/visual-casebook.md` | Good and bad layout patterns |
| Template adapter | `skills/artifact-template-bp/SKILL.md` | Organ-chip BP template adaptation |
| Template checklist | `skills/artifact-template-bp/references/bp-production-checklist.md` | Version, asset, render, and delivery gates |

---

## Ecosystem position

This repository belongs to the methods and tooling layer of the Tashan human–agent mixed digital world project.

```text
Tashan digital world
├── General skill systems
│   ├── tashan-cursor-skills
│   ├── tashan-research-skills
│   └── tashan-ppt-skills  ← this repository
├── Applications and workbenches
└── Domain projects and workflows
```

Related repositories:

| Repository | Role | Link |
|---|---|---|
| `tashan-cursor-skills` | General Tashan Cursor skill system | [GitHub](https://github.com/TashanGKD/tashan-cursor-skills) |
| `tashan-research-skills` | Tashan research workflow skills | [GitHub](https://github.com/TashanGKD/tashan-research-skills) |
| `tashan-ppt-skills` | PPT / BP production skills | This repository |

---

## Environment variables

No environment variables are required by this repository. It contains no API keys, GitHub tokens, or project data.

The host environment supplies the PPT tools, fonts, and runtime dependencies needed for actual deck production.

---

## Contributing

Contributions to general PPT reasoning, layout, evidence organization, and case studies are welcome. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

## Changelog

See [`CHANGELOG.md`](CHANGELOG.md).

---

## License

MIT License. See [`LICENSE`](LICENSE).
