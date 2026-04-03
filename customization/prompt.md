# Customization: prompt

## Default-looking examples

```bash
[student@workstation ~] $   # <- normal user prompt
[student@workstation ~] #   # <- privileged/root prompt
```

## Simple PS1

```bash
export PS1='[\u@\h \w]\$ '   # <- [user@host cwd]$
```

## Green prompt

```bash
export PS1='\[\e[32m\][\u@\h \w]\[\e[0m\]\$ '   # <- wrap colours in \[ \]
```

## Add git branch

```bash
parse_git_branch() { git rev-parse --abbrev-ref HEAD 2>/dev/null; }   # <- get the current git branch name, hide errors outside git repos
export PS1='[\u@\h \w $(parse_git_branch)]\$ '                        # <- show [user@host current-dir branch]$ in the prompt
```

## Persist it

```bash
echo 'export PS1="[\u@\h \w]\$ "' >> ~/.bashrc   # <- append the prompt configuration to .bashrc
source ~/.bashrc                                 # <- reload .bashrc in the current shell
```
