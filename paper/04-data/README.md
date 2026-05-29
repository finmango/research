# Step 4 — Data Assembly

**Goal:** a single, versioned, documented dataset that the analysis reads from.
This is the bulk of the real labor (≈ brief roadmap Phases 1–3).

## Order of operations
1. Build the **exposure layer** (public inputs — do this first, no outcome
   data involved). See `sources.md` rows for O\*NET, OEWS, the three indices.
2. Stand up the **search signal** pull + divergence normalization.
3. Build **WARN + JOLTS** ingestion → `ai_layoff_intensity`.
4. **Only after pre-registration is posted (Step 3):** pull the **outcome**
   series (BLS occupational unemployment) and merge.
5. **Freeze** a versioned snapshot. Tag it in git; record version in
   `data-dictionary.md`. The analysis must run against the frozen file, not a
   live pipeline.

## Suggested layout (when code starts)
```
04-data/
  sources.md           # this folder: provenance
  data-dictionary.md   # this folder: schema
  raw/                 # (gitignored) untouched downloads
  interim/             # cleaning steps
  processed/           # the frozen analysis table(s)
  snapshots/           # versioned, tagged freezes + checksums
```

## Definition of done
- [ ] All `sources.md` rows ingested or access-blocked-and-noted
- [ ] `data-dictionary.md` complete for every field in `processed/`
- [ ] One frozen snapshot with checksum + git tag
- [ ] Suppression rules applied per pre-registration
