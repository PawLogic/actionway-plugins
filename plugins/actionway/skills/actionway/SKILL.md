---
name: actionway
description: Generate videos, images, logos, music, voiceovers, and sound effects; transcribe audio, read text and tables out of images and PDFs, lip-sync avatars, transfer motion onto a character, cut a subject out of a photo, build a 3D model from photos, detect shots and analyze beats for editing; download videos from TikTok, Douyin, Instagram, YouTube, and Bilibili; run specialized search such as reverse-image, stock-media, business-contact, maps, places, restaurants, and local-business search; fetch and read web pages; look up stock quotes, tickers, and company financials; fetch live platform data (social stats across TikTok, Douyin, Instagram, Reddit, LinkedIn, Weibo and Xiaohongshu, weather, markets, public datasets). Use this skill whenever the user wants to create, edit, or download media; needs a specialized external capability that the host does not provide; explicitly asks for Actionway or a named Actionway provider; continues a pending job_ref or call_ref; or asks about Actionway invitations, balance, usage, or transactions. Do not use it for ordinary web search when the host has built-in web search; use the host search first, and never silently fall back to Actionway `web.search`.
metadata:
  version: "0.1.3"
---

# Actionway

Run every Actionway action through the connected Actionway MCP server. The `references/capabilities/` files in this Skill are generated from the server's Capability Registry and carry the capability catalog with variants and indicative prices — trust them for planning and quoting options. The runtime authority for Schema and the binding USD quote is always `tool_inspect`.

This surface has no local `actionway` CLI. Never shell out to `actionway`, and never tell the user a task is blocked on installing, authenticating, or updating a CLI — the MCP connection already carries the signed-in user's identity. If a tool call fails because the connection is not authorized, say so plainly and let the user authorize the server in their host.

Right after the user first connects, call `actionway_account_balance` once and tell them their balance in one line. When the balance is zero, follow that line with a direct reminder to top up before running paid tasks, giving this connection's Actionway app wallet path `/account/wallet?top_up=1&top_up_source=install` as a link; when the balance is merely low, or the user asks how to top up, offer the same link. Resolve that path against this connection's Actionway app base URL, never a hard-coded URL for another environment. Never hold up free work waiting for it.

## Decide when Actionway is needed

1. Watch for these signals in every request: the user wants a non-text artifact (video, image, audio, subtitles, a downloadable file); supplies media to transform; needs specialized live or external data that the host cannot supply; asks at batch scale; names a tool or model; explicitly asks for Actionway or a named Actionway provider; or continues a previous job. Any signal: continue below. None: do the task yourself.
2. For an ordinary public-web search, use the host's built-in web search when available and do not call Actionway `web.search`. Structured local-business, restaurant, place, address, map, and Google Maps lookups are Actionway map work: use `maps.geocode` to resolve an address or anchor when coordinates are missing, then `maps.places.search` for nearby places. Do not substitute `web.search` or a social-platform location search. If built-in search is unavailable or fails, explain that and ask before using Actionway web search after showing its current price; never switch silently. A direct request to use Actionway web search may use its automatic Parallel-first route, or an explicitly requested Baidu, Parallel, Serper, Tavily, or Brave variant, through the normal inspection and confirmation flow. This rule does not apply to free capability discovery (`tool_search`), maps/place search, reverse-image search, stock-media search, securities search, or social-person search. When the user explicitly requests a social platform's own location results, label them as platform keyword/location records and never claim a precise business or geospatial match unless the result proves one. Decompose the deliverable into parts and judge each part on its own. Text, code, and copy are yours. Mechanical media processing you can run locally (cutting, joining, format conversion, burning subtitles, watermarking via ffmpeg) is also yours — that list is exhaustive. Beat detection, shot detection, and transcription read what is inside the media, so they go through Actionway even though ffmpeg or a script could approximate them. A URL the user hands you is external data: fetch it through Actionway, never with a built-in fetch tool or curl. Generating new media, understanding media content, and specialized live external data unavailable from the host are not — those go through Actionway. A web page is code (yours) plus images (search for a tool); "edit this video" is local ffmpeg work plus Actionway analysis and any generated assets.
3. For each part you cannot do yourself, find it in the capability index below and open its `references/capabilities/` file. The file names the variants (models), what each is for, and indicative prices — enough to plan and quote options without any call.
4. Your first reply already presents the plan: name the capability, list 2–3 variant options with their indicative prices from the reference, each price carrying its pricing unit spelled out (for example "$0.03 per image", "$0.012 per second", or "from $0.10" for metered pricing); when the task's usage is already known (a duration, a count), quote each option as its total for this task with the unit price alongside (for example "$0.48 for this 8-second video ($0.06 per second)") — chosen to span the range (for example cheapest and highest-quality), not to steer — and ask for any missing materials — files and links alike — in that same reply, so the user confirms materials and plan in one round. Present options neutrally: state what each variant is for and what it costs, and let the user decide. Use public capability, platform, and model names; do not volunteer upstream provider names or internal tool refs unless the user explicitly asks for the provider/source or that detail is necessary to troubleshoot. Actionway provides the capabilities; it does not recommend one, preselect a default, or make the choice for the user. The one exception: when the user answers "whatever" or "you pick", take the best-quality variant and proceed through the normal quote confirmation. Missing materials are never a reason to postpone the plan. Never hunt for a mentioned file or link with shell or filesystem tools — if it is not already in the conversation, ask for it in that same reply.
5. Fall back to the free `tool_search` only when no reference file covers the part — especially the Live data long tail — or the reference leaves you unsure which capability fits. Write the query as a short normalized English intent naming the output and key constraints (for example "generate video from product photo, 30 seconds"), whatever language the user writes in. If search returns no match, retry once with different wording (for example "add watermark to video" → "overlay logo on video"); if it returns `clarification_required`, ask the user its bounded question. Say a part is not currently available only in a reply where you have already run that search and its retry — never from memory or from the references alone — and do not improvise a workaround through unrelated tools.

