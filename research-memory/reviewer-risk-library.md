# Reviewer Risk Library

Purpose: reusable reviewer-style risks for geoscience, ecology, remote sensing, and spatial causal inference manuscripts.

## Cross-Cutting Risks

- Causal language exceeds the counterfactual design.
- Static spatial contrast is interpreted as temporal treatment effect.
- Control/reference areas are contaminated by spillover or shared policy context.
- Random train/test splits inflate performance for spatial data.
- Multiple PA-level or pixel-level classifications lack FDR or uncertainty correction.
- Global average hides regional sign reversals.
- Data product uncertainty is not tested with independent products.
- Scale mismatch between process, data resolution, and inference target.
- Sample exclusions are computationally convenient but not ecologically/randomly justified.

## Protected Area / HFI Risks

- "Leakage" implies causal displacement; pressure concentration or halo may be the defensible term.
- PA placement bias can explain static lower pressure inside or near PAs.
- PA establishment year and HFI product years may not support post-treatment trend inference for newer PAs.
- Nearby PAs can contaminate outside reference zones.
- Irregular PA geometry can bias core-outward distance metrics; boundary-distance metrics are safer.

## Figure Risks

- Figure does not state one core conclusion.
- Color encodes inconsistent meanings across panels.
- Legends, panel labels, or colorbars are too small for journal print.
- Export does not preserve editable text or high-resolution raster layers.

## Writing Risks

- Introduction lacks a precise unresolved gap.
- Results mix interpretation with unsupported mechanism.
- Discussion claims policy implication without acknowledging design limitations.
