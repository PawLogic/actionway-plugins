# Generate Image (`media.image.generate`)

Generate or edit a still image from a prompt with optional reference images.

- Users ask for it as: create a new image; edit an image using references; image generation; text to image; image editing.
- Takes text, image → returns image. Runs asynchronously; expect a job to wait on.
- Not for: find an existing image on the web — use `web.image.search` instead.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| Banana Pro (`banana-pro`) | $0.30 | Use Banana Pro when it matches the requested quality, provider, or model preference. |
| Banana 2 (`banana-2`) | $0.20 | Use Banana 2 when it matches the requested quality, provider, or model preference. |
| Seedream (`seedream`) | $0.10 | Use Seedream when it matches the requested quality, provider, or model preference. |
| Seedream 5 Lite (`seedream-5-lte`) | $0.10 | Use Seedream 5 Lite when it matches the requested quality, provider, or model preference. |
| GPT Image 2 (`gpt-image-2`) | $0.15 | Use GPT Image 2 when it matches the requested quality, provider, or model preference. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
