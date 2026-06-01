# AI Exposure and Household Financial Stress

One-page draft covering the abstract, the two papers, and the roadmap. Paste-ready for Google Docs.

## In one paragraph

We are building an open, monthly, state-by-occupation signal. It joins how exposed an occupation is to AI with how much financial stress its households are showing in their search behavior, things like searches around money, housing, and food. The signal comes from public AI-exposure indices and actual Google Health Trends probabilities rather than the usual 0 to 100 popularity index, and it runs through a documented pipeline anyone can rerun. That one dataset gives us two papers. First we publish the dataset itself. Then we test whether the signal arrives before the official unemployment numbers do.

Neither paper makes a causal claim. We never say AI caused any household's distress. We measure it, we don't assign blame.

## Paper 1: The dataset (we do this first)

What it is. An open, monthly, state-by-occupation measure of AI-exposed household financial stress, released as a reusable dataset plus the pipeline that builds it.

What it claims. That the signal is well built, well documented, reusable, and lines up with known layoff events when you look back at them. The divergence-from-baseline method handles the problem of everyone suddenly searching the same term at once.

What it does not claim. It does not predict unemployment. That is Paper 2's job. And it says nothing causal.

Why it stands alone. There is no open, high-frequency, state-by-occupation read on AI-exposed financial stress today. Releasing it openly, with the pipeline, is the contribution on its own. It is also our best shot at publication, since the open-data-descriptor lane is one where we have published before. It gets a paper out faster and with more certainty, and it becomes the ground Paper 2 stands on.

## Paper 2: The leading indicator (the follow-up)

Working title. Do AI-Exposed Workers Show Financial Stress First?

The claim, in one sentence you can falsify. In the generative-AI period, the combined AI-exposure and financial-stress search signal at month t leads realized occupational unemployment at month t+k, for k of 1 to 3 months, among high-exposure occupations across US states.

The test. A panel regression of occupational unemployment at t+k on the standardized signal at t. The signal leads if the sum of the lead coefficients over k of 1, 2, and 3 comes out positive at the 5 percent level. We fix all of this before we touch the data, so there is no picking the best month after the fact.

What's new. The search-based distress input is the new piece. Joining exposure to unemployment has been done before, so we don't claim that part. What nobody has done is the leading-indicator test. Everyone else measures at the same time or looks backward. We ask whether the signal gets ahead of the official data.

The "so what."
- If the result is positive, we have a public, monthly, sub-national early warning for AI-driven labor stress, months ahead of the BLS.
- If the result is null, it is still a paper. A careful negative that bounds how much search behavior can actually tell us is worth publishing. Writing that down now is what makes pre-registering safe.

## The roadmap

| Phase | What | Paper |
|---|---|---|
| A | Lock the claim, write the literature gap | Foundation and Paper 2 |
| B | Build and freeze the dataset, stand up the pipeline | Foundation |
| C | Write the dataset manuscript, submit to a data venue | Paper 1 |
| D | Post the pre-registration, after data is frozen and before pulling outcomes | Paper 2 |
| E | Pull outcomes, run the lead-lag analysis and robustness checks | Paper 2 |
| F | Write the predictive manuscript, then a working paper, then a journal | Paper 2 |

A and B come first. C ships Paper 1 while D starts Paper 2. E and F follow.

Two rules we don't break:
1. Post Paper 2's pre-registration before we pull its outcome data.
2. Don't draft Paper 2's manuscript until its analysis is in.

## Where we are now

Foundation
- [ ] Data sources confirmed and ingested
- [ ] Reproducible pipeline
- [ ] Frozen, documented snapshot
- [x] Literature gap drafted (full reading of about 20 sources still to do)

Paper 1, dataset descriptor
- [ ] Contribution statement reviewed
- [ ] Manuscript drafted
- [ ] Submitted to a data venue
- [ ] Co-author confirmed

Paper 2, leading indicator
- [x] Claim locked as drafted (co-author sign-off pending)
- [ ] Pre-registration drafted and posted with a timestamp
- [ ] Lead-lag analysis run, kill condition checked
- [ ] Predictive manuscript drafted
- [ ] Working paper posted

## Four things we don't get to forget

1. Measurement, not causation. Neither paper claims AI caused any household's distress.
2. Search saturation is the first thing a reviewer attacks. Show the divergence-from-baseline approach actually working. Don't just assert it.
3. Augmentation is not substitution. Keep them apart everywhere.
4. Pre-register Paper 2 before we see its outcomes. That one move is what makes the predictive result believable later.
