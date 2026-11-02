# Claims checked against v1.5.0

Source paths are in `Rav-2007/codeterminal-core` at tag v1.5.0 (commit 6cc75c3),
as line numbers in that tag's files.

**How "verified" was done.** Verified means the claim was read in the v1.5.0
source. Where noted, it was also run: `npm install -g mochiii@1.5.0` into an
empty prefix, then `mochiii --version` and `mochiii --stop`. **Nothing on the
MCP page was run**: no daemon was started and no server was added, so those
claims are source-read only.

## Could not verify, or only partly

| Page | Claim | Source | Status |
|---|---|---|---|
| install | `npm install -g mochiii@latest` updates | none in the code; ordinary npm behaviour. Stated in `docs/REFERENCE.md:34` | could not verify in source |
| install | Removing: `mochiii --stop` in each folder, then `npm uninstall -g mochiii` | `clients/tui/main.go:41` for `--stop`; the uninstall order is from `docs/REFERENCE.md:33-36`. REFERENCE also says npm stops no service; that part is **left out** of the page | partly verified |
| mcp/add-a-server | A project's `.mcp.json` can only propose a server, which runs only after `/mcp-server approve` | `daemon/mcpuser.go:38-39` (comment), `clients/tui/mcpserver.go:350-357` (client side). `daemon/mcpproject.go` was not read in full | partly verified |
| mcp/add-a-server | Use a full path, `~` not used in the example | the client does no shell expansion (`clients/tui/mcpserver.go:101-103`). No `~` expansion was found in `daemon/mcpexpand.go`, but not every daemon path was searched. `docs/REFERENCE.md:1101` and the README use `~/notes` in an example | partly verified |
| index | The VS Code extension exists | `clients/vscode/package.json:2-6` (name `mochiii-vscode`, version 1.5.0). The Marketplace's published version was **not** checked | verified for the source, not for the Marketplace |

## Verified

| Page | Claim | Source (v1.5.0) |
|---|---|---|
| index | Mochiii is a terminal coding assistant | npm description, `npm/build.js:196`; registry `mochiii@1.5.0` |
| index | Needs a provider API key, or a model server on your computer | `clients/tui/connect.go:75`; `clients/tui/localmodels.go:21` |
| index | Works on the folder it starts in; a note for the home folder | `clients/tui/firstrun.go:50-82` |
| index | First run asks whether to build a search index; it runs on this computer | `clients/tui/firstrun.go:123-125` |
| index | The index is in `<project>/.mochiii/index` | `clients/tui/firstrun.go:34,38` |
| install | `npm install -g mochiii` | `npm/build.js:5,108`; ran it: `added 2 packages` |
| install | Node 18 or later | `npm/build.js:203`; registry `engines` of `mochiii@1.5.0` |
| install | A platform package matching the computer is installed with it | `npm/build.js:202`; `npm/mochiii/platform.js:16-31` |
| install | Linux x64 and ARM64; macOS Apple Silicon; Windows x64 | `npm/mochiii/platform.js:16`; registry `cpu` of `@mochiii/win32-x64@1.5.0` |
| install | Windows on ARM runs the x64 build | `npm/mochiii/platform.js:5,24`; registry `cpu = [x64, arm64]` |
| install | Intel Macs are not supported | `npm/mochiii/platform.js:21-22` |
| install | The musl Linux build has no code search | `npm/mochiii/platform.js:7-9`; `daemon/programrole.go:104` |
| install | Code search needs glibc on regular Linux | `install/install.sh:135-144`. The page says "needs glibc" and gives no version |
| install | `mochiii --version` prints the version | `clients/tui/main.go:38,44-46`; ran it: `mochiii 1.5.0` |
| install | Starting `mochiii` in a folder opens the chat | `clients/tui/main.go:53-55` |
| install | Offer to download the model, once per computer, and index the folder | `clients/tui/firstrun.go:123-125,193` |
| install | `[Y/n/never]`: Enter or Y builds; n asks next time; never is remembered per folder | `clients/tui/firstrun.go:30,125-135` |
| install | `--index`, `--no-index`, `MOCHIII_NO_INDEX=1` | `clients/tui/main.go:39-40,48` |
| install | A question before a model is set up asks you to paste a provider API key | `clients/tui/connect.go:75` |
| install | A background service runs per project folder; `--stop` stops it | `clients/tui/main.go:41`; `clients/tui/launch.go:57-74`; ran `--stop`: "no Mochiii background service is running for this folder" |
| install | "package for this computer is not installed" message and the fix | `npm/mochiii/platform.js:71-72` |
| mcp/add-a-server | `/mcp-server add <name> <command> [args]` | `clients/tui/mcpserver.go:49-50,62,164-246` |
| mcp/add-a-server | Line split into words, quotes keep a path together, no shell | `clients/tui/mcpserver.go:100-138` |
| mcp/add-a-server | Nothing stored until the server's name is typed; anything else or Esc cancels | `clients/tui/mcpserver.go:26-30,504-510,522-533` |
| mcp/add-a-server | The warning shows the command, full privileges, where it starts, and "only add a server whose program you trust" | `daemon/mcp_handler.go:263-285` |
| mcp/add-a-server | Started once to list its tools; available from the next question; each tool asks first | `clients/tui/mcpserver.go:516`; `daemon/mcp_handler.go:583-594` |
| mcp/add-a-server | `--env NAME` takes a name; `NAME=value` and `NAME=value command` are refused | `clients/tui/mcpserver.go:158-160,183-185,241-243` |
| mcp/add-a-server | `/mcp-server key <name> <VARIABLE>` asks for the value hidden; Esc cancels | `clients/tui/mcpserver.go:377-391` |
| mcp/add-a-server | The variable must be one the server was added with | `daemon/mcpenv.go:230-238` |
| mcp/add-a-server | A stored value is used first; else the daemon's environment | `daemon/mcpenv.go:150-165` (`mcpEnvValueFor`; text at 152 puts the daemon environment after the stored values) |
| mcp/add-a-server | Export it, or put it in `.env`, before starting Mochiii | `clients/tui/mcpserver.go:159-160` |
| mcp/add-a-server | list, check (`--timeout` 1 to 120), get, disable, enable, remove | `clients/tui/mcpserver.go:49-61,293-334` |
| mcp/add-a-server | At most 24 tools at a time | `daemon/mcpconfig.go:637` |
| mcp/add-a-server | Mochiii's own tools come first; each question keeps the best-fitting rest | `daemon/mcp/registry.go:285-286`; `daemon/toolsearch.go:23-25` |
| mcp/add-a-server | The model can look up more with `find_tools` | `daemon/toolsearch.go:42` |
| mcp/add-a-server | Add tells you how many tools are not on the default list | `daemon/mcp_handler.go:594-597` |
| mcp/add-a-server | Servers are in `~/.mochiii/mcp-servers.json` | `daemon/mcpuser.go:47-48,117` |
| mcp/add-a-server | Keys are in `~/.mochiii/mcp-secrets.json`, readable only by you | `clients/tui/mcpserver.go:390`; `daemon/mcpsecrets.go:16,42` |
| mcp/add-a-server | Not kept in the project | `daemon/mcpuser.go:22-39` |
| mcp/add-a-server | A server starts in a private folder of its own; `--in-project` starts it in the project | `daemon/mcpstartdir.go:31`; `clients/tui/mcpserver.go:65,175-178` |

## Left out on purpose

- Privacy, retention and "nothing is uploaded" statements. The v1.5.0 README has
  them, and #86 later reworded them. None is on any page.
- The licence. See the PR description.
- The VS Code extension's version on the Marketplace.
