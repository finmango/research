# Pre-Registration (OSF-ready): Do AI-Exposed Workers Show Financial Stress First?

This is the self-contained version of the pre-registration, the one we upload to
OSF Registries and timestamp. It restates every definition the design depends
on, so a reader needs nothing else to evaluate it. The internal working copy is
`preregistration.md`. The positioning brief it draws from is
`../../AI_ECONOMIC_IMPACT_2026.md`.

Status: drafted and self-contained. Pending co-author sign-off, then post to OSF.
We have not accessed the outcome data. See section 2.

## 0. Administrative

- Title. Do AI-Exposed Workers Show Financial Stress First? A State by
  Occupation Leading-Indicator Approach.
- Authors. [names, affiliations, ORCIDs to fill in]
- Corresponding author. [fill in]
- Version. v1 draft. Date set on posting.
- License. Open, MIT, matching the repository.

## 1. Background and aim

Official labor statistics confirm AI-driven displacement only after a lag of
quarters. By then the exposed households have already absorbed the financial
stress. We ask whether a combined AI-exposure and household financial-stress
search signal leads realized occupational unemployment by one to three months,
among the most exposed occupations, across US states, in the generative-AI
period. This is a measurement and prediction study, not a causal one. We never
claim AI caused any specific household's distress.

## 2. Data-access statement (why we register now)

As of registration we have built, or will build, only the inputs: the exposure
composite and the search signal. We have not accessed, pulled, summarized, or
inspected the outcome series (CPS occupational unemployment) for the test
window. We post this design first, then pull the outcome. That ordering is the
credibility claim, so we state it plainly and date it.

## 3. Hypotheses

- H1 (confirmatory, primary). The combined AI-distress signal at month t is
  positively related to realized occupational unemployment at t+k, for k of 1, 2
  and 3 months, among high-exposure occupations (top tercile of the exposure
  composite). Operationally, the sum of the distributed-lead coefficients over k
  is positive at the threshold in section 6.
- H2 (confirmatory, placebo). No such lead appears among low-exposure
  occupations (bottom tercile).
- H3 (secondary). Augmentation-coded search terms do not predict unemployment;
  substitution-coded terms do.

## 4. Variables

### 4.1 Predictor: the combined AI-distress signal

Two pieces, an exposure layer and a search layer.

Exposure composite. For each SOC-coded occupation we build a composite from
three published indices: Felten, Raj and Seamans (AIOE, 2021); Eloundou,
Manning, Mishkin and Rock (GPT exposure, 2023); and Brynjolfsson, Mitchell and
Rock (suitability for machine learning, 2018), where available. Each index is
z-scored across occupations, then averaged with equal weights by default. We
roll the occupation scores up to states with BLS OEWS state employment shares:

    AIExposure_state = sum over occ of ( employment_share[state, occ] x ExposureScore[occ] )

The high-exposure group is the top tercile of the composite, employment-weighted
across detailed occupations. The low-exposure group is the bottom tercile, used
as the H2 placebo. The confirmatory test (H1, H2) runs on these two groups.

Occupation clusters (the descriptive layer). For the public cube and for the
secondary by-cluster breakout we use six SOC major groups, chosen because their
exposure varies widely:

1. Office and administrative support (SOC 43), high exposure
2. Computer and mathematical (SOC 15), mixed
3. Healthcare practitioners (SOC 29), low to moderate
4. Production (SOC 51), moderate
5. Transportation and material moving (SOC 53), moderate
6. Education, training and library (SOC 25), moderate

Search layer. We pull Google Health Trends volumes for an AI-distress ontology
in four categories:

- Displacement awareness: "will AI take my job", "AI replaced me", "job to AI"
- Reskilling intent: "reskill from [occupation]", "career change at 40",
  "learn to code 2026"
- Acute distress: "laid off tech", "severance negotiation",
  "unemployment after layoff"
- Adaptation, tracked separately as augmentation rather than substitution:
  "use ChatGPT at work", "AI tools for [occupation]"

Each term passes a signal-to-noise screen before it goes live. We normalize each
series as divergence from a trailing 52-week baseline, with robustness at 26 and
104 weeks, and we pull from January 2022 so the divergence is defined from the
first test month. Google Health Trends is geographic (state by week), so the
search layer is measured at the state level; the occupational content of the
test comes from stratifying the outcome by exposure.

