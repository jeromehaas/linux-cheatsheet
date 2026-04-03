# Setup basic dot files

## Minimal ~/.vimrc

```bash
cat > ~/.vimrc <<'EOF'   # <- create or overwrite the Vim config file with the content below
set number               # <- show absolute line numbers
set relativenumber       # <- show relative line numbers
set tabstop=4            # <- display tabs as 4 spaces wide
set shiftwidth=4         # <- use 4 spaces for auto-indent operations
set expandtab            # <- insert spaces instead of real tab characters
set cursorline           # <- highlight the current line
syntax on                # <- enable syntax highlighting
```

## Minimal ~/.tmux.conf

```bash
cat > ~/.tmux.conf <<'EOF'  # <- create or overwrite the tmux config file with the content below
set -g mouse on             # <- enable mouse support in tmux
set -g history-limit 50000  # <- keep a larger scrollback history
setw -g mode-keys vi        # <- use Vim-style keys in copy/scroll mode
```

## Useful shell baseline

```bash
cat >> ~/.bashrc <<'EOF'      # <- append the following shell settings to .bashrc
export EDITOR=vim             # <- use Vim as the default editor
export PAGER=less             # <- use less for paged output
HISTFILESIZE=10000            # <- keep more commands in shell history

alias ll='ls -lah'            # <- long file listing with hidden files
alias gs='git status -sb'     # <- compact git status shortcut

mcd() {                       # <- function: make directory, then enter it
  mkdir -pv "$1" && cd "$1"   # <- create the directory path and cd into it if successful
}

source ~/.bashrc              # <- reload the Bash config in the current shell

```
