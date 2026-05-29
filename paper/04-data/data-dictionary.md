# Step 4b. Data Dictionary

One row per variable in the frozen dataset. The reviewers need it and the
replication package needs it. Fill it in as we build.

## Keys
| Field | Type | What it is | Example |
|---|---|---|---|
| `state_fips` | str | State FIPS code | "39" (Ohio) |
| `soc_code` | str | SOC occupation code | "43-0000" |
| `occ_cluster` | str | One of the six clusters, brief section 3.4 | "office_admin" |
| `period` | date | Month or quarter, reference period | "2026-03" |
| `vintage` | date | Release vintage, for outcomes | "2026-04-19" |

## Variables we build
| Field | Type | What it is | Source or formula |
|---|---|---|---|
| `exposure_score` | float | z-scored composite exposure | brief section 3.1 |
| `exposure_state` | float | employment-share-weighted state rollup | brief 3.1 formula |
| `search_raw` | float | raw Health Trends volume | Google Health Trends |
| `search_divergence` | float | divergence from trailing baseline | section 3.2 |
| `ai_layoff_intensity` | float | exposure-weighted layoffs over labor force | brief 3.3 formula |
| `high_exposure` | bool | above the pre-registered cutoff | pre-registration |

## Outcome variables
| Field | Type | What it is | Source |
|---|---|---|---|
| `unemp_occ` | float | realized occupational unemployment | BLS |
| `unemp_state` | float | LAUS state unemployment | BLS |

## Quality flags
| Field | Type | What it is |
|---|---|---|
| `cell_n` | int | employment count in the cell |
| `suppressed` | bool | true when `cell_n` is below N |
| `low_confidence` | bool | search volume below the floor |

## Freeze record
- Snapshot version: ___
- Date frozen: ___
- Git tag or DOI: ___
- Row count: ___
