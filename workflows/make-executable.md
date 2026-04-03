# Workflow: Make executable

## Check / add shebang

```bash
head -n 1 script.sh           # <- inspect first line
#!/usr/bin/env bash           # <- common bash shebang
```

## Make script executable

```bash
chmod +x script.sh            # <- add executable bit
./script.sh                   # <- run from current directory
```
