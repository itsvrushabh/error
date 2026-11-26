# Neovim (`nvim`) Guide

## Config Locations

- **Config root**: `~/.config/nvim/` (`init.lua` or `init.vim`)
- **Data / plugins**: `~/.local/share/nvim/`
- **State / logs**: `~/.local/state/nvim/` (including `lsp.log`)

## Common Tasks & Fixes

### 1. First-Line Diagnostics
- Run `:checkhealth` inside Neovim to inspect providers, clipboard, Treesitter, and LSPs.
- Check `:messages` for Lua stack traces or startup warnings.
- Test without user config: `nvim --clean`

### 2. LSP & Treesitter Issues
- **LSP status**: `:LspInfo` and `:LspLog`
- **Restart LSP**: `:LspRestart`
- **Treesitter**: `:TSUpdate` or `:TSInstallInfo`

### 3. Clipboard in WSL
If `+` / `*` registers fail in WSL:
- Install `win32yank.exe` (or use `wl-clipboard` / `xclip` if WSLg is active) and ensure it is on `PATH`.
- Verify with `:checkhealth` under **Clipboard**.

### 4. Reporting Config Issues
When an issue is found in the `nvim` config repository, create a GitHub issue ticket (`gh issue create`) in that repo containing:
- **Issue**: Exact error/`:messages` output, `:checkhealth` findings, and reproduction steps
- **Resolution**: The config/plugin/LSP fix that resolves it
- **Bypass / Workaround**: Temporary bypass (e.g., `nvim --clean`, disabling the offending plugin, or `:LspStop`)
