# People Search (`people.search`)

Search professionals by job title, company and supported filters; return normalized profile evidence for caller-side assessment.

- Users ask for it as: find people at a company by title; find professionals by role and location; 寻找公司负责人和行业专家; people search; find professionals; 找人; 找公司负责人.
- Takes text → returns structured-data, url. Runs synchronously.
- Not for: general web research — use `web.search` instead.
- Not for: find or verify email addresses, automatic outreach, or sensitive personal profiling.

Choose a provider and supply structured filters. Return evidence without model assessment. Reserve by limit; settle by the returned deduplicated count. Empty results cost zero.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| Icypeas (`icypeas`) | $0.002 per item, settled by actual usage ($0.002 per item) | Search a batch of professionals with location, skill or keyword filters and pagination. |
| Findymail (`findymail`) | $0.04 per item, settled by actual usage ($0.04 per item) | Find up to three people at a known company by job title. Not for: Location, skill, keyword or exclusion filters and pagination.. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
