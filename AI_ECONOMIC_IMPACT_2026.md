# Measuring AI's Economic Impact on Household Financial Health

**A FinMango Positioning Brief**

**Prepared by:** FinMango Research Team
**Date:** May 2026
**Companion to:** Financial Health Barometer Methodology v2.4 (Dec 2025)

---

## Executive Summary

If AI is going to break parts of the labor market over the next few years, the first place it'll show up isn't GDP. It's going to be in households: rent that doesn't get paid on time, food-bank lines that get longer in metros nobody was watching, search queries about reskilling at 2 a.m. The BLS will eventually confirm what happened, but by then the damage has already worked its way through people's savings, credit, and mental health.

We've been running the **FinMango Financial Health Barometer** since 2025. It's a state-level signal that combines slow, authoritative government data (BLS, Census, HUD) with real-time behavioral data (Google Health Trends search volumes) and an academic anchor (Harvard JCHS on housing). Four indices today: Financial Anxiety, Food Insecurity, Housing Stress, and Affordability.

This brief makes a fairly narrow argument. We've already built the pipeline. With a focused set of extensions, the same pipeline can produce something that doesn't exist yet: a monthly, household-level read on how AI exposure is translating into financial stress, broken out by state and by the occupations most likely to be affected.

**What we're asking for:** funding and a research partnership to build the four extensions described here over 12 months. The estimated cost is roughly 1.5–2 FTE-years of engineering and research time (see §7). We're writing this with recent foundation interest in AI's labor effects in mind — including the OpenAI Foundation's May 2026 announcement — but the work stands on its own merit either way.

What follows: where current statistics fall short, the four pieces we'd add to the Barometer to fill that gap, and a 12-month plan for getting it shipped and validated.

---

## 1. Why Current Statistics Aren't Enough

Anyone trying to track AI's economic impact today is working with three kinds of data, and each one has a hole in it.

The official labor-market series (BLS unemployment, OEWS occupational employment, JOLTS) are the most trustworthy numbers anyone has, but they lag. State unemployment (LAUS) lands roughly three weeks after the reference month — fast, but not occupation-specific. Occupational employment (OEWS) is annual and publishes on the order of a year after its reference period. By the time the occupation-level data confirms a shift, the households living through it have absorbed months of stress. The latency we're trying to beat is measured in quarters, not weeks.

The academic AI-exposure indices (Felten et al., Eloundou et al., Brynjolfsson) are useful for a different reason. They tell you which occupations are at risk. They don't tell you whether the risk has actually shown up yet, in which places, or how hard. Static maps, not flowing signals. The most recent evidence is starting to fill in the "has it shown up" question — Brynjolfsson, Chandar & Chen's November 2025 "Canaries in the Coal Mine" finds a ~16% relative employment decline for 22–25-year-olds in the most AI-exposed occupations since late 2022 — but it lands at the national/occupation level and on the lag of payroll and survey data, not the state-by-state, near-real-time read we're after.

Then there's macro: CPI, productivity, GDP. Too aggregated to be useful here. Acemoglu's 2025 estimate puts AI's total-factor-productivity gain at well under 1% over a decade — modest in the aggregate, and that's exactly the problem: a small national productivity bump can sit on top of a serious local collapse in administrative-support occupations across three Midwestern metros and never show up.

What's missing is the household-level read, stratified by AI exposure. The question isn't whether AI is changing the economy; it's whether the workers most exposed to it are showing financial stress, where, and how fast. We think the Barometer is the most direct way to answer that.

---

## 2. What the Barometer Looks Like Today

Quick context, since some of this is in the methodology doc already:

| Index | Government Input | Search Signal | Calibration |
|---|---|---|---|
| Financial Anxiety | BLS LAUS unemployment | "debt help", "bankruptcy" | — |
| Food Insecurity | Census SAIPE poverty rate | "food bank near me" | — |
| Housing Stress | Census ACS B25071, HUD FMR | "eviction help" | Harvard JCHS 2025 |
| Affordability | Composite of the three above + cost-of-living adjustment | — | — |

Indices land on an 80–200 scale, adjusted by regional multipliers, with full source attribution on every output. The pipeline runs daily for unemployment, monthly for housing prices, annually for the structural inputs.

The four extensions below sit on top of this. The existing v2.4 methodology doesn't change.

---

## 3. The Four Extensions

### 3.1 An AI-Exposure Layer Anchored in O\*NET

For each SOC-coded occupation we'd build a composite AI-exposure score from three published indices: Felten/Raj/Seamans (AIOE), Eloundou et al. (GPT exposure), and Brynjolfsson's SML where it's available. Z-score normalize, equal-weight by default, and run the obvious sensitivity tests on alternative weightings.

