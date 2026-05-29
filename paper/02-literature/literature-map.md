# Step 2. Literature Positioning

Know what's already out there. Then we can say, in one paragraph, what we do
that nobody else does. Figure on 20 to 25 focused reads across three areas.

## 2.1 The gap we own (draft, tighten as we read)

Plenty of people measure AI exposure, meaning which jobs are at risk. A few
recent papers measure the effects that already landed (the Stanford Canaries
work on payroll, Anthropic's observed-exposure measure on the CPS). One paper
gets closest to us: Frank, Ahn and Moro (2025) join AI-exposure scores to
state-by-occupation unemployment risk and find that an ensemble predicts it.
But they use exposure scores against realized unemployment claims, they treat
it contemporaneously, and their data stops in 2019. Separately, a long
literature nowcasts unemployment from Google Trends, and some of it finds that
distress-related searches lead jobless claims. Nobody has put the two
together: a high-frequency household financial-stress search signal, tested as
a leading indicator of occupational unemployment in the generative-AI period.
That's the paper.

## 2.2 Three areas to cover

### A. AI-exposure measurement (we have most of these)
- Felten, Raj and Seamans (2021), AIOE. One of our inputs.
- Eloundou, Manning, Mishkin and Rock (2023), GPTs are GPTs. One of our inputs.
- Brynjolfsson, Mitchell and Rock (2018), SML. One of our inputs.
- Marguerit (2025), arXiv:2503.19159. Automation versus augmentation, wages.
- ILO Working Paper 140 (Gmyrek, Berg et al., 2025). Refined global index.
- Acemoglu (2025), Economic Policy 40(121):13 to 58. Aggregate TFP is modest.

### B. The effects that already landed (the new neighbors, read these closely)
- Frank, Ahn and Moro (2025), PNAS Nexus 4(4):pgaf107, arXiv:2308.02624. THE
  CLOSEST NEIGHBOR. Joins AI-exposure scores to state-by-occupation unemployment
  risk (UI claims, 2010 to 2019). Ensemble of exposure scores beats baseline by
  about 18 points. No search signal, no lead-lag test, pre-ChatGPT. This is the
  paper our related-work paragraph has to distinguish from most carefully.
- Brynjolfsson, Chandar and Chen (2025), Canaries in the Coal Mine (Stanford
  Digital Economy Lab). About a 16% relative drop for ages 22 to 25 in exposed
  jobs.
- Massenkoff and McCrory (2026), Labor market impacts of AI (Anthropic Economic
  Index). An exposure neighbor, but occupation-level only with no state
  dimension, and contemporaneous, not our closest. Observed exposure from usage
  and capability, automation-weighted, about 800 O\*NET occupations.
- Anthropic Economic Index reports (Sept 2025 geographic, Jan 2026, Mar 2026).
- HBS Working Paper 25-039, Displacement or Complementarity? Still to read.

### C. Search-based nowcasting (the method precedent, still to read)
- Choi and Varian (2012), Predicting the Present with Google Trends. The seed.
- D'Amuri and Marcucci, Google Trends for unemployment forecasting. Track down.
- [authors TO VERIFY] (2023). "Nowcasting Unemployment Using Neural Networks and
  Multi-Dimensional Google Trends Data." Economies 11(5):130, MDPI. Finds that
  searches like "Unemployment" and "Severance Pay" surged before initial jobless
  claims, and that distress keywords beyond pure job-search terms (mental health,
  consumption, and so on) improve forecasting. Useful precedent that search can
  lead claims, and that a multi-dimensional distress ontology helps.
- Add: recent Google Health Trends methodology and the privacy/aggregation work.
- Add: divergence-from-baseline and anomaly-detection refs for the section 3.2
  normalization.

## 2.3 Reading log

| Cite | Area | Takeaway | How it relates to our claim | Read? |
|---|---|---|---|---|
| Choi and Varian 2012 | C | | search to labor nowcasting works | no |
| Massenkoff and McCrory 2026 | B | observed-exposure method | exposure neighbor, but occupation-level only, contemporaneous, null result; not our closest | yes |
| Canaries 2025 | B | the effect is real but late | our signal aims to get ahead of it | yes |
| Frank, Ahn and Moro 2025 | B | exposure ensemble predicts state-by-occupation UI risk | closest neighbor; we add the search input and the lead test | yes |
| [authors TO VERIFY] 2023 (Economies 11(5):130) | C | distress searches lead jobless claims; multi-dim ontology helps | method precedent for our search signal | no |
| | | | | |

## 2.4 The related-work paragraph

Write this last, once the table is full. About 150 words. Cover A, B and C, then
name the gap. Don't pad it.

Status: areas scoped / reading log filled / gap paragraph written
