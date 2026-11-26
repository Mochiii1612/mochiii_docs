# Sitemap and sources

Every page, and the files its facts come from. Paths are in `Rav-2007/codeterminal-core`
at main `26ef54d` (terminal app 1.6.1, VS Code extension 1.0.1). "Run" means the fact
was also seen in a real run: terminal app 1.6.1 from npm and the extension's main-branch
build in VS Code 1.144, both with Qwen2.5-7B-Instruct on llama.cpp on the author's
computer, no key.

Abbreviations: `R` README.md · `REF` docs/REFERENCE.md · `RN` docs/RELEASE_NOTES.md ·
`VR` clients/vscode/README.md · `VP` clients/vscode/package.json · `VC`
clients/vscode/CHANGELOG.md · `CP` clients/vscode/src/chatPanel.ts · `MJ`
clients/vscode/media/main.js.

The version line on every page: `VR:69-70`, `VP:5-6`, `RN:8`.

## Get started

| Page | Sources |
|---|---|
| `index` Overview | `R:8,26-27,104-110,125-134,166-178`; `VR:3-4,23-24`; `VC:30-36` |
| `getting-started/install-vscode` | `VR:56-72`; `R:71-82`; `VP:20-22` (engines); `REF:1741-1744`; run (panel) |
| `getting-started/install-terminal` | `R:45-59,237-253`; `REF:32-37,101-111,128-133`; `npm/mochiii/platform.js:72` |
| `getting-started/first-run` | `REF:101-111,115-117,281-286,663-669,776-779`; `RN:27-28`; `clients/tui/main.go:40-41`; `VR:28-36,56-61`; `VC:42-43`; `CP:4256`; run (index offer, first screen, panel) |
| `getting-started/update-and-uninstall` | `R:84-102`; `REF:35-37,92-99`; `VC:11-18`; `VR:69-72`; `RN:102-118` |
| `getting-started/beta` | `VR:63-79`; `REF:1730-1744`; `RN:116-117`; `VP:133-259` (Show Daemon Log) |

## Models

| Page | Sources |
|---|---|
| `models/choosing-a-model` | `REF:210-236,241-242,248-256,718-744,828-850`; `RN:176-177`; `clients/vscode/src/slashCommands.ts:76-78`; `CP:4339-4341`; `clients/vscode/src/chatPages/markup.ts:53-57`; `models.json:3`; run (provider list) |
| `models/openrouter` | `protocol/providers.go:52-53`; `REF:224-230,237-239,355,461-465,490-493,580-583`; `models.json:3-24` |
| `models/anthropic` | `protocol/providers.go:56-57`; `REF:210-230,241-242` |
| `models/google-gemini` | `protocol/providers.go:58-59`; `REF:210-230,241-242` |
| `models/groq` | `protocol/providers.go:62-63`; `REF:210-230,241-242` |
| `models/openai-compatible` | `REF:223,264-265,353-357,440-442,586-590,848`; `VP:63-74`; `VR:43-45`; `protocol/providers.go:54-55` |
| `models/other-providers` | `protocol/providers.go:51-83,140-177`; `REF:210-236,831-834` |
| `models/local-models` | `R:180-201`; `REF:359-438`; `VR:43-46`; `clients/vscode/src/apiKey.ts:218-221`; run (`/agent on` check → compact agent; VS Code no-key notice) |

## Using Mochiii

| Page | Sources |
|---|---|
| `using/vscode` | `VP:133-259` (commands); `CP:4205-4215,4317-4369`; `clients/vscode/src/chatPages/markup.ts:53-57`; `VC:22-27,37-44`; `RN:76-100`; `VP:81-85`; `clients/vscode/src/workingFolder.ts:1-14`; `clients/vscode/src/daemonClient.ts:1090-1112`; run (panel, ⋯ menu, working line) |
| `using/terminal` | `REF:742-811,816-826,876-899,663-669`; `RN:10-38,66-70`; `clients/tui/slash.go:290-321`; `clients/tui/main.go:43`; `clients/tui/transcriptbound.go:62-63`; run (answer, tool line, `/help`) |
| `using/modes` | `CP:4417-4437,2290-2340,2920-2925`; `VP:104-116`; `clients/vscode/src/autoConsent.ts:1-19`; `clients/vscode/src/autoAccess.ts:1-25,62-68,90-96`; `VC:30-39`; `daemon/mcpconfig.go:1197-1198`; `clients/vscode/src/slashCommands.ts:114-116`; `daemon/planmode.go:152-161`; `clients/tui/slash.go:88,163`; `REF:765-774`; `RN:40-48,191`; run (mode menu, Auto warning, auto-approve) |
| `using/adding-context` | `CP:860-939,4376-4382`; `MJ:102,1155-1160`; `clients/vscode/src/attachmentExtract.ts:1-49,70-76,120-153`; `VP:81-85`; `VC:39-41`; `REF:870-874,1031-1032,1563-1565`; run (+ menu) |
| `using/approvals` | `MJ:2697-2745`; `clients/vscode/src/autoAccess.ts:62-68`; `REF:1303-1326,1368-1372,1052-1058,1239-1250`; `RN:40-48,58-64,147-153,160-162,188-190`; `daemon/mcpconfig.go:1192-1198`; `clients/tui/autoapprove.go:13-24`; run (VS Code card, terminal question, edit review) |
| `using/undo-and-backups` | `REF:321,1058,1086-1089,1239-1267`; `RN:42-45`; `daemon/fileops.go:30-45`; `MJ:3118-3141`; run (backup summary, refused edits) |
| `using/history` | `REF:657-695,1482-1491`; `RN:76-100,183-187`; `VP:120-124`; `CP:4206-4215`; `clients/tui/slash.go:86`; `clients/vscode/src/slashCommands.ts:62`; `clients/tui/transcriptbound.go:62-63`; run (unsaved-quit prompt) |
| `using/commands` | `clients/tui/slash.go:79-185`; `clients/vscode/src/slashCommands.ts:44-236`; `REF:1380-1382`; `VC:37-39` |

