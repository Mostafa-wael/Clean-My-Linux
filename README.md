# Clean-My-Linux

The script I run when my Ubuntu laptop starts running out of space. It deletes caches that rebuild themselves, old app and package versions, and stale logs, then tells you how much it got back.

I rewrote it in 2026. The first version emptied every log file, deleted man pages and ran `deborphan` to remove "orphan" packages. That last one quietly uninstalled things I still needed (CPU microcode, for one). The new version sticks to stuff that's safe to lose.

## Install

```bash
git clone https://github.com/Mostafa-wael/Clean-My-Linux.git
cd Clean-My-Linux
sudo install -m 755 clean /usr/local/bin/clean
```

## Usage

```bash
sudo clean          # every user under /home, plus the system
clean               # only you, plus the system (asks for sudo)
clean --dry-run     # show what would go, delete nothing
clean --status      # disk, memory and pressure, no cleaning
clean --deep        # also clear the slow-to-rebuild stuff (see below)
```

Try `clean --dry-run` first so you know what it's about to touch.

## What gets cleaned

Per user:

- browser caches (Chrome, Chromium, Brave), npm and `npx` caches, `pnpm store prune`, uv, pip, Go build caches, TypeScript, Helm, Playwright and Puppeteer browsers, thumbnails, the Mesa shader cache, VS Code and Cursor cache folders, and the Trash
- extension folders VS Code and Cursor leave behind after updates
- old versions of CLI tools that keep a `versions` folder in `~/.local/share` (the one you're using stays)
- `.zs-old` and `.AppImage.old` backups in `~/Applications`

Docker: unused images and build cache. Volumes stay, they have your data in them.

System, with sudo:

- `apt autoclean`, `apt clean` and `apt autoremove --purge`
- config files left over from packages you already uninstalled
- journal logs older than 7 days
- rotated logs in `/var/log` (`.gz`, `.1`, `.old`), never the live ones
- disabled snap revisions, and it sets snap to keep only 2 from now on

Only with `--deep`:

- the Go module cache (`go clean -modcache`)
- pre-commit hook environments
- the agent cache in Cursor's `state.vscdb`, which can quietly grow to several GB. Chat history isn't touched. Cursor has to be closed. The file gets backed up first and restored if anything goes wrong.

## What it won't touch

`~/.cache/aws` (your AWS SSO login lives there), Docker volumes, live log files, man pages, and any package that's still installed.

## Requirements

Ubuntu or Debian with `bash`, `apt` and `python3`. snap, docker, pnpm, go and sqlite3 are optional; whatever isn't installed gets skipped.

Enjoy the free space!
