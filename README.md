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
Plus a hand-written [`references/guide.md`](references/guide.md): the realm model,
addon folder structure, a recursive autoloader, the `net` library, `NetworkVar`,
and SWEP/ENT/gamemode/derma skeletons.

## Install

Clone (or copy) this repo into your Claude Code **user skills** folder so the
directory is named `glua`:

- **macOS / Linux:** `~/.claude/skills/glua`
- **Windows:** `%USERPROFILE%\.claude\skills\glua`

```bash
git clone https://github.com/<you>/glua.git ~/.claude/skills/glua
```

Claude Code auto-discovers it from `SKILL.md` on the next session. Confirm with
`/skills` (look for `glua`). It activates automatically on GLua questions, or
explicitly via `/glua`. You can also place it in a project's
`.claude/skills/glua/` to scope it to one repository.

## Provenance

- **Generated:** the per-unit files under
  `references/{classes,libraries,panels,hooks,enums}/`, `references/globals*.md`,
  `references/assets/*`, and the baseline index tables in each category
  `README.md` were produced by a build script from `wiki.json` (a merged dump of
  the Facepunch wiki). The build tooling is maintained separately and is not part
  of this skill-only repository.
- **Hand-written:** `SKILL.md`, `references/guide.md`, and the curated overview
  prose at the top of each category `README.md` and the top `references/README.md`.

## Why `README.md` and not `CLAUDE.md`?

`SKILL.md` is the skill manifest (required filename). The `README.md` files serve
two purposes: GitHub renders them as per-folder landing pages, and they are the
skill's on-demand **index** files (Claude reads them by path). `CLAUDE.md` is a
separate feature - auto-loaded project memory for working *inside* a repo - and is
not used for skill content.

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
