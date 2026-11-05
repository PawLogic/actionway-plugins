# Judge Evidence (`reasoning.judge`)

Evaluate supplied text with typed yes/no, choice or score questions; return probabilities without searching or taking actions.

- Users ask for it as: judge whether supplied evidence supports a criterion; classify supplied text into specified options; score a candidate against descriptive levels; 用 Jev 判断候选人是否符合条件; Jev; judge evidence; classify text; 语义判断; 证据评分.
- Takes text → returns structured-data. Runs synchronously.
- Not for: find people or retrieve missing profile evidence — use `people.search` instead.
- Not for: general chat, text generation, arithmetic, or multi-step reasoning.

Ask one to five independent questions about the same text. Boolean answers report probability_true, not a thresholded verdict. Choice returns one option; score uses the zero-based positions of the supplied levels.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| Jev (`jev`) | $0.002 | Use Jev when it matches the requested quality, provider, or model preference. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
