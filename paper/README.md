# Paper Project: AI Exposure and Household Financial Stress

A step-by-step workspace for turning the FinMango positioning brief
(`../AI_ECONOMIC_IMPACT_2026.md`) into a publishable empirical paper.

**Working title:** *Do AI-Exposed Workers Show Financial Stress First? A
State × Occupation Leading-Indicator Approach*

**One-sentence claim (the thing the whole paper defends):**
> A search-behavior + AI-exposure signal leads realized occupational
> unemployment by 1–3 months in high-exposure occupations across U.S. states.

---

## How to use this folder

Each numbered subfolder is one step. Work them roughly in order — but note
the hard dependency: **you cannot write the manuscript (06) until the
validation result exists (05).** Steps 1–3 are desk work you can do now;
steps 4–5 are the real labor and gate everything else.

| # | Folder | What it produces | Can start now? |
|---|--------|------------------|----------------|
| 1 | `01-claim/` | The single falsifiable claim + contribution statement | ✅ now |
| 2 | `02-literature/` | Positioning, the gap you own, reading list | ✅ now |
| 3 | `03-preregistration/` | Time-stamped, locked analysis design | ✅ now (before touching outcome data) |
| 4 | `04-data/` | Frozen, documented dataset + dictionary | ⏳ needs pipeline work |
| 5 | `05-analysis/` | Lead-lag result + robustness battery | ⏳ needs data |
| 6 | `06-manuscript/` | The actual paper draft | ❌ blocked until 05 |
| 7 | `07-reproducibility/` | Public code + replication package | ⏳ alongside 04–05 |
| 8 | `08-submission/` | Venue choice, co-author, timeline | ✅ can plan now |

## Progress tracker

- [ ] **1. Claim locked** — single falsifiable sentence agreed
- [ ] **2. Literature mapped** — gap statement written, ~20 sources read
- [ ] **3. Pre-registration posted** — OSF/AsPredicted timestamp obtained
- [ ] **4. Data assembled & frozen** — versioned snapshot + dictionary
- [ ] **5. Analysis run** — headline result + robustness complete
- [ ] **6. Manuscript drafted** — full draft through limitations
- [ ] **7. Replication package** — public repo regenerates every figure
- [ ] **8. Submitted** — working paper posted; co-author confirmed

## Guardrails (from the brief's §8 — do not lose these)

1. **Measurement, not causation.** Frame as a leading-indicator/measurement
   paper. Do not claim AI *causes* any household's distress.
2. **Search saturation is the #1 reviewer target.** The
   divergence-from-baseline normalization must be *shown working*, not asserted.
3. **Augmentation ≠ substitution.** Keep them separate everywhere; conflating
   them is a known failure mode.
4. **Pre-register before you see outcomes.** It's the credibility multiplier.
