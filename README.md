# kf-cli - KnowledgeFactory Native CLI Plugin

**Version**: 0.1.0
**Status**: Tested (8/8 commands pass)

## Overview

Native CLI-based Claude Code plugin for Obsidian knowledge management. Full-featured, no Docker or MCP dependencies required.

## Why kf-cli?

- **No Docker required** — uses yt-dlp, gh CLI, obsidian-cli, and direct file operations
- **Faster** — local I/O with no cold start penalty
- **Simpler** — fewer moving parts, easier to debug
- **Self-contained** — installs as a standalone plugin, no external services needed

## Installation

Open your Obsidian vault in Claude Code, then run:

```bash
# Step 1: Add the ZorCorp zorskill marketplace (one-time)
/plugin marketplace add ZorCorp/zorskill

# Step 2: Install kf-cli
/plugin install kf-cli

# Step 3: Verify
/plugin list
```

You should see `kf-cli` in the list. Then run `/kf-cli:setup` to configure.

> **Note**: Installation is done via Claude Code plugin commands — no git clone needed.

## Prerequisites

```bash
brew install yt-dlp gh jq uv
```

Verify: `yt-dlp --version && gh --version && jq --version && uvx --version`

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
| `/kf-cli:share <filename>` | Share via URL-encoded link (no server) |
| `/kf-cli:bulk-auto-tag` | Bulk AI tagging for existing notes |
| `/kf-cli:semantic-search <query>` | Search vault via Obsidian REST API |
| `/kf-cli:setup` | Setup wizard with dependency checks |

See [COMMANDS.md](COMMANDS.md) for full reference.

## Project Structure

```
kf-cli/
├── .claude-plugin/
│   └── marketplace.json       # Plugin manifest (11 commands)
├── commands/                   # Command .md files (prompt definitions)
├── templates/                  # Note templates
├── scripts/
│   ├── core/                   # publish.sh, fetch-youtube-transcript.sh
│   └── helpers/common.sh       # Utility functions
├── SKILL.md                    # CLI-native skill definition
├── COMMANDS.md                 # Full command reference
├── TROUBLESHOOTING.md          # Common issues and fixes
├── CHANGELOG.md                # Version history
└── README.md
```

## License

MIT

## Credits

Built by ZorCorp
