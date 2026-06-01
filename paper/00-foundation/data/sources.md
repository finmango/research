# Step 4a. Data Sources

Every input, where it comes from, how often it updates, the license, and how to
get it. All of it public. That's on purpose, same as the brief (sections 3.1
and 6).

| Dataset | Use | Granularity | Cadence | Access | License | Status |
|---|---|---|---|---|---|---|
| O\*NET | Task to SOC mapping | Occupation | Annual | onetonline.org | Open | no |
| BLS OEWS | Employment shares by SOC and state | State by SOC | Annual, about a year late | bls.gov/oes | Public | no |
| Felten/Raj/Seamans AIOE | Exposure input | Occupation | Static | Published data | Cite | no |
| Eloundou et al. GPT exposure | Exposure input | Occupation | Static | arXiv:2303.10130 supp. | Cite | no |
| Brynjolfsson SML | Exposure input | Occupation | Static | Published | Cite | no |
| Google Health Trends | AI-distress search signal | State, weekly | Real-time | API, access TBD | Terms apply | no |
| BLS occupational unemployment | The outcome we validate against | Occupation, CPS | Monthly | bls.gov | Public | no |
| BLS LAUS | State unemployment | State | Monthly, about 3 weeks | bls.gov | Public | no |
| BLS JOLTS | Openings and turnover | Industry | Monthly | bls.gov/jlt | Public | no |
| WARN Act notices | Layoff events | State | Rolling | Per state, API/scrape/PDF | Public | no |

## The parts that can block us

- Google Health Trends. Confirm the access tier and the rate limits. This one
  gates the whole search signal, so sort it early. Write down exactly how we
  build the queries.
- WARN. There's no national feed. We build a per-state list. Note which states
  give an API, which need scraping, and which are stuck in PDFs.
- OEWS suppression. We inherit their cell-suppression rules. Record them so the
  paper matches.

## Nice to have, not core

- Anthropic Economic Index state-usage data. A cross-check, not an input.
- ILO WP 140 exposure index. Another exposure cross-check for section 5.
