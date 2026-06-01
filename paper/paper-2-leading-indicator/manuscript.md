# Paper 2. Manuscript (the leading-indicator study)

Blocked until the analysis gives us a result. Don't draft prose before then. We'd
just be writing a wish list.

Standard empirical structure. The methods and the results carry the paper. The
prose from the brief becomes a tight intro. Aim for 8,000 to 10,000 words for a
working paper.

## Title
Do AI-Exposed Workers Show Financial Stress First? A State by Occupation
Leading-Indicator Approach. Working title.

## 1. Introduction
- The lag. The BLS confirms displacement quarters late (brief section 1).
- The question. Do exposed workers show financial stress first? Where, and how
  fast?
- The contribution bullets, from `claim.md` section 1.2.
- One line previewing the result.

## 2. Related Work
- Areas A, B and C, plus the gap paragraph, from
  `../00-foundation/literature-map.md`.

## 3. Data
- The public inputs, the join, the frozen snapshot. From
  `../00-foundation/data/`.
- A table of sources, granularity, and cadence.

## 4. Methods
- 4.1 The exposure composite and the state rollup (brief section 3.1).
- 4.2 The search ontology and the divergence normalization (brief section 3.2).
- 4.3 The layoff weighting (brief section 3.3).
- 4.4 The lead-lag estimation, which is just the pre-registration in prose.

## 5. Results
- 5.1 The headline lead-lag result.
- 5.2 Robustness. Placebo, weighting, saturation, augmentation versus
  substitution, out of sample.

## 6. Discussion
- What the signal can do, what it can't. The dashboard as the thing people
  actually use.

## 7. Limitations
- Take brief section 8 and expand it, honestly. Causation, saturation,
  geographic resolution, augmentation versus substitution. Say the
  measurement-not-causation thing out loud.

## 8. Conclusion
- The leading indicator, or the bounded null. And what comes next.

## References
- Pull from the brief's reference list. It's already audited.

## Appendices
- A. The full ontology term list.
- B. The weighting sensitivity tables.
- C. The suppression rules.
- D. A link to the replication package in `../00-foundation/reproducibility/`.

## Abstract
About 150 words. Template with slots to fill:

> Official labor statistics confirm AI-driven displacement only after a lag of
> [quarters], and by then the households living through it have already taken on
> the financial stress. We build a [monthly], [state by occupation] signal that
> joins occupational AI-exposure, composed from the
> [Felten, Eloundou, and Brynjolfsson] measures and mapped to states with BLS
> OEWS employment shares, to household financial-stress signals drawn from
> [Google Health Trends] search behavior. Over [period], we test whether that
> signal leads realized occupational unemployment in high-exposure occupations.
> We find [the signal leads by ___ months / no lead we can detect], and the
> result [holds up under / does not survive] placebo, weighting, and
> search-saturation checks. [Augmentation-coded and substitution-coded terms
> behave as predicted.] The pipeline and the dataset are released openly. The
> approach gives us [an early warning for / a bound on] sub-national AI
> labor-market stress.

## Three sentences to write before we submit
1. What we built: ___
2. What we found: ___
3. Why it matters: ___

Status: blocked, waiting on the analysis / drafting / full draft