### 4.2 Outcome

Realized unemployment from CPS microdata (IPUMS-CPS), computed at the occupation
level and then aggregated, from the same micro-data, two ways: into the high and
low exposure groups for the confirmatory test, and into the six clusters for the
descriptive cube and the secondary breakouts. Monthly, on a 3-month rolling
basis to tame CPS sampling noise. The reference period is the survey month. We
fix the vintage to first release so revisions cannot move the result. Robustness
brackets: LAUS state unemployment, and national unemployment by occupation
cluster.

### 4.3 Secondary grounding input (not in the confirmatory test)

To ground the search signal in real events we compute an exposure-weighted
layoff intensity from WARN Act notices and BLS JOLTS:

    AILayoffIntensity_state,q = sum over event of ( workers x ExposureScore[occ] ) / labor_force_state

This is a validation and case-study input, not a predictor in the confirmatory
regression.

## 5. Analysis plan

Primary model. A panel distributed-lead regression of occupational unemployment
at t+k on the standardized signal at t, with leads at k of 1, 2 and 3,
group-by-state and month fixed effects, and standard errors clustered by state
and by exposure group. The decision statistic is the sum of the three lead
coefficients in the high-exposure group.

Out-of-sample check. The signal-augmented model must also beat an autoregressive
baseline on RMSE at horizon k, in a rolling-window evaluation.

## 6. Inference criteria (the number that counts)

- Primary. The distributed-lead coefficient sum is positive at p < 0.05,
  two-sided.
- Multiple comparisons. There is exactly one confirmatory test, the pooled
  high-exposure lead-coefficient sum. Every by-state, by-cluster and by-k
  breakout is secondary and reported with Benjamini-Hochberg FDR control at q of
  0.10, labeled exploratory.
- Confirmatory versus exploratory. Anything not named here as confirmatory is
  exploratory, and labeled as such in the paper.

## 7. Exclusions and suppression

- Suppress any cell (state, exposure group or cluster, and month) with fewer
  than 50 labor-force respondents in the 3-month pooled window.
- Flag, but do not drop, any search series below its volume floor: a state-week
  below the 10th percentile of that term's national distribution is
  low-confidence. Drop a series only if it is zero or near-zero for more than
  half the window. Floors can be tightened after we see the volume
  distributions, never loosened, and any change is documented.

## 8. Sample and period

All 50 states plus DC. Test window from January 2023 (post-ChatGPT, the
generative-AI period) to the data-freeze month. Search series pulled from
January 2022 for the baseline. Monthly frequency.

## 9. What counts as support, and the kill condition

Support means the primary test clears the threshold in section 6, the H2 placebo
shows no comparable lead, and the result survives the search-saturation check
(the same result across different baseline windows).

Kill condition. If, after four quarters of data, the signal does not show a
statistically significant positive lead-lag relationship with realized
occupational unemployment in the high-exposure group at the threshold above, we
treat the predictive claim as unsupported, we publish that, and we either
re-scope to a descriptive-only signal or shelve it. We commit to this now, while
we still do not know the answer.

## 10. Open specification choices to settle at sign-off

Three construction choices are not yet pinned. A credible registration cannot
leave them vague, so we name them here and lock them with the co-author before
posting. Current defaults are in brackets.

1. Search occupational resolution. Health Trends is geographic, not
   occupational. [Default: keep the predictor at the state level and carry the
   occupational content on the outcome side, through the exposure groups.] The
   alternative apportions the state search signal to occupation groups by
   employment share, which adds assumptions.
2. The confirmatory unit. [Default: two exposure groups, the top and bottom
   tercile of the composite over detailed occupations, which are well powered
   and give a clean placebo.] The six-cluster cube stays descriptive and
   secondary.
3. How exposure enters. [Default: as a group definition, top versus bottom
   tercile, with a continuous exposure-weighted specification as robustness.]

## 11. Registration record

- Platform. OSF Registries.
- URL. ___ (fill on posting)
- Timestamp. ___ (fill on posting)
- Frozen commit of this file. ___ (commit hash of the signed-off version)
