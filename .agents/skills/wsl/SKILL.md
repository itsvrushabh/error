---
name: wsl
description: >
  Master skill for managing, customizing, and troubleshooting a WSL (Arch Linux)
  development environment, including ~/.config/ files, shell (Bash/Zsh), Neovim (nvim),
  tmux, Starship prompt, themes, pacman/AUR packages, and WSL system configuration.
  Triggers: wsl, arch, pacman, aur, bash, zsh, shell, nvim, neovim, tmux, starship,
  themes, fonts, systemd, networking, interop, and CLI tooling errors.
---

# WSL Master Skill

Manage and troubleshoot a **WSL + Arch Linux** development environment—covering the shell, Neovim, tmux, Starship, theming, package management, and WSL system configuration.

## Topic Guides

Deeper instructions for each area live next to this file. Read the matching guide before starting:

- [`shell.md`](shell.md) — Bash/Zsh configuration, `PATH`, environment variables, aliases, quoting, and script debugging
- [`nvim.md`](nvim.md) — Neovim config (`~/.config/nvim/`), plugins, LSP, Treesitter, `:checkhealth`, and Lua errors
- [`tmux.md`](tmux.md) — tmux sessions, panes, keybindings, TPM plugins, and custom scripts (e.g., `tmux-whisper`)
- [`starship.md`](starship.md) — Starship prompt (`~/.config/starship.toml`), modules, Nerd Fonts, and prompt latency
- [`themes.md`](themes.md) — Terminal, editor, tmux, and prompt theming, colorschemes, and fonts
- [`pacman.md`](pacman.md) — Arch Linux `pacman`, AUR helpers (`yay`/`paru`), keyrings, mirrors, and broken dependencies
- [`system.md`](system.md) — WSL configuration (`/etc/wsl.conf`, `.wslconfig`), `systemd`, DNS/networking, filesystem, and Windows interop

## Critical Safety Rules

- **Prefer user-local configs**: Edit `~/.config/`, `~/.bashrc`, `~/.tmux.conf`, etc. rather than system-wide `/etc/` or `/usr/share/` files unless explicitly required.
- **Backup before major edits**: When modifying critical configs (`/etc/wsl.conf`, `/etc/pacman.conf`, `~/.bashrc`), keep a backup or verify syntax before reloading.
- **Linux filesystem for projects**: Keep repositories and heavy I/O workloads under `/home/<user>/` rather than `/mnt/c/` for performance and proper POSIX permissions.

## Quick Triage Workflow

1. **Capture the exact error**: Record the full error message, exit code (`echo $?`), and command.
2. **Isolate the layer**:
   - Shell / PATH? → [`shell.md`](shell.md)
   - Editor / LSP? → [`nvim.md`](nvim.md)
   - Multiplexer / keybindings? → [`tmux.md`](tmux.md)
   - Prompt rendering? → [`starship.md`](starship.md)
   - Colors / fonts? → [`themes.md`](themes.md)
   - Packages / updates? → [`pacman.md`](pacman.md)
   - WSL / systemd / DNS? → [`system.md`](system.md)
3. **Verify after fixing**: Reload the relevant config (`source ~/.bashrc`, `tmux source-file ~/.tmux.conf`, `:checkhealth`, etc.) and re-run the failing command.
