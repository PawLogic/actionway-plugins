# Generate Video (`media.video.generate`)

Generate or transform a video from a prompt and optional media references.

- Users ask for it as: create a new video; animate an image; transform a reference video; video generation; text to video; image to video.
- Takes text, image, video, audio → returns video. Runs asynchronously; expect a job to wait on.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| Image Video 3 (`image-video-v3`) | default: $0.06 per second; 720p: $0.06 per second; 1080p: $0.12 per second | Use Image Video 3 when it matches the requested quality, provider, or model preference. |
| Motion Video (`motion-video`) | default: $0.10 per second | Use Motion Video when it matches the requested quality, provider, or model preference. |
| AI Video (`ai-video`) | default: $0.10 per second | Use AI Video for image- or keyframe-driven video with a duration or driving audio. Not for: Prompt-only text-to-video requests without a source image.. |
| AI Video Pro (`ai-video-pro`) | 720p: $0.14 per second; 1080p: $0.40 per second | Use AI Video Pro when it matches the requested quality, provider, or model preference. |
| AI Video Pro Multiframe (`ai-video-pro-multiframe`) | 720p: $0.14 per second; 1080p: $0.40 per second | Use AI Video Pro Multiframe when it matches the requested quality, provider, or model preference. |
| HappyHorse Image to Video (`happyhorse-i2v`) | default: $0.30 per second | Use HappyHorse Image to Video when it matches the requested quality, provider, or model preference. |
| HappyHorse Reference to Video (`happyhorse-r2v`) | default: $0.30 per second | Use HappyHorse Reference to Video when it matches the requested quality, provider, or model preference. |
| HappyHorse Video Edit (`happyhorse-video-edit`) | default: $0.30 per second | Use HappyHorse Video Edit when it matches the requested quality, provider, or model preference. |
| Seedance 1.5 (`seedance-1-5`) | 720p: $0.12 per second; 1080p: $0.24 per second | Use Seedance 1.5 when it matches the requested quality, provider, or model preference. |
| Seedance 2.5 (`seedance-2-5`) | 480p: $0.20 per second; 720p: $0.40 per second | Use Seedance 2.5 when it matches the requested quality, provider, or model preference. |
| Seedance 2.0 (`seedance-2-0`) | 480p: $0.14 per second; 720p: $0.30 per second; 1080p: $0.72 per second; 4k: $1.44 per second | Use Seedance 2.0 when it matches the requested quality, provider, or model preference. |
| Seedance 2.0 Fast (`seedance-2-0-fast`) | 480p: $0.11 per second; 720p: $0.24 per second | Use Seedance 2.0 Fast when it matches the requested quality, provider, or model preference. |
| Seedance 2.0 Mini (`seedance-2-0-mini`) | 480p: $0.07 per second; 720p: $0.15 per second | Use Seedance 2.0 Mini for low-cost prompt-only videos lasting 5 to 12 seconds. |
| MiniMax H3 (`minimax-h3`) | default: $0.30 per second; 768p: $0.16 per second; 2k: $0.30 per second | Use MiniMax H3 when it matches the requested quality, provider, or model preference. |
| Kling 3.0 (`kling-3`) | 720p: $0.20 per second; 1080p: $0.40 per second | Use Kling 3.0 when it matches the requested quality, provider, or model preference. |
| Kling O3 Reference to Video (`kling-o3-ref2v`) | 480p: $0.10 per second; 720p: $0.24 per second; 1080p: $0.60 per second | Use Kling O3 Reference to Video when it matches the requested quality, provider, or model preference. |
| Kling O3 Pro Reference to Video (`kling-o3-pro-ref2v`) | 480p: $0.13 per second; 720p: $0.26 per second; 1080p: $0.48 per second | Use Kling O3 Pro Reference to Video when it matches the requested quality, provider, or model preference. |
| Kling O3 Video to Video (`kling-o3-v2v`) | 480p: $0.10 per second; 720p: $0.20 per second; 1080p: $0.60 per second | Use Kling O3 Video to Video when it matches the requested quality, provider, or model preference. |
| Kling O3 Pro Video to Video (`kling-o3-pro-v2v`) | 480p: $0.13 per second; 720p: $0.26 per second; 1080p: $0.48 per second | Use Kling O3 Pro Video to Video when it matches the requested quality, provider, or model preference. |
| Grok Imagine 1.5 (`grok-imagine-1-5`) | 480p: $0.10 per second; 720p: $0.16 per second | Use Grok Imagine 1.5 when it matches the requested quality, provider, or model preference. |
| Gemini Omni Video (`gemini-omni-video`) | 720p: $0.10 per second; 1080p: $0.30 per second; 4k: $0.60 per second | Use Gemini Omni Video when it matches the requested quality, provider, or model preference. |
| LongCat Avatar 1.5 (`longcat-avatar-1-5`) | default: $0.20 per second | Use LongCat Avatar 1.5 when it matches the requested quality, provider, or model preference. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
