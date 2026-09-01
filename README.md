# Actionway plugins

Public marketplace distribution for the Actionway plugin on Codex and Claude Code. Both hosts install the same Remote MCP connection and MCP-native Actionway Skill; Claude Code additionally loads the bundled slash commands.

## Install on Codex

```bash
codex plugin marketplace add PawLogic/actionway-plugins
codex plugin add actionway@pawlogic
```

Refresh the marketplace after a new release:

```bash
codex plugin marketplace upgrade pawlogic
```

## Install on Claude Code

```bash
claude plugin marketplace add PawLogic/actionway-plugins
claude plugin install actionway@pawlogic
```

Update an existing installation:

```bash
claude plugin marketplace update pawlogic
claude plugin update actionway@pawlogic
```

Complete Actionway OAuth when the host asks you to connect the `actionway` MCP server.

## Versioning

Releases follow Semantic Versioning and are tagged as `vMAJOR.MINOR.PATCH`. The selector `actionway@pawlogic` means “plugin `actionway` from marketplace `pawlogic`”; the text after `@` is a publisher marketplace name, not a version or npm dist-tag.

## What is included

- Remote MCP server: `https://mcp.actionway.ai/mcp`
- Actionway MCP-native Skill and capability references
- Claude Code commands: `/actionway:start`, `/actionway:balance`, `/actionway:jobs`
- Codex install-surface metadata and Actionway artwork

Documentation: [actionway.ai/get-started](https://actionway.ai/get-started)

This public repository contains generated distribution artifacts. The canonical source is maintained by PawLogic.
