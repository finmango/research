# Step 4a — Data Sources

Every input, where it comes from, its cadence, license, and access notes.
All public — that's a deliberate design choice (brief §3.1, §6).

| Dataset | Use | Granularity | Cadence | Access | License | Status |
|---------|-----|-------------|---------|--------|---------|--------|
| O\*NET | Task→SOC mapping | Occupation | Annual | onetonline.org (download) | Open | ☐ |
| BLS OEWS | Employment shares by SOC × state | State × SOC | Annual (~1yr lag) | bls.gov/oes | Public | ☐ |
| Felten/Raj/Seamans AIOE | Exposure input | Occupation | Static | Published data | Cite | ☐ |
| Eloundou et al. GPT exposure | Exposure input | Occupation | Static | arXiv:2303.10130 supp. | Cite | ☐ |
| Brynjolfsson SML | Exposure input | Occupation | Static | Published | Cite | ☐ |
| Google Health Trends | AI-distress search signal | State, weekly | Real-time | API (access TBD) | Terms apply | ☐ |
| BLS occupational unemployment | **Outcome (validation)** | Occupation/CPS | Monthly | bls.gov | Public | ☐ |
| BLS LAUS | State unemployment | State | Monthly (~3wk) | bls.gov | Public | ☐ |
| BLS JOLTS | Openings/turnover | Industry | Monthly | bls.gov/jlt | Public | ☐ |
| WARN Act notices | Layoff events | State | Rolling | Per-state (API/scrape/PDF) | Public | ☐ |

## Access notes / blockers
- **Google Health Trends** — confirm access tier and rate limits; this gates
  the search signal. Document the exact query construction.
- **WARN** — no national feed; build a per-state ingestion list. Note which
  states are API vs. scrape vs. PDF.
- **OEWS suppression** — inherit their cell-suppression rules; record them.

## Optional / "nice to have"
- Anthropic Economic Index state-usage data — cross-check, not core input.
- ILO WP 140 exposure index — alternative exposure cross-check (§5).
