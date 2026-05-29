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
  related to realized occupational unemployment at t plus k, with k between one
  and three months, in high-exposure occupations.
- H2, the placebo. No such lead shows up in low-exposure occupations.
- H3, optional. Augmentation-coded search terms don't predict unemployment.
  Substitution-coded terms do.

## 3.2 Variables (spell every one out)

- Exposure score. Composite of Felten, Eloundou and Brynjolfsson, z-scored,
  equal-weighted by default. State rollup uses OEWS employment shares, formula
  in brief section 3.1.
- Search signal. The ontology from brief section 3.2, normalized as divergence
  from baseline. Set the baseline window here: trailing ___ months.
- Outcome. BLS occupational unemployment or LAUS. Fix the reference period and
  the vintage now.
- High-exposure cutoff. Top third or top quarter of the composite.

## 3.3 Analysis plan (name the statistic and the threshold)

- The primary test: cross-correlation at lag k, panel regression with leads, or
  an out-of-sample nowcast against an AR baseline.
- Decision threshold: ___.
- How we handle multiple comparisons across states and clusters: ___.

## 3.4 Kill condition (from brief section 5)

> If, after four quarters of data, the signal doesn't show a statistically
> significant positive lead-lag correlation with realized occupational
> unemployment in high-exposure clusters at the threshold above, we treat the
> predictive claim as unsupported, we publish that, and we either re-scope to a
> descriptive-only signal or shelve it.

We decide this now, while we still don't know the answer. That's the point.

## 3.5 Exclusions and suppression (set in advance)

- Suppress any state by occupation cell below employment count N of ___.
- Flag any search series below volume floor ___ as low confidence.

## 3.6 Sample and period

- States: all 50 plus DC. Period: ___ to ___. Frequency: monthly or quarterly.

## 3.7 Registration record

- Platform: OSF Registries or AsPredicted.
- URL: ___
- Timestamp: ___
- Frozen commit of this file: ___

Status: drafted / co-author sign-off / posted with timestamp
