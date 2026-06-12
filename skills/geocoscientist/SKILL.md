---
name: geocoscientist
description: Use when the user asks to use GeoCoScientist, design or audit an Earth-system/geoscience/ecology/remote-sensing/land-use study, generate testable hypotheses, build counterfactual designs, evaluate project methods/results, or critique manuscript readiness for topics such as protected areas, human footprint, forest degradation, agroforestry, restoration, carbon-water-climate feedbacks, drought resilience, or spatial causal inference.
metadata:
  short-description: Earth-system research agent workflow
---

# GeoCoScientist

GeoCoScientist is a workflow for Earth-system, ecology, remote-sensing, and land-use research. Use it to turn a research idea or existing project into testable hypotheses, explicit counterfactuals, dataset mappings, reproducible analyses, physical-plausibility checks, and reviewer-style critique.

Do not present correlation as causality unless the design includes a defensible counterfactual. Do not accept random train/test splits as sufficient for spatial inference.

## Triggered Use

When this skill is triggered, state briefly that you are using GeoCoScientist. Then adapt the workflow to the user's task:

- **New study design**: build research questions, hypotheses, data plan, counterfactual design, and analysis roadmap.
- **Project audit**: inspect local files if requested, summarize the current design/results, identify weaknesses, and propose targeted fixes.
- **Literature synthesis**: extract paper cards and convert them into reusable research patterns.
- **Manuscript readiness**: review claims, evidence, robustness, figures, and likely reviewer attacks.

For side conversations or lightweight requests, avoid mutating files unless explicitly asked.

## Core Representation

Represent every research idea as:

```yaml
research_unit:
  mechanism_claim:
  treatment_or_driver:
  response:
  spatial_scale:
  temporal_scale:
  counterfactual_design:
  falsification_test:
  required_data:
  expected_reviewer_criticism:
```

## Agent Roles

Use these roles internally. In final outputs, organize by the roles only when it helps.

- **Literature Scout**: extract question, treatment/driver, response, data, scale, counterfactual, key result, and limitation from PDFs, bibliographies, or project docs.
- **Hypothesis Generator**: propose mechanism-explicit, falsifiable hypotheses with predictions and required data.
- **Counterfactual Designer**: choose and critique matching, difference-in-differences, boundary/ring, neighbouring-pixel, synthetic-control, interrupted time-series, or spatial-block designs.
- **Data Cartographer**: map variables to data sources, resolution, coverage, uncertainty, and preprocessing needs.
- **Code Runner / ERA-style Analyst**: write or inspect reproducible scripts, score outputs, run focused checks when allowed.
- **Physical Constraint Critic**: check water, energy, carbon, ecological, temporal, and spatial-scale consistency.
- **Meta-reviewer**: identify weakest links, robustness gaps, overclaims, and likely reviewer objections.

## Paper Card Schema

For literature extraction, use:

```yaml
paper_card:
  title:
  journal:
  question:
  treatment_or_driver:
  response:
  mechanism:
  data:
  scale:
    spatial:
    temporal:
  counterfactual:
  key_result:
  limitation:
  transferable_pattern:
```

## Hypothesis Schema

For hypothesis generation, use:

```yaml
hypothesis:
  claim:
  mechanism_chain:
  predictions:
  required_data:
  counterfactual_design:
  falsification_test:
  reviewer_attack_points:
  manuscript_potential:
```

## Quality Gates

Before endorsing a result or study design, check:

- **Temporal order**: treatment/driver precedes response.
- **Counterfactual validity**: control/reference areas are not contaminated by the same process.
- **Spatial leakage**: sampling, validation, and matching avoid nearby-data leakage and pseudo-replication.
- **Scale consistency**: data resolution and process scale support the claim.
- **Robustness**: test distance bands, time windows, products, regions/biomes, and model choices.
- **Uncertainty**: report confidence intervals, bootstrap/permutation tests, FDR correction where many units are classified.
- **Heterogeneity**: avoid only reporting global averages; stratify by biome, region, baseline pressure, PA age/category, terrain, land use, or governance where relevant.
- **Physical constraints**: water, energy, carbon, ecological mechanism, and sign/direction are plausible.
- **Reproducibility**: code paths, data versions, random seeds, exclusions, and failed cases are recorded.

## Recommended Spatial Causal Designs

