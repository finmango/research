# Step 3 — Pre-Registration

**Goal:** lock the design *before* touching any outcome data, and post it with
a timestamp (OSF Registries or AsPredicted). This is the single biggest
credibility multiplier for a measurement paper. It is also your defense
against "did you fish for this result?"

**Rule:** complete and post this *before* downloading/merging BLS occupational
unemployment (the outcome). Exposure and search inputs can be built first.

---

## 3.1 Hypotheses

- **H1 (primary).** The joined AI-distress signal at time *t* is positively
  associated with realized occupational unemployment at *t + k* (k = 1–3
  months) in high-exposure occupations.
- **H2 (placebo).** No such lead exists in low-exposure occupations.
- **H3 (optional).** Augmentation-coded search terms do *not* predict
  unemployment; substitution-coded terms do.

## 3.2 Variables (pre-specify exactly)

- **Exposure score** — composite of Felten/Eloundou/Brynjolfsson, z-scored,
  **equal-weighted** by default. State rollup via OEWS employment shares
  (formula in brief §3.1).
- **Search signal** — ontology in brief §3.2, normalized as
  **divergence-from-baseline** (define baseline window: trailing __ months).
- **Outcome** — [BLS occupational unemployment / LAUS]; reference period and
  vintage fixed here.
- **High-exposure cutoff** — [top tercile / quartile] of composite.

## 3.3 Analysis plan (pre-specify the statistic AND the threshold)

- Primary test: [cross-correlation at lag k / panel regression with leads /
  out-of-sample nowcast vs. AR baseline].
- **Significance / decision threshold:** ____.
- Multiple-comparison handling across states/clusters: ____.

## 3.4 Kill condition (from brief §5 — the pre-committed bar)

> If, after four quarters of data, the signal does not show a statistically
> significant positive lead-lag correlation with realized occupational
> unemployment in high-exposure clusters (at the threshold in §3.3), we treat
> the predictive claim as unsupported, publish that result, and re-scope to a
> descriptive-only signal or shelve it.

## 3.5 Data exclusions & suppression (pre-specify)

- Suppress state × occupation cells below employment count N = ____.
- Search series below volume floor ____ flagged low-confidence.

## 3.6 Sample & period

- States: all 50 + DC. Period: ____ to ____. Frequency: monthly/quarterly.

## 3.7 Registration record

- Platform: ☐ OSF Registries  ☐ AsPredicted
- URL: ____
- Timestamp: ____
- Frozen commit of this file: ____

---

**Status:** ☐ drafted  ☐ co-author sign-off  ☐ POSTED (timestamp obtained)
