# Customization: aliases

## Safer defaults

```bash
alias rm='rm -i'       # <- confirm delete
alias cp='cp -i'       # <- confirm overwrite
alias mv='mv -i'       # <- confirm overwrite
```

## Navigation and listing

```bash
alias ..='cd ..'       # <- go one directory up
alias ...='cd ../..'   # <- go two directories up
alias ll='ls -lah'     # <- long listing with hidden files
```

## Git

```bash
alias g='git'                                           # <- short git command
alias gs='git status -sb'                               # <- compact git status
alias gl='git log --oneline --decorate --graph -n 20'   # <- compact recent git history
```

## Search

```bash
alias rgf='rg -n --hidden --glob "!.git/*"'   # <- search with line numbers, include hidden files, skip .git
```

## Persist aliases

```bash
echo "alias ll='ls -lah'" >> ~/.bashrc   # <- append alias to bash config
source ~/.bashrc                         # <- reload bash config in current shell
```
