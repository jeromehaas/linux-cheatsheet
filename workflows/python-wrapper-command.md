# Workflow: Python wrapper command

## Create the script

```bash
mkdir -p ~/bin                                        # <- create a personal bin directory in your home folder
cat > ~/bin/run-tests <<'PY'                          # <- create the script file and write the Python code below into it
#!/usr/bin/env python3                                # <- run this script with Python 3 from the current PATH
import subprocess                                     # <- import Python's subprocess module to run shell commands
raise SystemExit(subprocess.call(["pytest", "-q"]))   # <- run pytest in quiet mode and exit with the same status code
```

## Make it executable

```bash
chmod +x ~/bin/run-tests      # <- add execute bit
```

## Add ~/bin to PATH

```bash
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc    # <- bash
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.zshrc     # <- zsh
source ~/.bashrc                                      # <- reload shell
```

## Run from anywhere

```bash
run-tests                               # <- now available as a command
```
