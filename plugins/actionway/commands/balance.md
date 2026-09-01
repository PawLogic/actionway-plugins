---
description: Show the signed-in user's Actionway balance
---

Read the user's current Actionway wallet balance and report it plainly.

Use the `actionway_account_balance` MCP tool from this plugin's server connection. Report the available amount, any held amount, and the update time. Read-only: do not start any call, and do not accept a user, workspace, or wallet override — the tool always answers for the signed-in account.
