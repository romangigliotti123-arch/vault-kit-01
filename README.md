# Roblox Dev Mastery Vault: kit

Built and maintained by Roman (GitHub: romangigliotti123-arch)

## Quick start

**HOW TO START USING**
- Start a new Claude session in your vault folder (for example `~/Obsidian/claudes-vault`); that folder has everything loaded.

**HOW TO SEE SKILLS AND AGENTS**
- Type `/rbx-list` in that session, or `/` then `rbx-`.

**THE TWO MODS (ALREADY INSTALLED)**
- Type `/reload-plugins` once; they run in the vault folder only. Remove: `/plugin`, or the installer's `--no-mods`.

**HOW TO MAKE A GAME IDEA**
- `/rbx-ideas` finds one fresh idea (reply `another`, `build it` or `plan`); `/rbx-idea-creator` starts from yours.

**HOW TO BUILD A GAME**
- `/rbx-workflow` builds a game stage by stage; resume with "I want to work on <game name>".

**HOW TO UPDATE**
- Type `/rbx-update` (works from any session).

**NOT SURE WHICH SKILL?**
- Tell Claude what you want to do and it names the skill; `/rbx-list` shows them all.

More details: `MANUAL-READ.md` in the vault folder (or the site's `/manual` page).

The Claude kit of the Roblox Dev Mastery Vault (Roblox game development knowledge base plus a manager toolkit): 18 Roblox agents (including the hidden-rubric idea judge), slash-command skills (`/rbx-workflow`, `/rbx-make`, `/rbx-update`, ...), helper tools, and the setup runbook for AI agents.

**Loaded only in the vault folder.** The kit is installed into `~/.claude/claude-kit` and does not load into normal Claude Code sessions. The vault folder itself (your clone, for example `~/Obsidian/claudes-vault`) is permanently loaded: the installer and every `/rbx-update` write the vault skills and agents, art-direction and visual-QA rules and reference-image pointers into its own `.claude/`, hidden from git together with your `Games/` and `Models/`. Load the vault by starting a Claude session in that folder; there is no load command. Always available everywhere: `/rbx-update`, `/rbx-check`, `/rbx-uninstall`.

## Install (one paste)

Paste this to Claude on the computer you want to set up:

> Set up the Roblox Dev Mastery Vault on my computer: fetch https://raw.githubusercontent.com/romangigliotti123-arch/vault-kit-01/main/SETUP-FOR-CLAUDE.md with curl and follow it exactly.

Claude clones the notes (https://github.com/romangigliotti123-arch/vault-notes-01.git), installs this kit, downloads the assets and reports at the end, telling you the vault folder to start your Claude session in. No questions, no tokens, no sudo. The runbook lists every command and everything it changes before it runs anything.

## What you trust

Installing runs code from this repository with your user rights (no admin): whoever controls the GitHub account `romangigliotti123-arch` controls what an update installs. Updates are manual (`/rbx-update`) unless you add the optional logon task. The tools only accept HTTPS sources under that account, verify asset zips by SHA-256 before extracting, and write extra repository shards only to the folders their `mount` list names. The full list, with how to verify and preview an update, is the "Trust model" in `claude-kit/INSTALL.md`.

## Update (one skill)

Run `/rbx-update` in Claude. It pulls new notes from vault-notes, refreshes the installed kit (and the folders where Roblox dev mode is loaded; an older always-on install is moved to the on-demand store automatically) and downloads changed asset zips. `/rbx-check` only reports whether something newer exists.

## Repositories

| Repository | What | Used by |
|---|---|---|
| [vault-kit](https://github.com/romangigliotti123-arch/vault-kit-01) (this repo) | `claude-kit/` (agents, skills, tools, mods), `SETUP-FOR-CLAUDE.md`, `repos.json` | first install |
| [vault-notes](https://github.com/romangigliotti123-arch/vault-notes-01) | the sanitised vault notes (Obsidian vault) with `claude-kit/` and the update scripts | install and `/rbx-update` |
| [vault-assets-01](https://github.com/romangigliotti123-arch/vault-assets-01) (and -02, ...) | asset zips as Release files + THIRD-PARTY-NOTICES.md (licences, sources); listed in `repos.json` (`assets`) | `claude-kit/tools/assets-sync.py` |
| [vault-refs-01](https://github.com/romangigliotti123-arch/vault-refs-01) (and -02, ...) | Roblox reference screenshots: frames from third-party games, for visual-quality comparison only (NOTICE.md has the credits and the takedown contact); listed in `repos.json` (`refs`) | `claude-kit/tools/refs-sync.py` (setup and `/rbx-update`; points the visual-QA step at them) |

`repos.json` is the one list of where everything lives; a new repository is added there and clients pick it up without any change on the user's side. The website https://vault-hhmi60uo.netlify.app/ is the viewer (search, graph, README); it is not needed for installing.

## By hand

```
git clone https://github.com/romangigliotti123-arch/vault-notes-01.git ~/Obsidian/claudes-vault
git clone --depth 1 https://github.com/romangigliotti123-arch/vault-kit-01.git /tmp/vault-kit && bash /tmp/vault-kit/claude-kit/install.sh
python3 ~/.claude/claude-kit/tools/assets-sync.py --vault ~/Obsidian/claudes-vault --base https://raw.githubusercontent.com/romangigliotti123-arch/vault-kit-01/main
```

(Windows: use `powershell -File .\claude-kit\install.ps1`; the full commands are in `SETUP-FOR-CLAUDE.md`.)

## Licence and credits

No open-source licence is declared for the kit itself. The notes and assets contain third-party material (Imported notes, Kenney / Quaternius / Poly Haven / ambientCG assets, open-source Luau libraries) that keeps its own licence and credits: see https://vault-hhmi60uo.netlify.app/README.html#licences and THIRD-PARTY-NOTICES.md in the vault-assets repositories. This repository is generated from a private master by the site build; do not edit it by hand.
