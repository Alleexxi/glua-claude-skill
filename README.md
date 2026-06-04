# glua - Garry's Mod Lua expert skill for Claude Code

A [Claude Code](https://claude.com/claude-code) **Agent Skill** that turns Claude
into an expert GLua developer: byte-accurate GMod API signatures, correct
**client / server / menu** realms, hooks, VGUI/derma panels, meta-table classes,
enumerations, and asset paths - all sourced from the official Facepunch wiki.

When you ask Claude about Garry's Mod addons, gamemodes, SWEPs, scripted entities,
derma, the `net` library, hooks, etc., it opens the exact reference file instead
of guessing a signature or realm.

## What's inside

| Area | Units | Members |
|---|---|---|
| Globals (`references/globals.md`) | - | 334 |
| Classes (`references/classes/`) | 45 | 2,296 |
| Libraries (`references/libraries/`) | 88 | 1,295 |
| Panels / VGUI (`references/panels/`) | 130 | 1,153 |
| Hooks (`references/hooks/`) | 10 namespaces | 547 |
| Enums (`references/enums/`) | 100 families | 3,002 |
| Assets (`references/assets/`) | icon16 (1011), flags16 (247), sound paths | - |

Every member carries its exact signature, arguments, returns, per-member realm,
and notes/warnings/bugs, and links back to its **wiki page** and **engine source**.


## Install

Pick whichever fits your workflow. After any method, start a new session and
confirm with `/skills` (look for `glua`). The skill activates automatically on
GLua questions, or explicitly via `/glua`.

### Option A - Claude Code plugin (recommended)

This repo doubles as a single-plugin marketplace. Inside Claude Code:

```text
/plugin marketplace add Alleexxi/glua-claude-skill
/plugin install glua@glua-claude-skill
```

### Option B - `npx skills`

The [`skills`](https://www.npmjs.com/package/skills) CLI installs from this repo
into your agent's skills folder:

```bash
npx skills add Alleexxi/glua-claude-skill        # project-level (.claude/skills/)
npx skills add Alleexxi/glua-claude-skill -g     # user-level (~/.claude/skills/)
```

### Option C - manual clone

The skill lives at `skills/glua/` inside the repo, so copy *that* folder (not the
repo root) into your skills directory:

- **macOS / Linux:** `~/.claude/skills/glua`
- **Windows:** `%USERPROFILE%\.claude\skills\glua`

```bash
git clone https://github.com/Alleexxi/glua-claude-skill.git /tmp/glua-claude-skill
cp -r /tmp/glua-claude-skill/skills/glua ~/.claude/skills/glua
```

Use a project's `.claude/skills/glua/` instead to scope it to one repository.

## Attribution & license

API data is derived from the community-maintained
[Garry's Mod wiki](https://wiki.facepunch.com/gmod/) (© Facepunch Studios &
contributors); this skill condenses that documentation for offline LLM use and
links each entry back to the canonical page. Engine source links point to
[Facepunch/garrysmod](https://github.com/Facepunch/garrysmod). `wiki.json` itself
comes from the `vscode-glua-enhanced` resources.

**License:** [MIT](LICENSE) for this skill and its tooling. The bundled API
reference data is derived from the Facepunch wiki - see [`NOTICE`](NOTICE) for
attribution.
