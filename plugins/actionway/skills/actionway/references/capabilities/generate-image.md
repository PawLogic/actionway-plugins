# Generate Image (`media.image.generate`)

Generate or edit images and animated GIFs from a prompt with optional references, masks or annotations.

- Users ask for it as: create a new image; edit an image using references; generate a looping GIF; edit a masked or annotated image; image generation; text to image; image editing; GIF generation; animated sticker; mask editing.
- Takes text, image → returns image. Runs asynchronously; expect a job to wait on.
- Not for: find an existing image on the web — use `web.image.search` instead.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| Banana Pro (`banana-pro`) | $0.30 | Use Banana Pro when it matches the requested quality, provider, or model preference. |
| Seedream (`seedream`) | $0.10 | Use Seedream when it matches the requested quality, provider, or model preference. |
| Seedream 5 Lite (`seedream-5-lte`) | $0.10 | Use Seedream 5 Lite when it matches the requested quality, provider, or model preference. |
| GPT Image 2 (`gpt-image-2`) | $0.15 | Use GPT Image 2 when it matches the requested quality, provider, or model preference. |
| BytePlus Seedream 5.5 (`seedream-5.5`) | $0.10 | Use BytePlus Seedream 5.5 when it matches the requested quality, provider, or model preference. |
| MiniMax H3 Image (`minimax-h3-image`) | From $0.038; varies by specification (Inspect for exact quote) | Generate one still image or edit up to 16 reference images with MiniMax H3 Image at 1K, 2K or 4K. |
| MiniMax H3 Image Highspeed (`minimax-h3-image-highspeed`) | From $0.06; varies by specification (Inspect for exact quote) | Generate one still image or edit up to 16 reference images with MiniMax H3 Image Highspeed at 1K, 2K or 4K. |
| GPT Image 2.6 flare (`gpt-image-2.6-flare`) | From $0.024; varies by specification (Inspect for exact quote) | Generate or edit one still image or animated GIF, with transparency, masks or annotation-guided still editing, and up to 16 references. Not for: SVG output is unavailable. GIF does not support transparency, masks or markup. Masks guide edits but do not guarantee pixel-exact preservation.. |
| GPT Image 2.6 sunburst (`gpt-image-2.6-sunburst`) | From $0.024; varies by specification (Inspect for exact quote) | Generate or edit one still image or animated GIF, with transparency, masks or annotation-guided still editing, and up to 16 references. Not for: SVG output is unavailable. GIF does not support transparency, masks or markup. Masks guide edits but do not guarantee pixel-exact preservation.. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
