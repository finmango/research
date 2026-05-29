# Step 1. Lock the Claim

One sentence. Falsifiable. Everything after it answers to it. If a result
wouldn't change whether that sentence is true, it doesn't go in the paper.

## 1.1 The claim (edit this until it's right)

> A search-behavior plus AI-exposure signal leads realized occupational
> unemployment by ___ months in high-exposure occupations across US states,
> with [statistic] of at least [threshold].

What we have to nail down:

- The lead window. One to three months? Whatever we pick goes in the
  pre-registration and we don't move it later.
- The outcome series. BLS occupational unemployment, LAUS, or CPS.
- What "high exposure" means. Top third or top quarter of the section 3.1
  composite.
- The headline number. Cross-correlation at lag k, a Granger-style test, or how
  much we beat a no-signal nowcast.

## 1.2 What's actually new

Three or four bullets, no more. First pass:

- A new input. Our signal is built from high-frequency household
  financial-stress search behavior (search, housing, food), not from exposure
  scores or realized unemployment claims. The exposure half exists already.
  Frank, Ahn and Moro (2025) even joined exposure to state-by-occupation
  unemployment risk already, so that join is not ours to claim. The
  search-based distress input is what's new.
- The leading-indicator test. This is our cleanest claim. Everyone in this
  space measures contemporaneously or looks backward. We test whether the
  signal leads realized occupational unemployment by one to three months, and
  we set the kill condition first. Frank et al. stop in 2019, before ChatGPT.
  We work in the generative-AI period and ask whether the signal gets ahead of
  the realized data.
- It's open. Public, reproducible pipeline and dataset under MIT, built on the
  Barometer we already run.
- And if we can manage it, a real handle on augmentation versus substitution.
  The literature still treats that one as open.

## 1.3 What this paper is not

- Not a causal paper. We never say AI caused anyone's distress.
- Not a new exposure index. We combine ones that already exist.
- Not the first to join exposure to state-by-occupation unemployment. Frank et
  al. did that. We add the search signal and the lead test.
- Not policy, not UBI. Not our lane, same as section 6 of the brief.

## 1.4 The "so what"

Result comes back positive? Then we've got a public, monthly, sub-national early
warning for AI-driven labor stress, months ahead of the BLS. That's the win.

Result comes back null? Still a paper. A careful negative result that bounds how
much search behavior can tell us about displacement is worth publishing. Write
that down now. It's the thing that makes pre-registering safe.

Status: draft / reviewed with co-author / locked
