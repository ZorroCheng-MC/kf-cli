# kf-cli — KnowledgeFactory CLI

Obsidian knowledge management for Claude Code and multi-agent systems. Capture YouTube videos, articles, ideas, and GitHub repos — all with AI auto-tagging and one-command publishing to GitHub Pages.

No Docker. No MCP. Just CLI tools.

## Install

### Option A — npm via zorskills (recommended)

Installs `kf-cli` alongside all ZorCorp skills and symlinks them into every agent on your machine.

```bash
npm install -g @zorcorp/zorskills
```

Available immediately in:
- **Claude Code** — invoke as `/kf-cli:command`
- **OpenClaw** — agent picks up on next restart

Update:

```bash
npm update -g @zorcorp/zorskills
```

### Option B — Claude Code Plugin Marketplace

For auto-update notifications inside Claude Code:

```
/plugin marketplace add ZorCorp/zorskill
/plugin install kf-cli
/plugin list
```

Then run `/kf-cli:setup` to configure your vault path.

---

## Prerequisites

```bash
brew install yt-dlp gh jq uv
```

Verify: `yt-dlp --version && gh --version && jq --version && uvx --version`

---

## Commands

| Command | Description |
|---------|-------------|
| `/kf-cli:capture <content>` | Smart router — auto-detects YouTube, GitHub, URL, or text |
| `/kf-cli:youtube-note <url>` | YouTube video note with transcript and curriculum |
| `/kf-cli:idea <text>` | Quick idea capture with AI tagging |
| `/kf-cli:gitingest <github-url>` | GitHub repository analysis digest |
| `/kf-cli:study-guide <source>` | Comprehensive study guide from any content |
| `/kf-cli:article <topic>` | Article with auto-generated Gemini hero image |
| `/kf-cli:publish <filename>` | Publish to GitHub Pages (sharehub) |
| `/kf-cli:share <filename>` | Share via URL-encoded link (no server needed) |
| `/kf-cli:bulk-auto-tag` | Bulk AI tagging for existing notes |
| `/kf-cli:semantic-search <query>` | Search vault via Obsidian REST API |
| `/kf-cli:setup` | Setup wizard with dependency checks |

See [COMMANDS.md](COMMANDS.md) for full reference.

---

## Project Structure

```
kf-cli/
├── .claude-plugin/
│   └── marketplace.json       # Plugin manifest
├── commands/                   # Command .md files (prompt definitions)
├── templates/                  # Note templates
├── scripts/
│   ├── core/                   # publish.sh, fetch-youtube-transcript.sh
│   └── helpers/common.sh       # Utility functions
├── SKILL.md                    # Skill definition (for ~/.agents/skills/ installs)
├── COMMANDS.md                 # Full command reference
├── TROUBLESHOOTING.md
├── CHANGELOG.md
└── README.md
```

---

## Migrating from kf-claude

`kf-cli` provides the same commands as `kf-claude` without Docker or MCP dependencies. See [MIGRATION.md](MIGRATION.md).

---

**ZorCorp** · [github.com/ZorCorp/kf-cli](https://github.com/ZorCorp/kf-cli) · MIT License