A note on prior art. The closest thing to this layer is Anthropic's "observed exposure" measure (Massenkoff & McCrory, 2026), which combines LLM capability assessments with real Claude usage data and deliberately weights automation over augmentation across ~800 O\*NET occupations — the same instinct behind our §3.2 augmentation/substitution split. We see that as a complement, not a competitor: it's a strong fourth candidate input to the composite (usage-grounded rather than task-theoretic), and we'd test adding it once licensing and update cadence are clear. Our contribution isn't a better exposure score; it's joining exposure to household financial-stress signals at the state level.

To get from occupations to states, we use BLS OEWS state-level employment shares by SOC code:

```
AIExposure_state = Σ_occ (employment_share_state,occ × ExposureScore_occ)
```

The output lives at two granularities: an aggregate state score, and a state × occupation-cluster matrix that lets you say something like "AI-exposed administrative workers in Ohio" and have it mean a specific number.

This works because everything underneath is public. O\*NET tasks, OEWS employment, the published exposure indices. Nothing proprietary, nothing we can't show our work on. The cadence is annual, set by OEWS.

We start at the state level not because it's the finest resolution available — OEWS supports MSA-level analysis in many states, and the argument in §1 about damage hiding in specific metros is exactly why we expect to go finer — but because state matches the existing Barometer's geography and search-signal sample sizes are largest there. State is the launch granularity; validation (§8) tells us where it's safe to push down to MSA.

### 3.2 An AI-Distress Search Ontology

The current Barometer pulls Google Health Trends signals for things like "eviction help" and "food bank near me." We'd add a fifth category for AI-displacement distress. Some candidate terms, all of which need signal-to-noise testing before they go live:

- **Displacement awareness:** "will AI take my job", "AI replaced me", "job to AI"
- **Reskilling intent:** "reskill from [occupation]", "career change at 40", "learn to code 2026"
- **Acute distress:** "laid off tech", "severance negotiation", "unemployment after layoff"
- **Adaptation (tracked separately):** "use ChatGPT at work", "AI tools for [occupation]" — this is augmentation, not displacement, and conflating them is a known failure mode. Cleanly separating augmentation from substitution is our hardest open problem; see §8.

The trick is normalization. Generic AI search interest is going up regardless of whether anyone is actually losing their job, so a raw spike in "will AI take my job" doesn't mean much. The signal is the *divergence* from the baseline. We'd validate the ontology against announced layoffs (next section) and against the state-level exposure scores from §3.1. If both correlate, the signal is real.

### 3.3 Cross-Referencing Layoffs

Two additional structural inputs ground the search data in actual events:

- **WARN Act notices.** Layoff disclosures triggered at 100 affected employees under the federal WARN Act, with many state "mini-WARN" laws setting lower thresholds (often 50, sometimes fewer). Some states publish APIs, some have to be scraped or compiled from PDFs.
- **BLS JOLTS.** Industry-level openings and turnover, monthly.

For each layoff event we'd code the affected occupations to SOC and compute an exposure-weighted layoff intensity by state and quarter:

```
AILayoffIntensity_state,q = Σ_event (workers × ExposureScore_occ) / labor_force_state
```

Why bother with the weighting? Because a 500-person warehouse layoff and a 500-person paralegal layoff look identical in standard layoff statistics and mean completely different things for an AI-impact measurement. The first is a logistics story; the second is a substitution story.

### 3.4 A State × Occupation Signal Cube

Right now the Barometer publishes at one dimension: state. The extension adds a second: occupation cluster. We'd start with six clusters chosen because their AI exposure varies a lot:

1. Office and administrative support (SOC 43) — high exposure
2. Computer and mathematical (SOC 15) — mixed; lots of augmentation, some substitution
3. Healthcare practitioner (SOC 29) — low to moderate
4. Production (SOC 51) — moderate
5. Transportation and material moving (SOC 53) — moderate, mostly autonomous-systems exposure
6. Education, training, and library (SOC 25) — moderate, AI-tutor substitution risk

Not every index stratifies cleanly by occupation. Financial Anxiety is the natural candidate: its government input (LAUS unemployment) and several search signals can be apportioned to occupation clusters via OEWS employment shares. Food Insecurity and Housing Stress rest on inputs (poverty rate, rent burden) and search terms ("food bank near me," "eviction help") that carry no occupational signal, so those stay state-only for now. The cube is therefore primarily an *anxiety-by-occupation* layer sitting alongside the existing state-level indices, not a full occupation breakout of all four. We'd be explicit about that in the published methodology.

What this enables is statements like (illustrative numbers, not real output):