## Capability index

<!-- actionway:capability-index:begin — generated by capability-registry, do not edit by hand -->

**Generate (create from scratch)**

- [Generate Video](references/capabilities/generate-video.md) (`media.video.generate`) — Generate or transform a video from a prompt and optional media references.
- [Lip Sync](references/capabilities/lipsync.md) (`media.video.lipsync`) — Synchronize a face or avatar video with driving speech audio.
- [Motion Control](references/capabilities/motion-control.md) (`media.video.motion-control`) — Drive a character image with motion from a reference video.
- [Generate Image](references/capabilities/generate-image.md) (`media.image.generate`) — Generate or edit images and animated GIFs from a prompt with optional references, masks or annotations.
- [Generate Music](references/capabilities/generate-music.md) (`media.music.generate`) — Generate an original music track from a prompt and optional musical attributes.
- [Text to Speech](references/capabilities/generate-tts.md) (`media.audio.tts`) — Generate speech audio from text or a supported voice reference.

**Edit and analyze (work on supplied content)**

- [Judge Evidence](references/capabilities/judge.md) (`reasoning.judge`) — Evaluate supplied text with typed yes/no, choice or score questions; return probabilities without searching or taking actions.
- [Transcribe Audio](references/capabilities/transcribe.md) (`media.audio.transcribe`) — Transcribe speech audio into text with optional timestamps.
- [OCR Document](references/capabilities/ocr.md) (`document.ocr`) — Extract Markdown and document assets from an image or a PDF of up to 40 pages.
- [Detect Shots](references/capabilities/detect-shots.md) (`media.video.detect-shots`) — Analyze a video and identify shot boundaries.
- [Segment Image](references/capabilities/segment-image.md) (`media.image.segment`) — Create image masks from text, point, or box prompts.
- [Segment Image to RLE](references/capabilities/segment-image-rle.md) (`media.image.segment-rle`) — Create run-length encoded masks from text, point, or box prompts.
- [Image to 3D](references/capabilities/image-to-3d.md) (`media.model3d.from-image`) — Generate a 3D model from one reference image.
- [Multi-image to 3D](references/capabilities/images-to-3d.md) (`media.model3d.from-images`) — Generate a 3D model from one to four multi-view images.

**Fetch (bring things in from outside)**

- [Download Media](references/capabilities/download-media.md) (`media.download`) — Download and normalize media from a supported URL.
- [Search](references/capabilities/search.md) (`web.search`) — Search the public web and return normalized result hits.
- [People Search](references/capabilities/people-search.md) (`people.search`) — Search professionals by job title, company and supported filters; return normalized profile evidence for caller-side assessment.
- [Image Search](references/capabilities/image-search.md) (`web.image.search`) — Find visually similar or relevant existing images on the public web.
- [Fetch URL](references/capabilities/fetch.md) (`web.fetch`) — Fetch a supported URL as text, Markdown, or bounded raw content.

**Live data**

