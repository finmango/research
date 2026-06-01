# Paper 1. Manuscript (the data descriptor)

A data-journal structure, not an empirical one. The Scientific Data shape works
well. Keep it short.

## Structure

- Background and Summary. Why the signal exists, the gap it fills, the brief in a
  few paragraphs.
- Methods. The exposure composite and the state rollup, the search ontology and
  the divergence normalization, the layoff weighting. This is the core.
- Data Records. The fields, the granularity, the cadence. Points at
  `../00-foundation/data/data-dictionary.md`.
- Technical Validation. The signal is consistent with known layoff events,
  descriptively, not as prediction. Saturation handled by divergence from
  baseline. Suppression and low-confidence flags.
- Usage Notes. How to use it, the licence, the caveats (no causation, and no
  prediction claim in this paper).
- Code Availability. Points at `../00-foundation/reproducibility/`.

## Abstract

About 100 to 150 words, data-venue style. Slots to fill:

> We release an open, monthly, [state-by-occupation] dataset of AI-exposed
> household financial stress, joining occupational AI-exposure (composed from
> the [Felten, Eloundou, and Brynjolfsson] measures and mapped to states with
> BLS OEWS employment shares) to household financial-stress signals drawn from
> [Google Health Trends] search behavior. We document the construction, the
> [fields and cadence], and a technical validation showing the signal is
> consistent with known layoff events. The pipeline is open and reproducible
> under MIT. The dataset supports [research on sub-national AI labor-market
> stress]. It is descriptive and makes no predictive or causal claim.

Status: not started / drafting / full draft
