# Themes, Colors & Fonts Guide

## Where Themes Live

- **Windows Terminal**: `%LOCALAPPDATA%\Packages\Microsoft.WindowsTerminal_*\LocalState\settings.json`
- **Neovim**: `~/.config/nvim/` (e.g., `tokyonight`, `catppuccin`, `gruvbox`)
- **tmux**: `~/.tmux.conf` / `~/.config/tmux/tmux.conf` (status bar, pane borders)
- **Starship**: `~/.config/starship.toml` (palettes and module styles)

## Common Tasks & Fixes

### 1. True Color (24-bit) Support in tmux & nvim
If colors look washed out or wrong inside tmux:
- In `~/.tmux.conf`:
  ```tmux
  set -g default-terminal "tmux-256color"
  set -ag terminal-overrides ",xterm-256color:RGB"
  ```
- In Neovim (`init.lua`):
  ```lua
  vim.opt.termguicolors = true
  ```
- Test true color in Bash: `echo "$COLORTERM"` (should be `truecolor` or `24bit`).

### 2. Fonts in WSL
- Fonts for terminal rendering must be installed on the **Windows host**, not inside WSL.
- Set the Nerd Font in Windows Terminal profile settings so icons in `nvim`, `tmux`, and `starship` render cleanly.
