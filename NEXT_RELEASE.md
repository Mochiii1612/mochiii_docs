# Next release: changes after 1.5.0

Private working file. It is not part of the published site (see `.mintignore`).
The published pages describe v1.5.0 (commit 6cc75c3) only. Everything below
landed in `Rav-2007/codeterminal-core` after that tag, found with
`git log v1.5.0..origin/main` (43 commits, last checked 2026-11-03). Nothing
here may appear in the docs as current behaviour until a release ships it.

Note: this repository is public, so this file is readable on GitHub even though
the site does not publish it.

## User-visible changes to document when released

| Change | Commits / PR | Pages it will affect |
|---|---|---|
| A `/mcp` panel in the terminal that takes a server's JSON pasted straight in; the daemon reads pasted JSON strictly and previews it | 8afcce4, 56d18ce (#87) | MCP: adding a server |
| A server's keys are asked for when it is added | 6b0a080 (#83) | MCP: adding a server, where keys are stored |
| Missing-key message says to set the key, not to fix the command | 741fb97 (#84) | Troubleshooting |
| Marketplace cards say when a server needs uv or Docker | cf4f869 (#85) | MCP: verified servers |
| Marketplace cards show a server's whole tool count, and that the rest are reached with `find_tools` | 4c56d88 (#75) | MCP: the tool limit |
| An icon slug on a catalog entry | 1b03f82 (#73) | none (catalog internals) |
| The tool-menu cap stays 24; wording about what it leaves added servers | 8eea225 (#76) | MCP: the tool limit |
| A read-only MCP tool is no longer labelled "marked destructive" in the approval prompt | 6617e5f (#78) | Using Mochiii: approvals |
| An MCP lookup that declares `openWorldHint` counts as having checked, for grounding | 1ba138f, 65d529d (#77) | Using Mochiii (answers about the web) |
| Installer 1.5.1: ends on the line the terminal needs, and does not stop on a file it cannot change | 73ba41e, 3369131 (#72) | Getting started: installers |
| `command not found` right after installing: run the line the installer printed | 23b48b2 | Troubleshooting |
| Version 1.5.1 | 2abdd59 | Releases |
| Privacy wording reworded, managed-proxy overviews archived, licence changed to proprietary | daaeb1a (#86) | Releases and licence |

## Not user-visible (CI, tests, internal docs)

fa929ae, 9b86210, 28a9b8d (design notes); 5029d94, 540d28c (#79, #81 CI);
96924f7 (#82 test); 7e143b2 (#74 test); 9bd810d (#80 comment); 41b76b7 (#88 CI
retry).

## Things to settle before the Releases and licence page

- At v1.5.0 the `LICENSE` file, the README and the npm package metadata
  (`mochiii@1.5.0`) all say Apache-2.0. `main` changed that to proprietary in
  #86. The 1.5.0 docs say nothing about the licence until this is decided.