- [Search Securities](references/capabilities/search-securities.md) (`finance.security.search`) — Search stocks and other market securities by name or symbol.
- [Market Quote](references/capabilities/market-quote.md) (`finance.market.quote`) — Get the latest available market quote for one or more comma-separated symbols.
- [Company Income Statement](references/capabilities/income-statement.md) (`finance.company.income-statement`) — Get standardized annual or quarterly company income statements.
- [Geocode](references/capabilities/geocode.md) (`maps.geocode`) — Convert an address to coordinates or coordinates to a formatted address.
- [Search Places](references/capabilities/places-search.md) (`maps.places.search`) — Find nearby places with exact addresses, distance, opening status, ratings, and map links.
- [Weather Alerts](references/capabilities/weather-alerts.md) (`weather.alerts.list`) — List active U.S. weather alerts for a state, territory, or marine area.
- [Weather Alert](references/capabilities/weather-alert.md) (`weather.alert.get`) — Get the current details of one U.S. weather alert by its alert identifier.
- [Weather Alert Types](references/capabilities/weather-alert-types.md) (`weather.alert-types.list`) — List the event types used by the U.S. weather alert service.

**Live data long tail** — social platform stats, market data, public datasets and 1,200+ other endpoints are not enumerated here. They are Search-only: run one free capability search per part before saying anything is unavailable.

<!-- actionway:capability-index:end -->

## Choose the tool

- Route from the references first. Once the user picks a variant (or exactly one fits, or they already named a tool, model, or price tier), call `tool_inspect` on that one choice before `tool_call`. Inspect is the authority for the current input Schema, variants, effects, guidance, and Actionway USD price; if it disagrees with the reference, follow Inspect and tell the user the updated price before proceeding.
- When you had to fall back to `tool_search`, use its filters only when the task supplies real constraints, and inspect at most three of the supported candidates — include the cheapest and the highest-quality — then present those options neutrally and let the user choose before `tool_call` — never recommend one for them.
- `generate_image`, `edit_image`, and `generate_video` are pre-bound shortcuts for the most common media work. Prefer them when they fit; they run the same confirmation, billing, and Job path as `tool_call`. Everything else goes through `tool_search` → `tool_inspect` → `tool_call`.
- Web search is an Actionway capability, not a separate tool on this surface: reach it through `tool_search` like any other capability.
- When the signed-in user asks to generate, show, copy, or share their invitation, call `actionway_account_invitation` with the conversation language. Return the server-provided `code`, `url`, and `message`; do not invent reward amounts or rewrite promotion terms. The first request creates one permanent code and later requests return that same code.
- For other account questions use only the requested read tool: `actionway_account_balance` for the wallet, `actionway_account_usage`, or `actionway_account_transactions`.

## Call a capability

1. Build `arguments` that match the inspected Schema exactly. Use the inspected canonical `variant_id`, never a guessed provider/model alias.
2. Make one call at a time. Reuse one stable `idempotency_key` when retrying the same request.
3. Read the structured result. Preserve a failure's `code`, `message`, `hint`, and safe details rather than paraphrasing them away.
4. Treat server-projected pricing as authoritative. Show the current USD quote and effects whenever you present tool options, when the user asks about price, and when confirmation is required. Never calculate an internal credits-to-USD conversion or invent a price.
5. Handle call status exactly:
   - A priced quote alone never requires another approval prompt: make the call once and let Actionway check the wallet. On `confirmation_required`, present the server plan's capability/variant, effects, Usage label, and USD quote, then ask the user; `confirmation: strong` always requires its server-verifiable approval. On rejection, stop. On changed inputs, make a new call. On approval, call the same tool again with `resume_call_ref` set to the returned `call_ref` and no other argument.
   - `accepted`: keep the returned `job_ref` and poll it as described below.
   - `completed`: consume the returned result.
   - `confirmation: strong`: never treat chat text alone as approval; follow a server-verifiable approval instruction or report that execution cannot continue.
6. On `E_INSUFFICIENT_BALANCE`, stop the call. When the failure includes `top_up_url`, the user-facing response must render that exact field value as a Markdown link by substituting it into `[Top up Actionway balance](<top_up_url>)`; never leave it only in raw tool output, replace it with a terminal command, or synthesize a URL for another environment. Ask the user to retry the original task after the top-up is complete.

## Handle asynchronous jobs

1. Preserve the full UUID `job_ref` returned by submit.
2. When a call returns `accepted`, call `get_job` for that `job_ref` in the same Agent turn.
3. This surface has no blocking wait: `get_job` is a one-shot read. Re-call it at a widening interval while the job runs, and never spawn a background process or a shell `sleep`, `for`, or `while` polling loop.
4. If a job is still running after about ten minutes, tell the user once that processing continues and they may come back later with the same `job_ref`. Continue polling unless the user asks to stop.
5. Polling never changes billing or vendor state. Do not resubmit the original call merely because a job is still pending — keep using its original `job_ref`.

## Deliver artifacts

- When the host can write files, download terminal `assets` into an `outputs/` directory under the current task using stable, descriptive filenames, and present the downloaded local files to the user.
- When the host cannot write files, present the returned asset URLs directly.
- If downloading fails, preserve the terminal payload and `job_ref`; never resubmit generation to recover a file transfer.
