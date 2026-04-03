# Shell basics

## Prompt basics

```bash
[student@workstation ~] $  # <- normal user prompt
[student@workstation ~] #  # <- privileged/root-style prompt
id                         # <- if uid=0, you are root
```

## Command structure

```bash
command [option(s)] [arguments]  # <- common structure

ls -a                            # <- short option
ls --all                         # <- long option
```

## Helpful keyboard shortcuts

```text
Ctrl + L  -> clear screen
Ctrl + D  -> exit / logout
Ctrl + R  -> search command history
Ctrl + A  -> jump to beginning of line
Ctrl + E  -> jump to end of line
Ctrl + U  -> delete from start to cursor
Ctrl + K  -> delete from cursor to end
Alt + B   -> move back one word
Alt + F   -> move forward one word
```

## Command chaining

```bash
date; whoami; uptime     # <- run all commands, even if one fails
make && npm test         # <- second command runs only on success
foo || echo "failed"     # <- second command runs only if first fails
```

## History tricks

```bash
history                  # <- show command history
!!                       # <- repeat last command
sudo !!                  # <- rerun last command with sudo
!3                       # <- run history entry 3
!ssh                     # <- run last command starting with ssh
^usr^tmp                 # <- replace text in previous command and run it
```

## Variables

```bash
MY_NAME="jeromehaas"     # <- define a shell variable
echo "$MY_NAME"          # <- print variable
export NODE_ENV=prod     # <- export to child processes
printenv PATH            # <- print one env var
env | sort               # <- list env vars
```

## Dates and uptime

```bash
date                     # <- full date and time
date +%R                 # <- HH:MM
date +%x                 # <- local short date
uptime                   # <- uptime and load
```

## Quoting

```bash
echo hello world         # <- two arguments
echo "hello world"       # <- one argument with spaces
echo 'literal $HOME'     # <- no variable expansion
echo "$HOME"             # <- variable expansion
printf '%s\n' "text"     # <- safer than echo in scripts
```

## Redirection and pipes

```bash
echo "hello" > greeting.txt                     # <- overwrite file
echo "nice to see you" >> greeting.txt          # <- append to file
ls -l ok.txt missing.txt > out.txt 2> err.txt   # <- split stdout and stderr

cat fruits.txt | sort                           # <- sort lines
cat fruits.txt | sort > fruits-sorted.txt       # <- save sorted output
```

## Commands that work well in pipelines

```text
cat   <- print file contents
grep  <- filter lines by pattern
sort  <- sort lines
uniq  <- remove repeated neighbouring lines
wc    <- count lines / words / chars
head  <- show first lines
tail  <- show last lines
cut   <- extract columns
tr    <- translate / delete characters
sed   <- stream editing
awk   <- column/pattern processing
xargs <- turn stdin into command arguments
tee   <- show and save output
```

## Help

```bash
man grep                 # <- open manual page
man -k ssh               # <- search man page topics
ls --help                # <- quick option overview
type ls                  # <- show if command is alias/function/binary
```
