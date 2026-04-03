# Navigation

## Basics

```bash
pwd                     # <- current working directory
ls                      # <- list files
ls -la                  # <- all files with details
cd /etc                 # <- change directory
cd ..                   # <- go up
cd ~                    # <- home directory
cd -                    # <- previous directory
```

## Directory stack

```bash
pushd /etc              # <- go there and remember current dir
popd                    # <- return
dirs -v                 # <- show stack
```

## Tree view

```bash
tree -L 2 .             # <- show tree 2 levels deep
tree -L 3 /             # <- show root tree 3 levels deep
```

## Quick search

```bash
find . -maxdepth 2 -type d -name "src"     # <- find a directory
find . -maxdepth 3 -type f -name "*.env"   # <- find matching files
locate nginx.conf                          # <- locate DB search
```
