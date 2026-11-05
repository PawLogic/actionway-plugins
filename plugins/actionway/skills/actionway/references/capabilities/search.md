# Search (`web.search`)

Search the public web and return normalized result hits.

- Users ask for it as: find current information on the web; research sources; web search; internet search; google search.
- Takes text → returns structured-data, url. Runs synchronously.
- Not for: find visually similar images — use `web.image.search` instead.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| Automatic Web Search (`auto`) | $0.02 | Use Automatic Web Search when it matches the requested quality, provider, or model preference. |
| Baidu (`baidu`) | $0.02 | Use Baidu when it matches the requested quality, provider, or model preference. |
| Parallel (`parallel`) | $0.02 | Use Parallel when it matches the requested quality, provider, or model preference. |
| Google via Serper (`serper`) | $0.02 | Use Google via Serper when it matches the requested quality, provider, or model preference. |
| Tavily (`tavily`) | $0.02 | Use Tavily when it matches the requested quality, provider, or model preference. |
| Brave Search (`brave`) | $0.02 | Use Brave Search when it matches the requested quality, provider, or model preference. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
