# Controlled Evolution Workflow for GeoCoScientist

## Purpose

GeoCoScientist is a research workflow for Earth-system science, ecology, remote sensing, land-use analysis, and manuscript development. It helps convert project experience into reusable research memory.

The workflow is designed for controlled learning. It does not treat every conversation or result as a permanent rule. Instead, it separates project-specific facts from transferable patterns and updates long-term memory only after explicit approval.

## Why The Workflow Exists

Research work produces repeated decisions:

- how to frame observational evidence without overclaiming causality;
- how to separate static spatial patterns from dynamic temporal processes;
- how to design counterfactuals for protected areas, land-use change, and restoration;
- how to revise figures and prose toward a concise, high-impact scientific style;
- how to anticipate reviewer objections before drafting the manuscript.

These decisions are often useful beyond one project. The workflow records them when they are stable, evidence-based, and likely to improve future work.

## Memory Layers

The system uses two memory layers.

### Project Memory

Project memory stays inside the project folder. It records local decisions, file paths, sample filters, model choices, unresolved exclusions, and interpretation boundaries.

Examples:

- a protected-area project changed from a leakage framing to a human-pressure edge framing;
- a PA sample was rebuilt because an inherited year filter no longer matched the manuscript target;
- an edge metric used period-mean HFI rather than recent HFI.

These facts should not automatically become global preferences.

### Shared Research Memory

Shared memory is stored in:

```text
research-memory/
```

It contains durable preferences and reusable patterns:

- `personal-research-profile.md`: research habits and decision preferences;
- `project-patterns.md`: transferable project lessons;
- `reviewer-risk-library.md`: recurring reviewer risks;
- `writing-style-profile.md`: prose preferences for geoscience manuscripts;
- `figure-style-profile.yaml`: plotting preferences and export defaults;
- `evolution-log.jsonl`: approved update history.

Only reusable lessons should be promoted to this layer.

## Evolution Cycle

The workflow follows five steps.

### 1. Observe

GeoCoScientist reads the relevant project files, draft revisions, figure scripts, or user decisions. It identifies what changed and why.

### 2. Distinguish

It separates three types of information:

- project-specific facts;
- reusable research patterns;
- personal style preferences.

Only the second and third categories are candidates for shared memory.

### 3. Propose

Before writing to memory, GeoCoScientist prepares an `Evolution Proposal`:

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

This proposal makes the update auditable. It also gives the user a chance to reject weak or overly specific lessons.

### 4. Approve

The user decides whether the proposal should be written. Without explicit approval, no shared memory file is changed.

### 5. Record

After approval, the relevant memory files are updated. A short record is appended to `evolution-log.jsonl`, including the source, target files, and update summary.

## Skill Synchronization

Three skills use the shared memory layer.

### GeoCoScientist

GeoCoScientist is the coordinator. It reads research preferences, project patterns, and reviewer risks when the user asks for memory-aware research design or project audit.

It should check:

- temporal order;
- counterfactual validity;
- spatial leakage;
- scale consistency;
- uncertainty;
- heterogeneity;
- physical plausibility;
- reproducibility.

### Geo Writing

Geo Writing reads `writing-style-profile.md` when the user asks to use personal writing style or synchronize prose preferences.

It should keep prose concise, mechanism-forward, and proportional to the evidence. It should avoid causal language when the design only supports association.

### Nature Figure

Nature Figure reads `figure-style-profile.yaml` when the user asks to use personal plotting style or learn from revised figures.

It should still begin from a figure contract: the claim, evidence chain, panel logic, backend, and export requirements come before aesthetic preferences.

## Safety Rules

The workflow follows four safety rules.

1. Do not silently update long-term memory.
2. Do not promote one-off project details to shared memory.
3. Do not store credentials, private raw data, unpublished manuscript text, or large outputs.
4. Do not use memory to override project evidence or user instructions.

## Example Use

To synchronize a project:

```text
Use GeoCoScientist to synchronize the PA-HFI project experience. First generate an Evolution Proposal. Do not write memory until I approve it.
```

To learn figure style:

```text
Compare this original Python figure script with my revised version. Summarize my plotting preferences and generate a figure-style-profile.yaml update proposal.
```

To learn writing style:

```text
Compare this draft and revised paragraph. Summarize my revision habits and generate a writing-style-profile.md update proposal.
```

## Expected Outcome

The workflow should make future work more consistent without making it rigid. It should help the assistant remember durable preferences, reuse tested research patterns, and anticipate reviewer risks, while keeping each new project grounded in its own evidence.

