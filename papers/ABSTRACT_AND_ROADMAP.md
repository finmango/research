# AI Exposure and Household Financial Stress

*Scott Glasgow, FinMango*

A short draft of the idea, the two papers, and how I'd sequence them. Sharing it early to see who would like to collaborate.

## In one paragraph

I'm building an open, monthly, state-by-occupation signal that ties an occupation's exposure to AI to the financial stress its households are showing online, the kinds of searches people run when money gets tight, around rent, groceries, bills. It's built from public AI-exposure indices and from actual Google Health Trends probabilities, not the usual 0 to 100 popularity index, and the whole pipeline is documented so anyone can rerun it. One dataset, two papers, and I'd like to get both into peer-reviewed journals. The first introduces the dataset and reports what it shows. The second asks whether the signal moves before the official unemployment numbers do.

To be clear up front: neither paper claims AI caused anyone's financial distress. This is a measurement exercise, nothing more.

## Why this is different, and the gap I'm filling

I spent time in the current literature, and the honest version is that what's new here is the combination. The individual ingredients all exist. What I haven't found anywhere is the three of them stitched together.

What's already out there, so I'm not pretending it's mine:
- Measuring AI exposure is a crowded field. Felten, Eloundou, Brynjolfsson, the ILO, Anthropic's Economic Index, MIT's new Iceberg Index, they all rank which jobs are exposed. I just use these scores as an input.
- Linking exposure to unemployment is heating up. Frank, Ahn and Moro get closest, and there's newer work from the St. Louis and Dallas Feds and from Stanford. But they run exposure scores against realized unemployment, mostly at the same point in time, and the closest paper stops in 2019, before ChatGPT existed.
- Using search behavior to read financial distress is old news. Choi and Varian, the FEARS index, the whole unemployment-nowcasting literature, they've shown for years that searches about money and joblessness can run ahead of the official figures. That method isn't mine; I'm borrowing it.

So here's the opening. Nobody has taken a high-frequency household financial-stress search signal, joined it to AI exposure, and tested it as a leading indicator of occupational unemployment, at the state-by-month level, in the generative-AI period, using real Health Trends probabilities instead of the 0 to 100 index. That's the contribution.

A word on why each paper survives alone. Paper 1 works because the dataset simply doesn't exist yet. There's no open, monthly, state-by-occupation read on this built from conditional-probability search data, and data papers get judged on whether they're rigorous and reusable, which this will be. Paper 2 works because everyone else is either measuring in the present or looking back, and I'm asking whether the signal gets out ahead of the realized data, with the test locked down in advance so the answer counts either way.

A risk I'd rather name than hide: this was a quiet corner 18 months ago and it's getting busy, with some well-funded groups circling. To me that says move now. Two things give me cover, getting Paper 1 out the door quickly, and time-stamping Paper 2's pre-registration early. The Health Trends access is also hard to replicate, which helps.

## Paper 1: The dataset and what it shows (I'd do this first)

I want this to be a real journal article, not a data dump. It introduces the dataset and the pipeline, and it reports what the data actually shows, descriptively. That second part is what lifts it from a deposit into something an editor will engage with.

The dataset itself is an open, monthly, state-by-occupation measure of AI-exposed household financial stress, built from the public exposure indices and from actual Health Trends probabilities, and shipped with the pipeline that produces it.

Then the findings, which is where it earns its keep. For the first time you can look at:
- which occupations and which states are carrying the most AI-exposed financial stress, and how that has shifted month to month through the generative-AI period
- how the signal behaved around real layoff and restructuring events, written up as case studies instead of just asserted
- where the high-exposure stress clusters geographically, and where it doesn't
- a validation section that puts the divergence-from-baseline method on display, so a reviewer can watch saturation get handled instead of taking my word for it

All of that stays descriptive. I'm not going to let Paper 1 drift into prediction, that's Paper 2's job, and keeping the wall up is part of what makes Paper 2 credible later, since its test has to stay genuinely unexplored until I pre-register it. And nothing causal, ever.

On where it lands: the data and methods venues are the floor I'm confident in, Scientific Data at Nature for the flagship version, Data in Brief for something faster, Data and Policy if I play up the policy angle. Because it carries actual findings and not just a dataset, it can also reach further, into applied economics, labor, or computational social science. I'd write it to clear the data venues while leaving that wider door open.

## Paper 2: The leading indicator (the follow-up)

Working title: Do AI-Exposed Workers Show Financial Stress First?

The claim, and it's falsifiable: in the generative-AI period, the combined AI-exposure and financial-stress search signal at month t leads realized occupational unemployment at month t+k, for k of 1 to 3 months, among high-exposure occupations across US states.

How I'd test it: a panel regression of occupational unemployment at t+k on the standardized signal at t. The signal leads if the lead coefficients over k of 1, 2 and 3 sum to something positive at the 5 percent level. All of that gets fixed before I touch the data, so there's no quietly picking the k that looks best afterward.

The genuinely new piece is the search-based distress input. Joining exposure to unemployment has been done, so I leave that alone. The leading-indicator test is the part nobody has run. Everyone in this space works in the present or looks backward, and I'm asking whether the signal gets there first.

Either result is worth writing up:
- positive, and I've got a public, monthly, sub-national early warning for AI-driven labor stress that runs months ahead of the BLS
- null, and it's still a paper, a careful bound on how little or how much search behavior can tell us here. Saying that out loud now is exactly what makes the pre-registration safe.

## The roadmap

| Phase | What | Paper |
|---|---|---|
| A | Lock the claim, write the literature gap | Foundation and Paper 2 |
| B | Build and freeze the dataset, stand up the pipeline | Foundation |
| C | Write the dataset-and-findings manuscript, submit to a journal | Paper 1 |
| D | Post the pre-registration, after data is frozen and before pulling outcomes | Paper 2 |
| E | Pull outcomes, run the lead-lag analysis and robustness checks | Paper 2 |
| F | Write the predictive manuscript, then a working paper, then a journal | Paper 2 |

A and B first. C ships Paper 1 while D gets Paper 2 going. E and F follow.

Two rules I won't bend:
1. Paper 2's pre-registration goes up before I pull a single outcome.
2. No drafting Paper 2's manuscript until the analysis is in hand.

## Where things stand

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

## Four things I keep reminding myself

1. Measurement, not causation. Neither paper says AI caused anyone's distress.
2. Search saturation is the first thing a reviewer will go after, so I have to actually show the divergence-from-baseline method working, not just claim it.
3. Keep augmentation and substitution separate, everywhere.
4. Pre-register Paper 2 before I see its outcomes. That single move is what makes the result believable down the line.

## References

The work I point to in the gap section, grouped the same way.

AI-exposure measurement (my inputs and the crowded part):
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

Reading distress from search behavior (the method I borrow):
- Choi and Varian (2012), Predicting the present with Google Trends, Economic Record. https://onlinelibrary.wiley.com/doi/10.1111/j.1475-4932.2012.00809.x
- Da, Engelberg and Gao (2015), The sum of all FEARS: investor sentiment and asset prices, Review of Financial Studies. https://academic.oup.com/rfs/article-abstract/28/1/1/1682440
- Grybauskas et al. (2023), Nowcasting unemployment using neural networks and multi-dimensional Google Trends data, Economies 11(5):130. https://www.mdpi.com/2227-7099/11/5/130
