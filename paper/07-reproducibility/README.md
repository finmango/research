# Step 7 — Reproducibility / Replication Package

**Goal:** anyone can clone the repo and regenerate every number and figure.
Free credibility, required by some venues, and on-brand for FinMango's
open-by-default posture (MIT). Build this *alongside* Steps 4–5, not after.

## Target layout
```
07-reproducibility/
  code/
    01_build_exposure.{py,R}     # exposure composite + state rollup
    02_pull_search.{py,R}        # Health Trends + divergence normalization
    03_build_layoffs.{py,R}      # WARN + JOLTS → intensity
    04_merge_freeze.{py,R}       # join + frozen snapshot
    05_analysis.{py,R}           # lead-lag + robustness (Step 5)
    06_figures.{py,R}            # regenerates every figure/table
  env/                           # requirements.txt / renv.lock / Dockerfile
  Makefile                       # `make all` reproduces the paper end-to-end
  README.md                      # exact run instructions
```

## Checklist
- [ ] One command (`make all`) reproduces all figures/tables from the frozen snapshot
- [ ] Pinned environment (lockfile or Docker)
- [ ] Seeds fixed for any stochastic step
- [ ] Data either bundled (if license allows) or fetchable by script
- [ ] README states runtime + hardware
- [ ] LICENSE = MIT; CITATION.cff added
- [ ] Archived with a DOI (Zenodo) at submission time

## Note on data licensing
Government inputs are public and bundleable. **Google Health Trends terms may
restrict redistribution** — if so, ship the *query code* + cached aggregates
rather than raw pulls, and document exactly how to regenerate.
