# Step 1 — Lock the Claim

**Goal:** one falsifiable sentence that governs every later decision. If a
result wouldn't change whether this sentence is true, it doesn't belong in
the paper.

---

## 1.1 The primary claim (fill in / edit)

> A search-behavior + AI-exposure signal leads realized occupational
> unemployment by **___ months** in high-exposure occupations across U.S.
> states, with [statistic] ≥ [threshold].

**Decisions to pin down:**
- Lead window: 1–3 months? (state in §3 preregistration)
- Outcome series: BLS occupational unemployment? LAUS? CPS?
- "High-exposure" cutoff: top tercile / quartile of the §3.1 composite?
- Headline statistic: cross-correlation at lag k? Granger-style test?
  Out-of-sample nowcast error reduction vs. a no-signal baseline?

## 1.2 Contribution statement (what's new)

Write 3–4 bullets. Draft:

- **New construct.** First measure that *joins* occupational AI-exposure to
  household financial-stress signals (search, housing, food) at the
  state × occupation level. (The exposure half exists in prior work; the
  join does not — see `../02-literature/`.)
- **Leading-indicator validation.** Tests whether the joined signal
  anticipates realized occupational unemployment, with a pre-registered
  kill condition.
- **Open infrastructure.** Public, reproducible pipeline + dataset under MIT,
  extending the running FinMango Barometer.
- *(Optional, if achievable)* **Augmentation vs. substitution separation** —
  an empirical handle on a distinction the literature treats as open.

## 1.3 What this paper is NOT (scope guards)

- Not a causal-identification paper (no claim AI *causes* distress).
- Not a new exposure index (we compose existing ones).
- Not a policy/UBI paper (explicitly out of lane per brief §6).

## 1.4 The "so what" test

If the result is **positive**: a publicly available, monthly, sub-national
leading indicator of AI-driven labor stress — months ahead of BLS.
If the result is **null**: still publishable as a careful negative result that
bounds how much search behavior can nowcast occupational displacement.
Either outcome is a paper. Write that down — it's what makes pre-registration safe.

---

**Status:** ☐ draft  ☐ reviewed with co-author  ☐ locked
