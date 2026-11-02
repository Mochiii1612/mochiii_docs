# Proposed sitemap

Describes Mochiii **1.5.0** (tag v1.5.0, commit 6cc75c3, and the 1.5.0 npm packages).
Pages marked **written** are in this first slice. The rest are proposals.

Paths are relative to `Rav-2007/codeterminal-core` at v1.5.0. The structure is
Cline-style in shape only: a hub, task-based sections, one job per page.

Changes from the requested outline, where the 1.5.0 source says a topic does not
exist as named:

- **"check mode" does not exist.** The modes are `plan` (terminal `/plan`, and the
  VS Code `plan` mode, `clients/vscode/package.json:109-122`) and, in VS Code,
  `auto` and `manual`. `check` appears only as `/spec check` (`clients/tui/slash.go:97`).
  The page is "Plan mode and specs".
- **"The verified servers" is not in the 1.5.0 source.** The list is served live by
  the website (`DEFAULT_CATALOG_URL`, `clients/vscode/src/mcpCatalog.ts:26`) and
  is the website repo's data, so it can change without a release. That page needs
  the live catalog read when it is written, and a date on it.
- **The terminal app has no marketplace.** The Marketplace is a VS Code feature
  at 1.5.0 (`clients/vscode/src/mcpMarketplace.ts`). The MCP pages say which client
  each step is for.

## Introduction

| Page | Purpose | Status | Source files to check |
|---|---|---|---|
| `index` Introduction | What Mochiii is, what you need, where to start | **written** | `npm/build.js`, `clients/tui/firstrun.go`, `clients/tui/localmodels.go` |

## Getting started

| Page | Purpose | Status | Source files to check |
|---|---|---|---|
| `getting-started/install` Install with npm | Install, start, update, remove, by npm | **written** | `npm/build.js`, `npm/mochiii/*`, `clients/tui/main.go`, `clients/tui/firstrun.go` |
| `getting-started/install-script` Install with the curl and PowerShell installers | Install without Node | proposed | `install/install.sh`, `install/install.ps1`, `docs/REFERENCE.md` (Install section, as a lead only) |
| `getting-started/first-run` First run | What happens the first time in a folder: model download, index offer | proposed | `clients/tui/firstrun.go`, `clients/tui/launch.go`, `daemon/embedderstamp.go` |
| `getting-started/connect-a-model` Connect a model | Your own key, or a local model server | proposed | `clients/tui/connect.go`, `clients/tui/connectchosen.go`, `clients/tui/localmodels.go`, `models.json` |
| `getting-started/first-task` Your first task | Ask a question, review an edit | proposed | `clients/tui/chat.go`, `clients/tui/approvalview.go`, `daemon/editapply` |

## Using Mochiii

| Page | Purpose | Status | Source files to check |
|---|---|---|---|
| `using/terminal` The terminal app and its commands | The chat screen, `/` commands, keys | proposed | `clients/tui/slash.go`, `clients/tui/chat.go`, `clients/tui/slashpopup.go` |
| `using/vscode` VS Code | Install, open the chat, what differs from the terminal | proposed | `clients/vscode/package.json`, `clients/vscode/src/extension.ts`, `clients/vscode/README.md` |
| `using/plan-and-spec` Plan mode and specs | `/plan`, and `/spec`, `/spec build`, `/spec check` | proposed | `clients/tui/slash.go`, `daemon/spec*.go`, `docs/SPEC_WORKFLOW.md` (lead only) |
| `using/approvals` Approvals and "marked destructive" | What you are asked, what the labels in the prompt mean | proposed | `clients/tui/chat.go` (approval risks, around line 2800), `clients/tui/approvalview.go`, `daemon/*classif*`, `models.agent.json` |
| `using/sessions-and-memory` Saved chats and memory | `/save`, `/resume`, `/history`, `/remember`, `/rules`, `/forget` | proposed | `clients/tui/slash.go`, `clients/tui/history.go`, `clients/tui/rules.go`, `daemon/chatarchive.go` |

## MCP

| Page | Purpose | Status | Source files to check |
|---|---|---|---|
| `mcp/what-is-mcp` What MCP is | One paragraph, and what Mochiii does with it | proposed | `daemon/mcpconfig.go`, `daemon/mcp/registry.go` |
| `mcp/verified-servers` The verified servers | Each server and what it needs | proposed, needs the live catalog | website repo `mcp/` and `scripts/mcp/`, `clients/vscode/src/mcpCatalog.ts` |
| `mcp/add-a-server` Add an MCP server | Add, key, check, remove, from the terminal | **written** | `clients/tui/mcpserver.go`, `daemon/mcp_handler.go`, `daemon/mcpenv.go`, `daemon/mcpsecrets.go`, `daemon/mcpuser.go`, `daemon/mcpstartdir.go` |
| `mcp/keys` Where keys are stored | `mcp-secrets.json`, `/mcp-server key`, VS Code's key command | proposed | `daemon/mcpsecrets.go`, `daemon/mcpenv.go`, `clients/vscode/src/mcpSecrets.ts` |
| `mcp/tool-limit` The 24-tool menu limit | What the cap is, what is left out, `find_tools` | proposed | `daemon/mcpconfig.go` (around line 580), `daemon/toolsearch.go`, `daemon/mcp/registry.go`, `daemon/mcp/relevance.go` |
| `mcp/remote-servers` Remote servers | `--transport http`, headers, sign-in | proposed | `clients/tui/mcpserver.go`, `daemon/mcpremote.go`, `daemon/mcpoauth.go` |

## Reference

| Page | Purpose | Status | Source files to check |
|---|---|---|---|
| `reference/settings` Settings | VS Code settings and environment variables | proposed | `clients/vscode/package.json`, `daemon/mcpconfig.go`, `models.json` |
| `reference/commands` Commands | Every slash command and command-line flag | proposed | `clients/tui/slash.go`, `clients/tui/main.go`, `daemon/main.go` |
| `reference/files` File locations | Where Mochiii keeps things | proposed | `daemon/mcpuser.go`, `daemon/mcpsecrets.go`, `clients/tui/firstrun.go`, credentials code (to find) |

## Troubleshooting

| Page | Purpose | Status | Source files to check |
|---|---|---|---|
| `troubleshooting/install` Install problems | `command not found`, missing platform package, no code search | proposed | `npm/mochiii/platform.js`, `daemon/programrole.go`, `install/install.sh` |
| `troubleshooting/mcp` MCP problems | A server did not start, a key is missing | proposed | `daemon/mcpstatus.go`, `daemon/mcp_handler.go`, `daemon/mcpenv.go` |
| `troubleshooting/connection` Connection and key problems | A refused key, the service not answering | proposed | `clients/tui/connect.go`, `clients/tui/daemonconn.go` |

## Releases and licence

| Page | Purpose | Status | Source files to check |
|---|---|---|---|
| `releases` Releases | What changed in each version | proposed | `docs/RELEASE_NOTES.md`, git tags |
| `licence` Licence | One line | **blocked** | At v1.5.0 `LICENSE`, `README.md` and the npm metadata all say Apache-2.0, not proprietary. See the PR description. |
