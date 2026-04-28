# tmux config

A modern tmux configuration for **tmux 3.4+**, featuring the [Catppuccin](https://github.com/catppuccin/tmux) theme, [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator), true color & undercurl support, and Vi-style keybindings.

## Installation

```bash
# Clone the repo
git clone https://github.com/leoxiaobin/tmux-config.git ~/.tmux

# Symlink the config
ln -s ~/.tmux/.tmux.conf ~/.tmux.conf

# Install TPM (plugin manager)
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

# Launch tmux, then install plugins
tmux
# Inside tmux, press: Ctrl-q  I  (capital I)
```

## Quick Reference

> **Prefix key:** `Ctrl-q` (shown below as `<P>`)

### Sessions

| Key | Action |
|-----|--------|
| `tmux` | Start a new session |
| `tmux attach` | Reattach to last session |
| `<P> d` | Detach from session |
| `<P> s` | List / switch sessions |
| `<P> $` | Rename session |

### Windows (tabs)

| Key | Action |
|-----|--------|
| `<P> c` | New window (inherits current path) |
| `<P> C` | New window with a custom name |
| `<P> n` / `<P> p` | Next / previous window |
| `<P> 1-9` | Jump to window by number |
| `<P> ,` | Rename window |
| `<P> &` | Kill window |
| `<P> Ctrl-q` | Toggle last window |

### Panes (splits)

| Key | Action |
|-----|--------|
| `<P> v` | Split horizontally (left/right) |
| `<P> b` | Split vertically (top/bottom) |
| `<P> h j k l` | Navigate panes (vim-style) |
| `Ctrl-h/j/k/l` | Navigate panes **and Vim splits** seamlessly *(vim-tmux-navigator)* |
| `<P> H J K L` | Resize pane by 5 cells (repeatable) |
| `<P> x` | Kill pane |
| `<P> z` | Toggle pane zoom (fullscreen) |
| `<P> Space` | Cycle pane layouts |
| `<P> o` | Rotate panes |

### Layouts

| Key | Action |
|-----|--------|
| `<P> m` | Main-horizontal layout (66% main pane) |
| `<P> M` | Main-vertical layout (50% main pane) |

### Copy Mode (Vi-style)

| Key | Action |
|-----|--------|
| `<P> [` | Enter copy mode |
| `v` | Begin selection |
| `Ctrl-v` | Toggle rectangle selection |
| `y` | Yank to system clipboard |
| `q` | Exit copy mode |

> You can also select text with the **mouse** — it copies to the clipboard automatically via OSC 52.

### Misc

| Key | Action |
|-----|--------|
| `<P> r` | Reload config |
| `<P> ?` | List all key bindings |

## Plugins

Managed via [TPM](https://github.com/tmux-plugins/tpm):

| Plugin | Description |
|--------|-------------|
| [catppuccin/tmux](https://github.com/catppuccin/tmux) | Catppuccin Mocha theme with rounded window tabs |
| [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator) | Seamless `Ctrl-hjkl` navigation between Vim and tmux panes |

### Plugin Management

| Key | Action |
|-----|--------|
| `<P> I` | Install new plugins |
| `<P> U` | Update plugins |
| `<P> Alt-u` | Remove unused plugins |

## Features

- **True color & undercurl** — full RGB color and styled underlines in supported terminals
- **Mouse support** — click panes, resize by dragging borders, scroll through history
- **50,000-line scrollback** — generous history buffer
- **Smart path inheritance** — new windows and splits open in the current directory
- **Auto window renumbering** — no gaps after closing windows
- **OSC 52 clipboard** — copy/paste works over SSH without extra tools

## Customization

Edit `~/.tmux/.tmux.conf`, then reload with `<P> r`.

To change the Catppuccin flavor, uncomment and set:

```tmux
set -g @catppuccin_flavor "latte"   # latte | frappe | macchiato | mocha (default)
```

## License

MIT
