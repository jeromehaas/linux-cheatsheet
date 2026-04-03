# Workflow: Disk usage hunt

## Find large folders

```bash
du -h --max-depth=1 . | sort -h      # <- top-level folder sizes
du -sh .                             # <- total size of current folder
```

## Find large files

```bash
find . -type f -size +100M -print0 | xargs -0 ls -lh   # <- files over 100 MB
find . -type f -size +100M 2>/dev/null                 # <- ignore errors
```

## Common Node.js culprit

```bash
du -h --max-depth=2 node_modules 2>/dev/null | sort -h | tail   # <- biggest package dirs
```
