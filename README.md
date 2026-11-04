# Roblox Dev Mastery Vault: kit

Built and maintained by Roman (GitHub: romangigliotti123-arch)

The Claude kit of the Roblox Dev Mastery Vault (Roblox game development knowledge base plus a manager toolkit): 13 Roblox agents, slash-command skills (`/rbx-workflow`, `/rbx-make`, `/rbx-update`, ...), helper tools, and the setup runbook for AI agents.

**Off by default.** The kit is installed but does not load into normal Claude Code sessions: its skills and agents sit in an on-demand store (`~/.claude/claude-kit/vault-mode/`). In a Roblox project folder, type `/rbx-load`: that folder enters "Roblox dev mode" (the vault skills and agents, art-direction and visual-QA rules, reference images, learn step) and `/rbx-unload` turns it off again. Always available: `/rbx-load`, `/rbx-unload`, `/rbx-update`, `/rbx-check`, `/rbx-uninstall`.

## Install (one paste)

Paste this to Claude on the computer you want to set up:

> Set up the Roblox Dev Mastery Vault on my computer: fetch https://raw.githubusercontent.com/romangigliotti123-arch/vault-kit-01/main/SETUP-FOR-CLAUDE.md with curl and follow it exactly.

Claude clones the notes (https://github.com/romangigliotti123-arch/vault-notes-01.git), installs this kit (switched off), downloads the assets and reports at the end; then type `/rbx-load` in your Roblox project folder. No questions, no tokens, no sudo. The runbook lists every command and everything it changes before it runs anything.

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
