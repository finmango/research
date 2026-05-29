# Step 1. Lock the Claim

One sentence. Falsifiable. Everything after it answers to it. If a result
wouldn't change whether that sentence is true, it doesn't go in the paper.

## 1.1 The claim (locked)

> In the generative-AI period, a combined AI-exposure and household
> financial-stress search signal at month t leads realized occupational
> unemployment at month t+k, for k of 1 to 3 months, among high-exposure
> occupations across US states.

The falsifiable number behind it: in a panel regression of occupational
unemployment at t+k on the standardized signal at t, the sum of the
distributed-lead coefficients over k of 1, 2 and 3 is positive at the 5 percent
level. We report it next to the lead-lag cross-correlation by k and an
out-of-sample comparison against an autoregressive baseline.

The decisions, now locked. These flow straight into the pre-registration and we
don't move them later.

- Lead window. k of 1, 2 and 3 months. The primary test is the distributed-lead
  specification over all three at once, and we report each k. No picking the
  best k after the fact.
- Outcome series. The unemployment rate for each state, occupation cluster, and
  month, from CPS microdata (IPUMS-CPS), on a 3-month rolling basis to tame the
  sampling noise, with thin cells suppressed below the pre-registered floor.
  LAUS state unemployment and national unemployment by occupation cluster are
  the robustness brackets. CPS is the only public series that is monthly and
  occupational at once: OEWS is annual, LAUS is not occupational.
- High exposure. Top tercile of the composite exposure score (Felten, Eloundou,
  Brynjolfsson, z-scored and equal-weighted), employment-weighted across
  detailed occupations. The bottom tercile is the placebo comparison (H2).
- Headline statistic. The distributed-lead coefficient sum above, with
  state-by-cluster and month fixed effects and standard errors clustered by
  state and by occupation cluster.

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

Status: locked as drafted. Co-author sign-off pending.
