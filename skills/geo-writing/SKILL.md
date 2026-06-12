---
name: geo-writing
description: Polish, restructure, or draft geoscience and ecology manuscript prose using concise Nature-leaning language patterns, section logic, and sentence-level guardrails derived from landmark papers, scientific writing books, and recurrent errors in non-native English drafts.
---

# Geo Writing

Use this skill when the task is to draft, revise, or diagnose English writing for geoscience, ecology, climate, biogeography, remote sensing, or Earth-system manuscripts.

This skill is for:

- tightening introductions, results, discussions, methods, abstracts, and titles
- converting Chinese notes or rough drafts into concise journal-style English
- checking sentence logic, article use, plurality, tense, transition words, and quantitative phrasing
- aligning prose with common `Nature` / high-impact Earth-science style without copying journal-specific wording

## Default stance

- Prefer argument clarity over ornament.
- Prefer short declarative sentences unless a longer sentence improves logic.
- Make the scientific job of each paragraph explicit: context, gap, question, approach, finding, implication, or limitation.
- Keep claims proportional to evidence.
- Use discipline-standard terms consistently.
- Avoid inflated language, vague intensifiers, and unnecessary abbreviations.

## Workflow

### 1. Identify the writing task

Decide whether the user needs:

- `structural revision`: argument flow, paragraph order, section architecture
- `line editing`: grammar, phrasing, concision, quantitative style
- `journal calibration`: more concise, more neutral, more method-driven, or more discussion-oriented language
- `translation-plus-rewrite`: rebuild logic first, then polish English

If the argument is weak, diagnose the logic before polishing sentences.

### 2. Match the section to its rhetorical job

- `Introduction`: why this problem matters, what is known, what remains unresolved, what this study tests or estimates
- `Results`: what was found, under what comparison, and with what quantitative support
- `Discussion`: how the findings change interpretation, how they align with prior work, and where the boundary conditions are
- `Methods`: what was done, why this design was used, and how reproducibility and inference quality were checked
- `Abstract`: problem, gap, approach, key result, implication
- `Title`: specific, searchable, claim-bounded

Use the move patterns in [references/section-patterns.md](references/section-patterns.md) when you need section-specific guidance.

### 3. Apply geoscience writing guardrails

Use [references/language-guardrails.md](references/language-guardrails.md) for recurring sentence-level issues, especially:

- article use: `a`, `an`, `the`
- singular versus plural scientific nouns
- tense consistency within results and methods
- distinction between `by`, `due to`, `because of`, `in contrast`, `by contrast`
- quantitative phrasing around effect size, uncertainty, periods, and comparisons
- punctuation that improves readability in long technical sentences

### 4. Prefer reusable high-clarity sentence patterns

Use [references/phrase-patterns.md](references/phrase-patterns.md) for compact templates commonly seen in strong geoscience writing, especially for:

- stating gaps without exaggeration
- presenting causal or quasi-causal designs cautiously
- describing remote-sensing and spatial analysis workflows
- reporting effect sizes and uncertainty
- expressing mechanism and limitations without overclaiming

### 5. Calibrate to high-impact Earth-science style

Use [references/source-notes.md](references/source-notes.md) when you need the broader style logic distilled from:

- landmark `Nature` and related high-impact Earth-system papers
- scientific writing books commonly used by researchers
- recurrent problems observed in non-native English manuscripts

Do not imitate any one paper's wording. Extract structural and stylistic habits only.

## What this skill should optimize

- fast reader comprehension
- strong paragraph logic
- concise scientific register
- quantitative precision
- cautious causal language when design is observational
- consistency in terms, tense, symbols, and units

## What to avoid

- decorative adjectives and dramatic adverbs
- vague claims such as `important`, `novel`, `robust`, `significant` without context
- long noun stacks when a prepositional phrase is clearer
- mixing results and interpretation in the same sentence unless the meaning depends on it
- overuse of abbreviations that reduce readability
- copying stock phrases from journals

## Output modes

When using this skill, default to one of these response styles:

- `rewrite only`: provide a clean revised paragraph
- `rewrite + rationale`: revised text plus 3-6 concrete style or logic notes
- `diagnose only`: identify structural, grammatical, and rhetorical problems without rewriting
- `phrase alternatives`: offer 2-4 concise variants for a title, topic sentence, or key claim

## Trigger examples

- `Use $geo-writing to revise this Introduction paragraph for Nature-style geoscience English.`
- `Use $geo-writing to rewrite this Methods subsection on propensity score matching.`
- `Use $geo-writing to diagnose why this Results paragraph reads awkwardly.`
- `Use $geo-writing to turn these Chinese notes into a concise Discussion paragraph.`

## Personal writing memory

When the user asks to use their personal writing style, learn from their revisions, or synchronize skills, read:

```text
C:\Users\dess\.codex\research-memory\writing-style-profile.md
```

Use it as a preference layer after the section-specific logic and language guardrails. It can guide tone, paragraph structure, causal caution, preferred terms, phrases to avoid, and Chinese-to-English term choices. Do not update it silently. If the user asks you to learn from draft/revised pairs, first produce a concise proposal of writing-style updates and wait for approval before writing memory.
