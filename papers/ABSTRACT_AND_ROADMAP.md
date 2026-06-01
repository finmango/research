# AI Exposure and Household Financial Stress

*One-page draft — abstract, the two papers, and the roadmap. Paste-ready for Google Docs.*

---

## In one paragraph

We are building an open, monthly, state-by-occupation signal that joins how
exposed an occupation is to AI with how much financial stress its households are
showing in their search behavior (search, housing, food). The signal is built
from public AI-exposure indices and actual Google Health Trends probabilities —
not the usual 0–100 popularity index — through a documented, reproducible
pipeline. From that one dataset we get two papers: first we publish the dataset
itself, then we test whether the signal arrives *before* the official
unemployment numbers do.

Neither paper makes a causal claim. We never say AI caused any household's
distress. We measure, we don't blame.

---

## Paper 1 — The dataset (we do this first)

**What it is.** An open, monthly, state-by-occupation measure of AI-exposed
household financial stress, released as a documented, reusable dataset plus the
pipeline that builds it.

**What it claims.** That the signal is well-built, well-documented, reusable,
and descriptively consistent with known layoff events. The
divergence-from-baseline method handles the "everyone is searching this now"
saturation problem.

**What it does not claim.** It does not predict unemployment (that's Paper 2),
and it says nothing causal.

**Why it stands alone.** There is no open, high-frequency, state-by-occupation
read on AI-exposed financial stress today. Releasing it openly, with the
pipeline, is the contribution. It is also our highest-probability venue — the
open-data-descriptor lane, where we've published before — so it gets a paper out
faster and surer, and becomes the foundation Paper 2 stands on.

---

## Paper 2 — The leading indicator (the follow-up)

**Working title.** *Do AI-Exposed Workers Show Financial Stress First?*

**The claim (one sentence, falsifiable).** In the generative-AI period, the
combined AI-exposure and financial-stress search signal at month *t* leads
realized occupational unemployment at month *t+k*, for *k* of 1 to 3 months,
among high-exposure occupations across US states.

**The test.** A panel regression of occupational unemployment at *t+k* on the
standardized signal at *t*. The signal leads if the sum of the lead coefficients
over *k* = 1, 2, 3 is positive at the 5% level. We fix this before we look at the
data — no picking the best month after the fact.

**What's new.** The search-based distress *input* is the new piece (joining
exposure to unemployment already exists in the literature). The leading-indicator
test is the cleanest claim — everyone else measures at the same time or looks
backward; we ask whether the signal gets *ahead* of the official data.

**The "so what."**
- *Positive result:* a public, monthly, sub-national early warning for AI-driven
  labor stress, months ahead of the BLS.
- *Null result:* still a paper — a careful negative that bounds how much search
  behavior can tell us. Writing that down now is what makes pre-registering safe.

---

## The roadmap

| Phase | What | Paper |
|---|---|---|
| A | Lock the claim, write the literature gap | Foundation + Paper 2 |
| B | Build and freeze the dataset; stand up the pipeline | Foundation |
| C | Write the dataset manuscript; submit to a data venue | Paper 1 |
| D | Post the pre-registration (after data is frozen, before pulling outcomes) | Paper 2 |
| E | Pull outcomes; run the lead-lag analysis and robustness checks | Paper 2 |
| F | Write the predictive manuscript; working paper, then journal | Paper 2 |

A and B come first. C ships Paper 1 while D starts Paper 2. E and F follow.

**Two rules we don't break:**
1. Post Paper 2's pre-registration *before* we pull its outcome data.
2. Don't draft Paper 2's manuscript until its analysis is in.

---

## Where we are now

**Foundation**
- ☐ Data sources confirmed and ingested
- ☐ Reproducible pipeline
- ☐ Frozen, documented snapshot
- ☒ Literature gap drafted (full ~20-source reading still to do)

**Paper 1 — dataset descriptor**
- ☐ Contribution statement reviewed
- ☐ Manuscript drafted
- ☐ Submitted to a data venue
- ☐ Co-author confirmed

**Paper 2 — leading indicator**
- ☒ Claim locked as drafted (co-author sign-off pending)
- ☐ Pre-registration drafted and posted with a timestamp
- ☐ Lead-lag analysis run; kill condition checked
- ☐ Predictive manuscript drafted
- ☐ Working paper posted

---

## Four things we don't get to forget

1. **Measurement, not causation.** Neither paper claims AI caused any
   household's distress.
2. **Search saturation** is the first thing a reviewer attacks. Show the
   divergence-from-baseline approach actually working — don't just assert it.
3. **Augmentation is not substitution.** Keep them apart everywhere.
4. **Pre-register Paper 2 before we see its outcomes.** That one move is what
   makes the predictive result believable later.
