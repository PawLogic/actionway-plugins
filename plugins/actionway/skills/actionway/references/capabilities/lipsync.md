# Lip Sync (`media.video.lipsync`)

Synchronize a face or avatar video with driving speech audio.

- Users ask for it as: make a portrait speak in sync with audio; lip sync; talking avatar.
- Takes image, audio, text → returns video. Runs asynchronously; expect a job to wait on.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| MiniMax H3 (`minimax-h3`) | default: $0.30 per second; 2k: $0.30 per second | Use MiniMax H3 when it matches the requested quality, provider, or model preference. |
| LongCat Avatar (`longcat-avatar`) | default: $0.20 per second | Use LongCat Avatar when it matches the requested quality, provider, or model preference. |
| AI Video Pro (`ai-video-pro`) | 720p: $0.14 per second; 1080p: $0.40 per second | Use AI Video Pro when it matches the requested quality, provider, or model preference. |
| AI Video Pro Multiframe (`ai-video-pro-multiframe`) | 720p: $0.14 per second; 1080p: $0.40 per second | Use AI Video Pro Multiframe when it matches the requested quality, provider, or model preference. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
