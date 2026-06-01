# AI Exposure and Household Financial Stress

Two papers, one dataset. This folder is the plan for turning the positioning
brief (`../AI_ECONOMIC_IMPACT_2026.md`) into published work.

## The shape

```
00-foundation/             shared by both papers
  data/                    the dataset: Paper 1's contribution, Paper 2's input
  reproducibility/         the open pipeline and replication package
  literature-map.md        one literature landscape, frames both papers
paper-1-data-descriptor/   the open dataset, published on its own (do first)
paper-2-leading-indicator/ the pre-registered predictive study (the follow-up)
```

Each paper folder has its own README with the steps in order. The foundation is
the work both papers stand on.

## Why two papers

We have to build and document the dataset before we can run any predictive test,
so the dataset gets built either way. The only real decision is whether we also
publish it on its own, and we do: it is our highest-probability venue (the
open-data-descriptor lane, where we have already published), it gets an AI paper
out faster and surer, and it becomes the foundation the predictive paper stands
on. If the predictive result lands strong, great. If it comes back null, we have
already banked a publication.

Neither paper makes a causal claim. Paper 1 makes no predictive claim at all.
One co-author goes on both.

## Paper 1. The dataset (do this first)

An open, monthly, state-by-occupation signal that joins occupational AI-exposure
to household financial-stress search behavior, released as a documented,
reusable dataset plus the pipeline that builds it. Descriptive. No predictive or
causal claim. Targets a data or methods venue. Full plan in
`paper-1-data-descriptor/README.md`.

## Paper 2. The leading indicator (the follow-up)

Using Paper 1's dataset, does the signal lead realized occupational unemployment
by one to three months in high-exposure occupations. Pre-registered, falsifiable,
still measurement and not causation. Working title: Do AI-Exposed Workers Show
Financial Stress First? Full plan in `paper-2-leading-indicator/README.md`.

## The roadmap

| Phase | What | Where |
|---|---|---|
| A | Lock the claim, write the literature gap | foundation + paper 2 |
| B | Build and freeze the dataset; stand up the pipeline | foundation |
| C | Descriptor manuscript; submit to a data venue | paper 1 |
| D | Post the pre-registration (after the data is frozen, before pulling outcomes) | paper 2 |
| E | Pull outcomes; run the lead-lag analysis and robustness | paper 2 |
| F | Predictive manuscript; working paper, then journal | paper 2 |

A and B first. C ships Paper 1 while D starts Paper 2. E and F follow. Two rules
we don't break: post Paper 2's pre-registration before we pull its outcome data,
and don't draft Paper 2's manuscript until its analysis is in.

## Where we are

Foundation:
- [ ] Data sources confirmed and ingested
- [ ] Reproducible pipeline
- [ ] Frozen, documented snapshot
- [x] Literature gap drafted; full reading (about 20 sources) still to do

Paper 1 (dataset descriptor):
- [ ] Contribution statement reviewed
- [ ] Descriptor manuscript drafted
- [ ] Submitted to a data venue
- [ ] Co-author confirmed

Paper 2 (leading indicator):
- [x] Claim locked as drafted (co-author sign-off pending)
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
