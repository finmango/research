# Step 3. Pre-Registration

Lock the design before we touch any outcome data. Then post it somewhere with a
timestamp (OSF Registries or AsPredicted). For a measurement paper this is the
single biggest thing we can do for credibility. It's also our answer the day
someone asks if we fished for the result.

The rule is simple. Finish this and post it before we pull or merge the BLS
occupational unemployment data, because that's the outcome. The exposure and
search inputs can be built first. The outcome waits.

## 3.1 Hypotheses

- H1, the main one. The joined AI-distress signal at time t is positively
  related to realized occupational unemployment at t plus k, with k of 1, 2 and
  3 months, in high-exposure occupations (top tercile of the composite).
  Operationally: the sum of the distributed-lead coefficients over k is positive
  at the threshold in 3.3.
- H2, the placebo. No such lead shows up in low-exposure occupations (bottom
  tercile).
- H3, optional. Augmentation-coded search terms don't predict unemployment.
  Substitution-coded terms do.

## 3.2 Variables (spell every one out)

- Exposure score. Composite of Felten, Eloundou and Brynjolfsson, z-scored,
  equal-weighted by default. State rollup uses OEWS employment shares, formula
  in brief section 3.1.
- Search signal. The ontology from brief section 3.2, normalized as divergence
  from a trailing 52-week baseline, with robustness at 26 and 104 weeks. We pull
  the search series from January 2022 so the divergence is well-defined from the
  first test month.
- Outcome. The unemployment rate for each state, occupation cluster, and month,
  from CPS microdata (IPUMS-CPS), on a 3-month rolling basis. The reference
  period is the survey month. We fix the vintage to first release so revisions
  can't move the result. LAUS state unemployment and national unemployment by
  occupation cluster are the robustness brackets.
- High-exposure cutoff. Top tercile of the composite, employment-weighted across
  detailed occupations. The bottom tercile is the placebo group for H2.

## 3.3 Analysis plan (name the statistic and the threshold)

- The primary test. A panel distributed-lead regression: occupational
  unemployment at t+k on the standardized signal at t, with leads at k of 1, 2
  and 3, state-by-cluster and month fixed effects, and standard errors clustered
  by state and by occupation cluster. The decision statistic is the sum of the
  three lead coefficients.
- Decision threshold. The lead-coefficient sum is positive at p < 0.05
  (two-sided). We also pre-specify an out-of-sample check: the signal-augmented
  model beats an AR baseline on RMSE at horizon k in a rolling-window evaluation.
- Multiple comparisons. There is exactly one confirmatory test, the pooled
  high-exposure lead-coefficient sum. Every by-state, by-cluster and by-k
  breakout is secondary and reported with Benjamini-Hochberg FDR control at
  q of 0.10, labeled exploratory.

## 3.4 Kill condition (from brief section 5)

> If, after four quarters of data, the signal doesn't show a statistically
> significant positive lead-lag correlation with realized occupational
> unemployment in high-exposure clusters at the threshold above, we treat the
> predictive claim as unsupported, we publish that, and we either re-scope to a
> descriptive-only signal or shelve it.

We decide this now, while we still don't know the answer. That's the point.

## 3.5 Exclusions and suppression (set in advance)

- Suppress any state, occupation cluster, and month cell with fewer than 50
  labor-force respondents in the 3-month pooled window.
- Flag, but do not drop, any search series below its volume floor: a state-week
  below the 10th percentile of that term's national distribution is
  low-confidence. Drop a series only if it is zero or near-zero for more than
  half the window. We can tighten these floors after seeing the volume
  distributions, never loosen them, and we document any change.

## 3.6 Sample and period

- States: all 50 plus DC. Test window: January 2023 (post-ChatGPT, the
  generative-AI period) to the data-freeze month. Search series pulled from
  January 2022 for the baseline. Frequency: monthly.

## 3.7 Registration record

- Platform: OSF Registries (preferred for the full design) or AsPredicted.
- URL: ___ (fill on posting)
- Timestamp: ___ (fill on posting)
- Frozen commit of this file: ___ (the commit hash of the posted version)

Status: drafted. Co-author sign-off and posting still to come. Do not pull the
CPS outcome data until this is posted with a timestamp.
