# AI Exposure and Household Financial Stress

One-page draft covering the abstract, the two papers, and the roadmap.

## In one paragraph

Building an open, monthly, state-by-occupation signal. It joins how exposed an occupation is to AI with how much financial stress its households are showing in their search behavior, things like searches around money, housing, and food. The signal comes from public AI-exposure indices and actual Google Health Trends probabilities rather than the usual 0 to 100 popularity index, and it runs through a documented pipeline anyone can rerun. That one dataset gives us two papers, and we are aiming both at peer-reviewed academic journals. The first introduces the dataset and reports what it shows. The second tests whether the signal arrives before the official unemployment numbers do.

Neither paper makes a causal claim. We never say AI caused any household's distress. We measure it, we don't assign blame.

## Why this is different, and the gap we fill

I checked the current literature, and the honest position is that the novelty here is in the combination, not in any single ingredient. Each piece exists on its own. Nobody has put them together the way we are.

What already exists, so we don't claim it:
- Measuring AI exposure is crowded. Felten, Eloundou, Brynjolfsson, the ILO, Anthropic's Economic Index, and MIT's new Iceberg Index all rank which jobs are exposed. We are not adding to this. We use these scores as an input.
- Linking AI exposure to unemployment is now active. Frank, Ahn and Moro come closest, and there is recent work from the St. Louis and Dallas Feds and Stanford. But this work uses exposure scores against realized unemployment, mostly looks at it at the same point in time, and the closest paper stops in 2019, before ChatGPT.
- Reading financial distress from search behavior is well established. Choi and Varian, the FEARS index, and the unemployment-nowcasting literature all show that searches about money, recession, and joblessness can lead the official numbers. We borrow the method, we don't claim it.

The gap nobody has filled. No one has joined a high-frequency household financial-stress search signal to AI exposure and tested it as a leading indicator of occupational unemployment, at the state-by-month level, in the generative-AI period, using actual Google Health Trends probabilities rather than the 0 to 100 index. That combination is the contribution.

How each paper is different on its own terms:
- Paper 1 is different because the dataset itself does not exist anywhere else. There is no open, monthly, state-by-occupation read on AI-exposed financial stress built from conditional-probability search data. A data paper is judged on whether it is rigorous, documented, and reusable, not on surprise, and this one clears that bar.
- Paper 2 is different because everyone else measures at the same point in time or looks backward. We test whether the signal arrives before realized occupational unemployment does, and we fix the test in advance so the result is believable either way.

One honest caveat. This was a quiet niche 18 months ago and is busier now, with well-funded groups nearby. That is an argument for moving, not waiting. Two things protect us: getting Paper 1 out fast, and posting Paper 2's pre-registration early so we have a dated flag in the ground. Our access to the Google Health Trends data is also hard for others to replicate, which gives the work a moat.

## Paper 1: The dataset and what it shows (we do this first)

This is a full academic paper, not just a data release. It does two jobs at once. It introduces the dataset and the pipeline, and it reports what the data shows on its own terms, descriptively. Both halves are publishable, and together they make a paper a journal will take seriously rather than a bare data deposit.

What it is. An open, monthly, state-by-occupation measure of AI-exposed household financial stress, built from public AI-exposure indices and actual Google Health Trends probabilities, released with the documented pipeline that produces it.

What it shows. This is the part that turns it into a real empirical paper. We report the descriptive picture the dataset makes possible for the first time:
- Which occupations and which states carry the most AI-exposed financial stress, and how that has moved month to month across the generative-AI period.
- How the signal behaved around known layoff and restructuring events, shown as case studies rather than asserted.
- The geography of it, where high-exposure stress clusters and where it doesn't.
- A validation section that shows the divergence-from-baseline method actually working, so a reviewer can see saturation is handled rather than take our word for it.

What it claims. That the signal is well built, well documented, and reusable, that it lines up with known events when you look back, and that the patterns above are real features of the data. All of this is descriptive.

What it does not claim. It does not predict unemployment. That is Paper 2's job, and we keep the line clean on purpose. It says nothing causal. We never claim AI caused any household's distress. Holding that line is also what protects Paper 2, since the predictive test has to stay genuinely pre-registered and unexplored until then.

Why it stands on its own. There is no open, high-frequency, state-by-occupation read on AI-exposed financial stress today. Building it, documenting it, and showing what it reveals is a contribution in its own right. It is also our surest route to a publication, it gets a paper out faster, and it becomes the ground Paper 2 stands on.

Where it can land. The data-and-methods venues are the safe floor: Scientific Data (Nature) for the flagship descriptor, Data in Brief for a faster lighter version, Data and Policy if we lean on the policy angle. Because we are carrying real descriptive findings, the same work also reaches broader empirical journals in applied economics, labor, and computational social science. The plan is to aim the manuscript so it qualifies for the data venues without giving up the shot at a wider economics readership.

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
| C | Write the dataset-and-findings manuscript, submit to a journal | Paper 1 |
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
- [ ] Descriptive findings and validation section drafted
- [ ] Manuscript drafted
- [ ] Target journal chosen and submitted
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

## References

The work we point to in the gap section, grouped the same way.

AI-exposure measurement (our inputs and the crowded part):
- Felten, Raj and Seamans (2021), Occupational, industry, and geographic exposure to artificial intelligence, Strategic Management Journal. https://sms.onlinelibrary.wiley.com/doi/full/10.1002/smj.3286
- Eloundou, Manning, Mishkin and Rock (2023), GPTs are GPTs: an early look at the labor market impact potential of large language models. https://arxiv.org/abs/2303.10130
- Brynjolfsson, Mitchell and Rock (2018), What can machines learn, and what does it mean for occupations and the economy?, AEA Papers and Proceedings. https://www.aeaweb.org/articles?id=10.1257/pandp.20181019
- Anthropic Economic Index, labor market impacts of AI. https://www.anthropic.com/research/labor-market-impacts
- MIT Iceberg Index (2025), measuring workforce exposure in the AI economy. https://arxiv.org/pdf/2510.25137

Linking AI exposure to unemployment (the active neighbors):
- Frank, Ahn and Moro (2025), AI exposure predicts unemployment risk, PNAS Nexus. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11983276/ and preprint https://arxiv.org/pdf/2308.02624
- St. Louis Fed (2025), Is AI contributing to rising unemployment? https://www.stlouisfed.org/on-the-economy/2025/aug/is-ai-contributing-unemployment-evidence-occupational-variation
- Dallas Fed (2026), Young workers' employment drops in occupations with high AI exposure. https://www.dallasfed.org/research/economics/2026/0106
- AI-exposed jobs deteriorated before ChatGPT (2026 preprint). https://arxiv.org/pdf/2601.02554
- PIIE (2026), Research on AI and the labor market is still in the first inning. https://www.piie.com/blogs/realtime-economics/2026/research-ai-and-labor-market-still-first-inning

Reading distress from search behavior (the method we borrow):
- Choi and Varian (2012), Predicting the present with Google Trends, Economic Record. https://onlinelibrary.wiley.com/doi/10.1111/j.1475-4932.2012.00809.x
- Da, Engelberg and Gao (2015), The sum of all FEARS: investor sentiment and asset prices, Review of Financial Studies. https://academic.oup.com/rfs/article-abstract/28/1/1/1682440
- Grybauskas et al. (2023), Nowcasting unemployment using neural networks and multi-dimensional Google Trends data, Economies 11(5):130. https://www.mdpi.com/2227-7099/11/5/130