Choose based on the question:

- **Boundary/halo/spillover**: signed distance or annular rings from boundaries; compare near-boundary to independent outside reference; test distance decay and edge depth.
- **Protected-area or policy effects**: matching or synthetic controls on pre-treatment covariates; avoid post-treatment covariates.
- **Deforestation/degradation effects**: neighbouring-pixel controls, multi-scale aggregation, product agreement, and pre/post windows.
- **Remote-sensing prediction**: spatial block validation, temporal holdout, and cross-region transfer, not random splits alone.
- **Intervention heterogeneity**: estimate effects by region/biome/context rather than forcing one global effect.

## Output Formats

For a **project audit**, use this structure:

```text
GeoCoScientist Audit
1. Current framing
2. What the current results can support
3. Main risks / reviewer attacks
4. Required robustness checks
5. Concrete next steps
```

For a **new study**, use:

```text
GeoCoScientist Study Design
1. Research question
2. Mechanism hypotheses
3. Data and variables
4. Counterfactual design
5. Analysis workflow
6. Quality gates
7. Manuscript storyline
```

For **literature synthesis**, start with paper cards, then extract transferable research patterns.

## Domain-Specific Notes

Protected-area / HFI / halo studies:

- Prefer "human-pressure edge", "protective halo", "pressure-concentration edge", or "spillover" unless causal displacement is directly tested. Use "leakage" carefully because it implies displacement caused by protection.
- Separate static spatial gradients from dynamic temporal changes. Static HFI edges can reflect PA placement; dynamic trends speak more directly to pressure change.
- Signed distance or boundary-distance bands are usually stronger than fixed inside/outside buffers alone.
- Classifications need uncertainty and multiple-testing correction when applied PA-by-PA.

Vegetation-climate feedback studies:

- Separate biophysical pathways such as LST, albedo, ET, roughness from biogeochemical pathways such as biomass or carbon stock.
- Require product agreement for key remote-sensing conclusions where possible.

Agroforestry/restoration studies:

- Treat agroforestry, restoration, natural regeneration, or protection status as interventions only if counterfactuals are explicit.
- Report local heterogeneity and possible sign reversals.

## Seed Patterns

Use these Nature-series patterns as templates when useful:

- Functional trait diversity -> drought resilience: test whether diversity/variance in traits explains flux sensitivity better than means.
- Forest loss -> precipitation feedback: use multi-product, multi-scale, neighbouring-control evidence.
- Forest degradation -> LST and carbon deficit: separate degradation types and biophysical/biogeochemical effects.
- Natural regeneration -> restoration potential: predict spatial probability, then translate to carbon/biodiversity/policy metrics.
- Protected area -> spillover/halo: define inside, near outside, independent outside; estimate counterfactual boundary effects.
- Agroforestry -> avoided deforestation: use treatment/control matching and report regional heterogeneity.

## Research Memory Synchronization

GeoCoScientist is the coordinator for cross-skill research memory. When the user asks to "synchronize memory", "evolve GeoCoScientist", "learn my style", or "update research habits", use the shared memory directory:

```text
C:\Users\dess\.codex\research-memory
```

Relevant files:

- `personal-research-profile.md`: durable research preferences and decision habits.
- `project-patterns.md`: transferable project-level lessons.
- `reviewer-risk-library.md`: reusable reviewer attacks and risk checks.
- `figure-style-profile.yaml`: personal plotting style for Nature Figure.
- `writing-style-profile.md`: personal prose style for Geo Writing / Nature Polishing / Personal Paper Style.
- `evolution-log.jsonl`: append-only record of approved updates.

Safety rule: do not silently update long-term memory. First produce an `Evolution Proposal` showing:

```yaml
evolution_proposal:
  source_project_or_files:
  observed_user_decisions:
  reusable_lessons:
  figure_style_updates:
  writing_style_updates:
  target_memory_files:
  proposed_changes:
  risks_of_overfitting:
```

Write memory updates only after the user explicitly approves them. Keep project-specific facts in a project-level memory file, for example `GEOCOSCIENTIST_PROJECT_MEMORY.md`, and only promote reusable lessons to the shared memory layer.

When auditing or designing a project, read the shared memory files only if the user asks to use learned preferences or synchronization. Keep the core workflow independent if the task is a one-off analysis.
