# Text to Speech (`media.audio.tts`)

Generate speech audio from text or a supported voice reference.

- Users ask for it as: convert text into spoken audio; generate a voiceover; text to speech; voice generation; tts.
- Takes text, audio → returns audio. Runs asynchronously; expect a job to wait on.

## Variants and indicative prices

| Variant | Indicative price | When to use |
|---|---|---|
| MiniMax TTS (`minimax-tts`) | text: $0.002 per 40 characters (min $0.002); fallback: $0.006 | Use MiniMax TTS when it matches the requested quality, provider, or model preference. |
| VoxCPM (`voxcpm`) | text: $0.002 per 40 characters (min $0.002); fallback: $0.006 | Use VoxCPM when it matches the requested quality, provider, or model preference. |
| Seed Audio (`seed-audio`) | $1.20, settled by actual usage ($0.01 per second (max $1.20)) | Use Seed Audio when it matches the requested quality, provider, or model preference. |

Prices are indicative catalog values refreshed with each skill release. Before calling, Inspect the chosen variant: Inspect's input Schema and USD quote are authoritative.
