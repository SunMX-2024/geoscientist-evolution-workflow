# GeoCoScientist Evolution Workflow

This project stores a controlled workflow for evolving research skills and reusable memory across geoscience, ecology, remote-sensing, and manuscript-writing tasks.

The workflow has one purpose: preserve durable research preferences and tested project patterns without turning temporary project details into long-term rules. It supports three linked skills:

- `geocoscientist`: coordinates research design, project audits, counterfactual reasoning, and reviewer-risk checks.
- `geo-writing`: uses the writing profile to draft and revise concise geoscience prose.
- `nature-figure`: uses the figure profile to guide publication-grade plotting decisions.

## Core Principle

Memory updates are explicit, reviewed, and reversible.

The assistant must not silently update long-term memory. It first prepares an `Evolution Proposal` that states the evidence, proposed changes, target files, and risks of overfitting. Shared memory is updated only after user approval.

## Repository Contents

```text
docs/
  geocoscientist-evolution-workflow.md
research-memory/
  personal-research-profile.md
  project-patterns.md
  reviewer-risk-library.md
  writing-style-profile.md
  figure-style-profile.yaml
  evolution-log.jsonl
skills/
  geocoscientist/SKILL.md
  geo-writing/SKILL.md
  nature-figure/SKILL.md
```

## Use Pattern

Use GeoCoScientist when a project, figure, or draft produces a reusable lesson:

```text
Use GeoCoScientist to synchronize this project experience. First generate an Evolution Proposal. Do not write memory until I approve it.
```

After approval, update only the relevant memory file and append a short entry to `evolution-log.jsonl`.

## Boundary

This repository should remain private. It may contain personal research preferences, writing habits, and unpublished project patterns. Do not publish it or include private project data, manuscripts, credentials, or large analysis outputs.

