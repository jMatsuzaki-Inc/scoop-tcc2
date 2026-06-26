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
# Login with Google (opens browser)
tcc2 login

# Login with an email one-time password (no browser; works over SSH/headless)
tcc2 login --mail

# Check login status
tcc2 status

# Start MCP server (for Claude Code, Cursor, etc.)
tcc2 mcp

# Logout
tcc2 logout
```

## Login methods

`tcc2` supports two ways to sign in. Both result in the same account.

- **Browser (Google):** `tcc2 login` opens your browser for Google sign-in.
- **Email one-time password (OTP):** `tcc2 login --mail` requires no browser — ideal for SSH / headless environments. Enter your email address, then the 6-digit code sent to your inbox:

```powershell
tcc2 login --mail
# Email: you@example.com
# A verification code has been sent to your email.
# Verification code: 123456
# Login successful: you@example.com
```

The code expires in 5 minutes. If you already signed in with Google before, using the same email address signs you into the same account.

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
- Authentication supports Google account (browser) and email one-time password (`tcc2 login --mail`). Apple login support is planned for a future release.