> Financial Anxiety for SOC 43 (administrative support) in Ohio rose 18 points between Q1 and Q2 2026 against a state aggregate change of +4. AI-exposed occupations are driving 80% of the state's anxiety increase.

That's not something anyone can publish today on a monthly cadence, which is the gap this whole program is trying to close.

---

## 4. What Gets Shipped

Three outputs:

A **public dashboard** on finmango.org showing the state × occupation cube, refreshed monthly. Free, no login, same hosting and design language as the existing Barometer.

A **quarterly AI Impact Brief**, 8 to 12 pages, with state-level vignettes describing what the prior quarter's signals showed. Distributed to research partners (World Bank, IMF, Google Health, OpenAI Foundation as relevant) and to the press.

**Open data and a REST API.** State × occupation × month time series under MIT license, methodology documentation alongside. The existing FinMango open-by-default posture extends to this.

A note on privacy. Every input is already aggregated — Google Health Trends is published at population scale, and the government series are public — so there's no individual-level data anywhere in the pipeline. But thinly populated state × occupation cells can still produce unstable or quasi-identifying estimates. We'll suppress any cell below a minimum employment count (threshold set during validation, likely on the order of the OEWS suppression rules we already inherit) and flag low-confidence cells rather than publish a noisy point estimate as if it were solid.

---

## 5. How We'll Know If It Works

We've thought hard about how to keep this honest, because the easiest failure mode for a signal product is to publish something nobody can falsify. Three validation paths, each one good enough on its own:

