# Keybindings & Shortcuts Reference

Quick reference for keybindings across **tmux**, **Neovim (`nvim`)**, **Bash / Readline**, **Atuin**, **fzf**, **Starship**, and **Windows Terminal / WSL**.

---

## 1. tmux

*(Default prefix: `Ctrl + b`, shown below as `prefix`)*

### Sessions
| Key | Action |
|---|---|
| `prefix + d` | Detach from current session |
| `prefix + s` | List / switch sessions |
| `prefix + $` | Rename current session |
| `prefix + (` / `)` | Switch to previous / next session |

### Windows
| Key | Action |
|---|---|
| `prefix + c` | Create new window |
| `prefix + ,` | Rename current window |
| `prefix + n` / `p` | Next / previous window |
| `prefix + 0..9` | Switch to window by number |
| `prefix + &` | Close current window |

### Panes
| Key | Action |
|---|---|
| `prefix + %` | Split pane vertically (left/right) |
| `prefix + "` | Split pane horizontally (top/bottom) |
| `prefix + Arrow` | Move between panes |
| `prefix + z` | Toggle pane zoom (fullscreen) |
| `prefix + x` | Close current pane |
| `prefix + {` / `}` | Swap pane left / right |
| `prefix + Space` | Cycle pane layouts |

### Copy Mode & Plugins (TPM)
| Key | Action |
|---|---|
| `prefix + [` | Enter copy mode (`q` to exit, `Space` to select, `Enter` to copy) |
| `prefix + ]` | Paste buffer |
| `prefix + I` | Install TPM plugins |
| `prefix + U` | Update TPM plugins |

---

## 2. Neovim (`nvim`)

### Modes
| Key | Action |
|---|---|
| `i` / `a` / `o` | Insert before / after cursor / new line below |
| `v` / `V` / `Ctrl + v` | Visual / Visual Line / Visual Block mode |
| `Esc` or `Ctrl + [` | Return to Normal mode |
| `:` | Command-line mode |

### Navigation & Editing (Normal Mode)
| Key | Action |
|---|---|
| `h` `j` `k` `l` | Left / Down / Up / Right |
| `w` / `b` / `e` | Next word / Previous word / End of word |
| `0` / `^` / `$` | Start of line / First non-blank / End of line |
| `gg` / `G` | Top / Bottom of file |
| `Ctrl + d` / `Ctrl + u` | Scroll half-page down / up |
| `dd` / `yy` / `p` | Delete (cut) line / Yank (copy) line / Paste |
| `u` / `Ctrl + r` | Undo / Redo |
| `.` | Repeat last change |

### Search & Replace
| Key | Action |
|---|---|
| `/pattern` | Search forward (`n` next, `N` previous) |
| `?pattern` | Search backward |
| `*` / `#` | Search word under cursor forward / backward |
| `:%s/old/new/gc` | Replace all with confirmation |

### Splits & Buffers
| Key | Action |
|---|---|
| `:vsplit` / `:split` | Vertical / Horizontal split |
| `Ctrl + w` then `h/j/k/l` | Move between splits |
| `Ctrl + w` then `q` | Close current split |
| `:bn` / `:bp` / `:bd` | Next buffer / Previous buffer / Delete buffer |

### Diagnostics & LSP (Common Defaults)
| Key | Action |
|---|---|
| `gd` | Go to definition |
| `gr` | Find references |
| `K` | Hover documentation |
| `[d` / `]d` | Previous / Next diagnostic |
| `:checkhealth` | Run Neovim health check |

---

## 3. Bash / Readline

| Key | Action |
|---|---|
| `Ctrl + a` / `Ctrl + e` | Move to start / end of line |
| `Ctrl + f` / `Ctrl + b` | Move forward / backward one character |
| `Alt + f` / `Alt + b` | Move forward / backward one word |
| `Ctrl + u` / `Ctrl + k` | Cut from cursor to start / end of line |
| `Ctrl + w` | Cut word before cursor |
| `Ctrl + y` | Paste (yank) last cut text |
| `Ctrl + l` | Clear screen |
| `Ctrl + c` | Interrupt / cancel current command |
| `Ctrl + d` | Exit shell (or EOF) |
| `Ctrl + z` | Suspend current process (`fg` to resume) |

---

## 4. Atuin (Shell History)

| Key | Action |
|---|---|
| `Ctrl + r` | Open Atuin interactive history search |
| `Up` | Open Atuin search (if bound) |
| `Enter` | Execute selected command |
| `Tab` | Insert selected command into prompt without running |
| `Ctrl + r` (inside Atuin) | Cycle search filter mode (global / host / session / directory) |
| `Ctrl + s` (inside Atuin) | Cycle search mode (prefix / fulltext / fuzzy / skim) |
| `Esc` / `Ctrl + c` | Exit Atuin without selecting |

---

## 5. fzf (Fuzzy Finder)

| Key | Action |
|---|---|
| `Ctrl + t` | Fuzzy-find files and paste path into command line |
| `Ctrl + r` | Fuzzy-search command history (when Atuin is not overriding it) |
| `Alt + c` | Fuzzy-find directory and `cd` into it |
| `Tab` / `Shift + Tab` | Multi-select / deselect items |

---

## 6. Starship Prompt

Starship is a prompt renderer (no interactive keybindings), but useful CLI commands include:

| Command | Action |
|---|---|
| `starship timings` | Profile module execution times |
| `starship print-config` | Print active configuration |
| `starship explain` | Explain what each prompt module is showing |

---

## 7. Windows Terminal & WSL

| Key / Command | Action |
|---|---|
| `Ctrl + Shift + t` | New tab |
| `Ctrl + Shift + w` | Close tab/pane |
| `Alt + Shift + d` | Duplicate/split pane automatically |
| `Alt + Shift + +` / `-` | Split pane vertically / horizontally |
| `Alt + Arrow` | Move between Windows Terminal panes |
| `Ctrl + Shift + c` / `v` | Copy / Paste |
| `wsl --shutdown` *(PowerShell)* | Restart WSL2 VM |
