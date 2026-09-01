---
description: Find the right Actionway capability for a task and start it
---

The user wants to accomplish this with Actionway: $ARGUMENTS

Use the Actionway MCP tools from this plugin's server connection: call `tool_search` with the user's intent, then `tool_inspect` on the chosen `tool_ref` before calling. For common media work, prefer the `generate_image`, `edit_image`, or `generate_video` shortcuts. The bundled Actionway skill is the authority for the full flow.

Do not shell out to an `actionway` CLI: this plugin ships no CLI, and a task is never blocked on installing or authenticating one.

Treat server-returned schemas and USD prices as authoritative; never invent a variant or a price. When a call returns `confirmation_required` and the user has just picked that option from the ones you presented at the same total price, that pick is their approval — resume with `resume_call_ref` right away; otherwise present the plan and quoted price and wait for the user's approval before resuming. When a call returns a `job_ref`, poll it with `get_job` instead of re-submitting.