## Features

| Page | Sources |
|---|---|
| `features/long-tasks` | `REF:1377-1455,609-615`; `clients/tui/slash.go:135-176`; `clients/vscode/src/taskRun.ts:1-27`; `VC:37-39`; `CP:2093-2096`; run (working and stopped lines) |
| `features/specs` | `REF:602-605,697-706`; `clients/tui/slash.go:106`; `clients/vscode/src/slashCommands.ts:68-70`; `clients/vscode/src/chatPages/markup.ts:128` and `clients/vscode/media/pages.js:653` (Customize → Specs, seen in run); the 1.6.0 page this replaces, verified then by a run |
| `features/project-rules` | `REF:1512-1545`; `clients/tui/slash.go:99-101` |
| `features/github` | `REF:1547-1586`; `clients/tui/slash.go:102-105` |
| `features/team` | `clients/tui/slash.go:125-127`; `clients/vscode/src/slashCommands.ts:130-133,311-327`; `daemon/roles.go:154-157`; `REF:607,705-706` |
| `features/spending-limits` | `REF:638-655`; `clients/tui/slash.go:97-98`; `clients/vscode/src/slashCommands.ts:118-119`; run (`/usage`, `/budget`, Account page) |
| `features/web-tools` | `REF:498-548,414-415,1410-1412`; `RN:50-56`; `models.agent.json:96-97`; `models.json:36-37`; `VC:28-29`; `VP:75-80` |
| `features/indexing` | `REF:99,169-191,974-1032,1588-1590,1654-1657`; `R:106-110,247-253`; `VR:28-36`; `VC:42-43`; `clients/tui/main.go:40` |

## MCP

| Page | Sources |
|---|---|
| `mcp/overview` | `REF:1098-1108,1202-1219,1752`; `VR:23-24`; `clients/vscode/src/mcpMarketplace.ts:200-210`; run (Customize → MCP, MCP Servers view) |
| `mcp/marketplace` | `clients/vscode/src/mcpMarketplace.ts:200-210`; `VP:125-130`; `RN:163-167`; `VR:23-24`; run (notice, Marketplace) |
| `mcp/add-a-server` | `REF:1110-1201,1224-1231`; `VR:23-24`; `RN:136-139,206`; `VP:133-259`; the 1.6.0 page this replaces, verified then by a run; run (VS Code form) |
| `mcp/keys-and-variables` | `REF:351,1186-1194,1220-1223,1159-1161`; `RN:140-153`; the 1.6.0 page this replaces; run (VS Code form text) |
| `mcp/troubleshooting` | `RN:140-158`; `REF:1202-1219,1230-1231`; `clients/vscode/src/slashCommands.ts:52-54`; `VP:133-259` |

## Reference

| Page | Sources |
|---|---|
| `reference/built-in-tools` | `daemon/mcpconfig.go:1157-1199`; `models.agent.json:86-109`; `models.json:29-38`; `daemon/builtinconfig.go:24`; `daemon/mcpbuiltin.go:380-616`; `daemon/fileops.go:323-353`; `daemon/runcommand.go:61-62`; `daemon/checkpoint.go:321`; `daemon/investigate.go:119-120`; `daemon/githistory.go:340-341`; `daemon/spec.go:279,517`; `daemon/longtask.go:942,968`; `REF:1207-1208,1303-1318,1415` |
| `reference/vscode-settings` | `VP:63-130`; `CP:2920-2925`; run (Settings page) |
| `reference/models-json` | `REF:444-496,333,1328-1343,1439-1443,641`; `models.json:1-38`; `daemon/builtinconfig.go:24`; `VP:75-80` |
| `reference/environment-variables` | `REF:349-357,98,867,1220-1221`; `clients/tui/main.go:41-43,50`; `clients/tui/inline.go:147`; `clients/tui/transcriptbound.go:62-63` |
| `reference/file-locations` | `REF:92-99,202-203,1535-1537,1576-1577`; `daemon/fileops.go:38-40`; `RN:116-117`; the 1.6.0 page this replaces |
| `reference/cli-flags` | `clients/tui/main.go:37-43`; `REF:84-90,222-246,309-341` |

## Help

| Page | Sources |
|---|---|
| `troubleshooting` | `RN:102-132,192-194`; `REF:113-143,367-368,901-912`; `VR:69-72`; `clients/vscode/src/daemonClient.ts:1090-1112`; `clients/vscode/src/apiKey.ts:218-221`; run (VS Code no-key notice) |
| `help/privacy-and-data` | `R:228-233`; `VR:48-54`; `REF:955-967,997-1003,1312-1316,1368-1372,1618-1653,527-531`; `clients/vscode/src/attachmentExtract.ts:1-6` |
| `help/faq` | the pages it links to |
| `help/release-notes` | `VC:6-55,100-107`; `RN:8-70,74-218,220-243` |

## Redirects

| Old path | New path |
|---|---|
| `/getting-started/install` | `/getting-started/install-vscode` |
| `/getting-started/connect-a-model` | `/models/choosing-a-model` |
| `/using/terminal-commands` | `/using/commands` |
| `/using/plan-and-spec` | `/features/specs` |
| `/using/saved-sessions` | `/using/history` |
| `/reference/settings-and-files` | `/reference/file-locations` |
