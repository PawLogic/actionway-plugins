# Image to 3D (`media.model3d.from-image`)

Generate a 3D model from one reference image.

- Users ask for it as: turn an image into a 3D model; generate 3d from image; meshy; tripo.
- Takes image → returns document, url. Runs asynchronously; expect a job to wait on.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| Meshy V7 (`meshy-v7`) | untextured: $0.968; untextured-rig: $1.21; untextured-rig-animation: $1.356; textured: $1.452; textured-rig: $1.694; textured-rig-animation: $1.84; ultra: $1.694; ultra-rig: $1.936; ultra-rig-animation: $2.082 | Use Meshy V7 when it matches the requested quality, provider, or model preference. |
| Tripo H3.1 (`tripo-h3-1`) | none-standard-triangle: $0.22; none-standard-quad: $0.276; none-detailed-triangle: $0.44; none-detailed-quad: $0.496; standard-standard-triangle: $0.33; standard-standard-quad: $0.386; standard-detailed-triangle: $0.55; standard-detailed-quad: $0.606; detailed-standard-triangle: $0.44; detailed-standard-quad: $0.496; detailed-detailed-triangle: $0.66; detailed-detailed-quad: $0.716 | Use Tripo H3.1 when it matches the requested quality, provider, or model preference. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
