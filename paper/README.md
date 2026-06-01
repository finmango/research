# AI Exposure and Household Financial Stress

Two papers, one dataset. This folder is the plan for turning the positioning
brief (`../AI_ECONOMIC_IMPACT_2026.md`) into published work.

## Why two papers

We have to build and document the dataset before we can run any predictive test.
That is step 4, and it gates step 5. So the dataset gets built either way. The
only real decision is whether we also publish it on its own, and we do, for
three reasons:

- It is our highest-probability venue. The open-data-descriptor lane is where
  we have already published (the COVID open-data work, including Scientific
  Data).
- It gets an AI paper out faster and surer. It does not wait on a year of
  generative-AI-period outcome data, and it can't come back null.
- It becomes the foundation the predictive paper stands on. If the predictive
  result later lands strong, great. If it comes back null, we have already
  banked a publication.

Neither paper makes a causal claim. Paper 1 makes no predictive claim at all.
One co-author goes on both.

## Paper 1. The dataset (do this first)

**What it is.** A data descriptor. An open, monthly, state-by-occupation signal
that joins occupational AI-exposure to household financial-stress search
behavior, documented as a reusable dataset plus the pipeline that builds it.

**The contribution sentence.**

> We release an open, monthly, state-by-occupation measure of AI-exposed
> household financial stress, built from public exposure indices and actual
> Google Health Trends probabilities, with a documented, reproducible pipeline.

**What it claims.** That the signal is well-built, well-documented, and
reusable, and that it is consistent with known layoff events descriptively. It
does not claim the signal predicts anything.

**Venue.** A data or methods outlet (Scientific Data, Data in Brief, or a
software paper for the pipeline).

**What it needs.** Steps 4 (data) and 7 (reproducibility), a descriptor-style
manuscript (step 6), and a data-venue submission (step 8). No outcome data, no
pre-registration, no lead-lag analysis.

## Paper 2. The leading indicator (the follow-up)

**What it is.** The predictive study. Using Paper 1's dataset, does the signal
lead realized occupational unemployment by one to three months in high-exposure
occupations. Working title: Do AI-Exposed Workers Show Financial Stress First?

**The claim** is locked in `01-claim/claim.md`.

**What it claims.** A pre-registered, falsifiable predictive lead. Still
measurement, not causation.

**Venue.** A working paper first (arXiv, SSRN, or NBER), then an applied-economics
or policy outlet. The result picks the home.

**What it needs.** The locked claim (1), the literature gap (2), the posted
pre-registration (3), Paper 1's frozen dataset (4), the analysis (5), a
predictive manuscript (6), and submission (8). This is where the co-author's
econometrics earns its keep.

## The roadmap

| Phase | What | Which paper |
|---|---|---|
| A | Lock the claim, write the literature gap | Both |
| B | Build and freeze the dataset; stand up the reproducible pipeline | Paper 1 core, Paper 2 input |
| C | Descriptor manuscript; submit to a data venue | Paper 1 |
| D | Post the pre-registration (after the data is frozen, before pulling outcomes) | Paper 2 |
| E | Pull outcomes; run the lead-lag analysis and robustness | Paper 2 |
| F | Predictive manuscript; working paper, then journal | Paper 2 |

Order: A and B first. C ships Paper 1 while D starts Paper 2. E and F follow.
Two rules we don't break: post Paper 2's pre-registration before we pull its
outcome data, and don't draft Paper 2's manuscript (F) until its analysis (E) is
in.

## Which folder feeds which paper

| Folder | Paper 1 (dataset) | Paper 2 (leading indicator) |
|---|---|---|
| `01-claim/` | | the predictive claim |
| `02-literature/` | the data-contribution framing | the predictive gap |
| `03-preregistration/` | | the registered design |
| `04-data/` | the contribution itself | the input |
| `05-analysis/` | | the lead-lag test |
| `06-manuscript/` | descriptor draft | predictive draft |
| `07-reproducibility/` | shared, and a selling point | shared |
| `08-submission/` | data venue | working paper, then journal |

## Where we are

Paper 1 (dataset):
- [ ] Data sources confirmed and ingested (step 4)
- [ ] Reproducible pipeline (step 7)
- [ ] Frozen, documented snapshot
- [ ] Descriptor manuscript drafted
- [ ] Submitted to a data venue
- [ ] Co-author confirmed

Paper 2 (leading indicator):
- [x] Claim locked as drafted (co-author sign-off pending)
- [ ] Literature gap drafted; full reading (about 20 sources) still to do
- [ ] Pre-registration drafted; posted with a timestamp
- [ ] Lead-lag analysis run; kill condition checked
- [ ] Predictive manuscript drafted
- [ ] Working paper posted

## Four things we don't get to forget

These come from section 8 of the brief. They are the ones that sink papers like
this.

1. Measurement, not causation. Neither paper claims AI caused any household's
   distress.
2. Search saturation is the first thing a reviewer attacks. Show the
   divergence-from-baseline approach actually working, don't just assert it.
   Paper 1's technical validation is the natural place to do that.
3. Augmentation is not substitution. Keep them apart everywhere.
4. Pre-register Paper 2 before we see its outcomes. That one move is what makes
   the predictive result believable later.
