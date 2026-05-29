# Step 7. Reproducibility and the Replication Package

The goal: anyone can clone the repo and rebuild every number and every figure.
It's free credibility, some venues require it, and it's how we already work.
Open by default, MIT. Build this alongside steps 4 and 5, not after.

## How it should look

```
07-reproducibility/
  code/
    01_build_exposure.{py,R}     # exposure composite and state rollup
    02_pull_search.{py,R}        # Health Trends and the divergence normalization
    03_build_layoffs.{py,R}      # WARN and JOLTS into intensity
    04_merge_freeze.{py,R}       # join and the frozen snapshot
    05_analysis.{py,R}           # lead-lag and robustness, step 5
    06_figures.{py,R}            # rebuilds every figure and table
  env/                           # requirements.txt, renv.lock, or Dockerfile
  Makefile                       # make all rebuilds the whole paper
  README.md                      # exactly how to run it
```

## The checklist

- [ ] One command, `make all`, rebuilds every figure and table from the frozen
      snapshot.
- [ ] The environment is pinned. A lockfile or Docker.
- [ ] Seeds are fixed for anything random.
- [ ] Data is either bundled, if the license allows, or fetched by script.
- [ ] The README says how long it runs and on what.
- [ ] LICENSE is MIT. Add a CITATION.cff.
- [ ] Archived with a DOI on Zenodo when we submit.

## One thing to watch on licensing

The government inputs are public, so we can bundle them. Google Health Trends
terms might not let us redistribute the raw pulls. If that's the case, we ship
the query code plus the cached aggregates, and document exactly how to rebuild
them from scratch.
