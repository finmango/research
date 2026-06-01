# Step 4. Data Assembly

Two-paper plan: shared foundation. The frozen dataset is Paper 1's contribution
and Paper 2's input. See ../README.md.

This is the bulk of the real work. Roughly phases 1 to 3 of the roadmap in the
brief. One frozen, documented dataset that the analysis reads from. That's the
target.

## The order it happens in

1. Build the exposure layer first. It's all public inputs and no outcome data,
   so there's no reason to wait. See the O\*NET, OEWS, and three-index rows in
   `sources.md`.
2. Stand up the search signal pull and the divergence normalization.
3. Build the WARN and JOLTS ingestion, then compute `ai_layoff_intensity`.
4. Only after the pre-registration is posted (step 3): pull the outcome series,
   the BLS occupational unemployment, and merge it in.
5. Freeze a versioned snapshot. Tag it in git. Record the version in
   `data-dictionary.md`. The analysis runs against the frozen file, never a live
   pipeline.

## How the folder should look once code lands

```
04-data/
  sources.md           # where everything comes from
  data-dictionary.md   # the schema
  raw/                 # untouched downloads, gitignored
  interim/             # cleaning steps
  processed/           # the frozen analysis tables
  snapshots/           # versioned, tagged freezes with checksums
```

## Done means

- [ ] Every row in `sources.md` is ingested, or blocked and noted as blocked.
- [ ] `data-dictionary.md` covers every field in `processed/`.
- [ ] One frozen snapshot, with a checksum and a git tag.
- [ ] Suppression rules applied, matching the pre-registration.
