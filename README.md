# TaskChute Cloud 2 CLI Scoop Bucket

> **Note:** The MCP server requires a Pro plan.
> Upgrade your plan at the [Plan Settings](https://taskchute.cloud/user/plan) page.

[TaskChute Cloud 2](https://taskchute.cloud) CLI - MCP Server for AI agents.

## Install

```powershell
scoop bucket add tcc2 https://github.com/jMatsuzaki-Inc/scoop-tcc2
scoop install tcc2
```

## Usage

```powershell
# Login (opens browser for authentication)
tcc2 login

# Check login status
tcc2 status

# Start MCP server (for Claude Code, Cursor, etc.)
tcc2 mcp

# Logout
tcc2 logout
```

## Setting Up with Claude Code

First, log in to your TaskChute Cloud 2 account:

```powershell
tcc2 login
```

Then, register tcc2 as an MCP server in Claude Code using the `claude mcp add` command:

```powershell
claude mcp add taskchute -- tcc2 mcp
```

Once registered, Claude Code can interact with your TaskChute Cloud 2 tasks directly through the MCP protocol.

## Update

```powershell
scoop update tcc2
```

## Uninstall

```powershell
scoop uninstall tcc2
scoop bucket rm tcc2
```

## Limitations & Roadmap

- The MCP server is available exclusively on the Pro plan. You can subscribe from the [Plan Settings](https://taskchute.cloud/user/plan) page.
- Rate limiting may be introduced in the future to prevent excessive API calls caused by AI agents.
- Currently, only Google account authentication is supported. Apple login support is planned for a future release.
