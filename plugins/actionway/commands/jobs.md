---
description: Check the status of an Actionway job
---

Check the Actionway job the user is asking about: $ARGUMENTS

If the arguments contain a `job_ref` (UUID), call the `get_job` MCP tool with it. If no `job_ref` was given, look for one in the recent conversation before asking the user for it.

Report the job's current status. When it has completed, present the result — media URLs included — and stop polling. Polling never changes billing or vendor state, but do not re-submit the original call to "retry" a job.