The first is the obvious one. Compare quarterly signal levels against subsequently released BLS unemployment-by-occupation data. If the signal has any predictive content, it should lead realized unemployment by one to three months in high-exposure occupations. We're committing to a bar in advance: if, after four quarters of data, the signal doesn't show a statistically significant positive lead-lag correlation with realized occupational unemployment in high-exposure clusters (we'll pre-register the exact statistic and significance level before the first release), we treat the predictive claim as unsupported, say so publicly, and either re-scope the product to a descriptive-only signal or shelve it. Naming the kill condition before we have results is the point.

The second is cross-checking against independent measures. Our state-aggregate exposure scores should correlate with regional exposure work like Acemoglu and Restrepo's, with the ILO's 2025 occupational-exposure index, and with the state-level usage patterns in the Anthropic Economic Index. Divergence is informative.

The third is the case-study check. Every release, we pick the top three state × occupation cells by signal change and look for real events (news, WARN notices) that plausibly explain the movement. When nothing matches, we go back to the ontology.

All validation results get published alongside the data, the same way the existing Barometer attributes its sources.

---

## 6. Why This Should Sit at FinMango

A few honest reasons.

The infrastructure already exists. The Barometer isn't a proposal, it's a running pipeline with daily and monthly ingestion, source attribution, and a public site. The AI extension is a meaningful but bounded addition to something that ships today.

The institutional validation is in place. World Bank, IMF, WHO, Google Health partnerships mean our methodology has been picked over by people who don't have to be polite. That same network is how outputs from this work get distributed.

We're open by default. Methodology, data, code: all MIT-licensed and public. Nothing about this program would create a dependency on us; if FinMango disappears tomorrow, the methodology can be picked up by anyone.

What we're not doing, and don't want to do: design post-AI economic systems, model UBI variants, or advocate for specific policy. That's not our lane and there are better people working on it. The role we're describing is narrower. We want to be the measurement layer that everyone else can build on.

---

## 7. Roadmap

| Phase | Months | Deliverable |
|---|---|---|
| 1. Exposure layer construction | 0–2 | Composite occupational scores; state-level rollup published |
| 2. Search ontology extension | 1–3 | AI-distress terms tested, added to Barometer pipeline |
| 3. Layoff/JOLTS integration | 2–4 | WARN + JOLTS ingestion live; weighted layoff intensity computed |
| 4. Industry × state cube launch | 3–6 | Public dashboard live; first monthly release |
| 5. Validation studies | 4–9 | Concurrent + cross-validation results published |
| 6. First Quarterly AI Impact Brief | 6 | Public release; partner distribution |
| 7. Open API + dataset release | 9–12 | Full programmatic access |

**Resourcing.** The plan assumes roughly 1.5–2 FTE-years across the 12 months: one data engineer (pipeline extensions, WARN/JOLTS ingestion, dashboard) and a part-time research lead (exposure scoring, ontology design, validation studies), with existing FinMango infrastructure and hosting absorbing the rest. We'll firm up a line-item budget with any committed partner before Phase 1 kicks off.

---

## 8. What We Don't Know Yet

Four real ones, in no particular order:

**Augmentation vs. substitution.** AI that augments knowledge workers can raise their earnings before any displacement shows up — recent work separating the two (e.g., "Augmenting or Automating Labor?", arXiv:2503.19159, 2025; and the automation-weighting in Massenkoff & McCrory's observed-exposure measure) finds genuinely divergent wage and employment effects, which is precisely why we can't lump them together. The search ontology needs to make that distinction and we don't have a clean test for it yet. We have ideas, but they're ideas, not results.

**Search-signal saturation.** Generic AI search interest is rising fast enough that displacement-specific queries risk drowning in the baseline. The divergence-from-baseline approach in §3.2 is our best current answer, but it needs empirical work before we trust it.

**Geographic resolution.** OEWS supports MSA-level analysis in many states. State is the obvious starting point because it matches the existing Barometer, but MSA may be the right unit for some of these signals. We'll let validation tell us which.

**Causal attribution.** Everything we're describing measures correlation between AI exposure and financial stress. Establishing AI as the cause of any specific household's distress is a different research program, and we'll be explicit about that limit in everything we publish. People will read causation into the data anyway; the best we can do is keep saying it isn't there.

---

## References

### AI Exposure Literature

*Foundational exposure indices (the §3.1 composite inputs):*
- Felten, E., Raj, M., & Seamans, R. (2021). Occupational, industry, and geographic exposure to artificial intelligence. *Strategic Management Journal*.
- Eloundou, T., Manning, S., Mishkin, P., & Rock, D. (2023). GPTs are GPTs: An early look at the labor market impact potential of large language models. OpenAI / arXiv:2303.10130.
- Brynjolfsson, E., Mitchell, T., & Rock, D. (2018). What can machines learn, and what does it mean for occupations and the economy? *AEA Papers and Proceedings*.

*Recent evidence and methods (2024–2026):*
- Brynjolfsson, E., Chandar, B., & Chen, R. (2025). *Canaries in the Coal Mine? Six Facts about the Recent Employment Effects of Artificial Intelligence.* Stanford Digital Economy Lab (November 2025). — Documents a ~16% relative employment decline for early-career workers (ages 22–25) in the most AI-exposed occupations since late 2022, with adjustment occurring through employment rather than compensation. Directly motivates §1.
- Massenkoff, M., & McCrory, P. (2026). *Labor market impacts of AI: A new measure and early evidence.* Anthropic Economic Index (March 5, 2026). — Introduces "observed exposure," combining LLM capability assessments with real usage data and weighting automation over augmentation across ~800 O\*NET occupations. Closest prior art to the §3.1 exposure layer; see note there.
- Anthropic Economic Index reports: *Uneven geographic and enterprise AI adoption* (Sept 15, 2025; all-U.S.-states usage data); *Economic primitives* (Jan 15, 2026); *Learning curves* (Mar 24, 2026). — State-level and occupation-level AI-usage data; relevant to the §3.1 state rollup and the augmentation/substitution split in §3.2.
- Gmyrek, P., Berg, J., et al. (2025). *Generative AI and Jobs: A Refined Global Index of Occupational Exposure.* ILO Working Paper 140 (May 20, 2025). — An alternative occupational-exposure index; a candidate cross-check for §5.
- Marguerit, D. (2025). *Augmenting or Automating Labor? The Effect of AI Development on New Work, Employment, and Wages.* arXiv:2503.19159 (March 24, 2025). — Separately measures automation vs. augmentation exposure and finds divergent wage effects by skill; informs the §3.2 / §8 augmentation-vs-substitution problem.
- Acemoglu, D. (2025). The simple macroeconomics of AI. *Economic Policy*, 40(121), 13–58 (NBER WP 32487, 2024). — Argues aggregate TFP effects are modest, which is exactly why macro series can mask the local, occupation-specific stress this program targets (§1).
- Acemoglu, D., & Restrepo, P. (2020). Robots and jobs: Evidence from US labor markets. *Journal of Political Economy*. — Regional-exposure cross-check referenced in §5.

### Data Sources (Proposed Additions)
- O\*NET: https://www.onetonline.org/
- BLS OEWS: https://www.bls.gov/oes/
- BLS JOLTS: https://www.bls.gov/jlt/
- WARN Act state notices (varies by state)

### FinMango Foundation
- FinMango Financial Health Barometer Methodology v2.4 (Dec 2025)
- FinMango Financial Health Barometer Whitepaper 2025

### Policy Context
- OpenAI Foundation, *Economic Futures in the Age of AI* (May 2026)
- International Center for Law & Economics (2025). *AI, Productivity, and Labor Markets: A Review of the Empirical Evidence.* — Useful survey of the still-mixed aggregate picture as of 2025.

---

*Financial Health Is A Right, Not A Privilege* | © 2026 FinMango | Open Source License (MIT)
