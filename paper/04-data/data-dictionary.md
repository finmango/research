# Step 4b — Data Dictionary

One row per variable in the frozen analysis dataset. Reviewers and the
replication package both depend on this. Fill as the dataset is built.

## Keys / dimensions
| Field | Type | Description | Example |
|-------|------|-------------|---------|
| `state_fips` | str | State FIPS code | "39" (Ohio) |
| `soc_code` | str | SOC occupation code | "43-0000" |
| `occ_cluster` | str | One of the 6 clusters (brief §3.4) | "office_admin" |
| `period` | date | Month/quarter (reference period) | "2026-03" |
| `vintage` | date | Data release vintage (for outcomes) | "2026-04-19" |

## Constructed variables
| Field | Type | Description | Source / formula |
|-------|------|-------------|------------------|
| `exposure_score` | float | z-scored composite AI-exposure | brief §3.1 |
| `exposure_state` | float | employment-share-weighted state rollup | brief §3.1 formula |
| `search_raw` | float | raw Health Trends volume | Google Health Trends |
| `search_divergence` | float | divergence from trailing baseline | §3.2 normalization |
| `ai_layoff_intensity` | float | exposure-weighted layoffs / labor force | brief §3.3 formula |
| `high_exposure` | bool | above pre-registered cutoff | §3 preregistration |

## Outcome variables (validation)
| Field | Type | Description | Source |
|-------|------|-------------|--------|
| `unemp_occ` | float | realized occupational unemployment rate | BLS |
| `unemp_state` | float | LAUS state unemployment | BLS |

## Suppression / quality flags
| Field | Type | Description |
|-------|------|-------------|
| `cell_n` | int | employment count in cell |
| `suppressed` | bool | true if `cell_n` < N (pre-registered) |
| `low_confidence` | bool | search volume below floor |

## Freeze metadata
- Snapshot version: ____
- Date frozen: ____
- Git tag / DOI: ____
- Row count: ____
