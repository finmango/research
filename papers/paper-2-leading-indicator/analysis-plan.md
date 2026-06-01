# Step 5. Analysis

Two-paper plan: this belongs to Paper 2, the leading-indicator study. Paper 1
makes no predictive claim and runs no lead-lag test. See ../README.md.

This is where we get the headline result and the checks that defend it. This
step gates the paper. No result, no paper.

Everything here has to match what we pre-registered in step 3. If we deviate, it
goes in a section labeled exploratory. We don't quietly change the plan.

## 5.1 The headline (the claim itself)

- [ ] Lead-lag test. signal at t against unemployment at t plus k, for k of one,
      two, and three months, in high-exposure occupations.
- [ ] Report the pre-registered statistic against its threshold.
- [ ] Did it clear the kill condition from step 3? Write down yes or no, plainly.

## 5.2 The robustness checks (reviewers will demand all of these)

- [ ] Placebo, H2. Low-exposure occupations should show no lead.
- [ ] Exposure weighting. Equal-weight versus the alternatives we promised in
      brief section 3.1.
- [ ] Search saturation, the first thing they'll attack (brief section 8). Show
      the result survives different baseline windows. Put raw next to
      divergence-normalized so the difference is obvious.
- [ ] Augmentation versus substitution, H3. The augmentation terms shouldn't
      predict. The substitution terms should.
- [ ] Out of sample. Does the signal beat a naive AR baseline, or not?
- [ ] Suppression. Results hold up across the cell-size threshold.

## 5.3 What each outcome means (decide this before we look)

| Result | What it means | How we frame it |
|---|---|---|
| Significant lead, survives the checks | The leading indicator works | Positive headline |
| Significant but fragile | Suggestive, no more | Honest: suggestive, needs more data |
| Null | No lead we can detect | A bounded negative result, still publishable |

## 5.4 What we hand to the manuscript

- [ ] Figure 1. Signal against realized unemployment, high versus low exposure.
- [ ] Figure 2. Lead-lag cross-correlation by k.
- [ ] Table 1. Main estimates plus the robustness columns.
- [ ] A map. State by cluster signal. Same thing the public dashboard shows.
- [ ] Every figure rebuilt by script. That feeds step 7.

Status: headline run / robustness done / kill condition checked
