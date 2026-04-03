# Workflow: Recent changes

## Files changed in the last hour

```bash
find . -type f -mmin -60        # <- modified in last 60 minutes
```

## Files changed today

```bash
find . -type f -daystart -mtime -0   # <- modified since start of today
```

## Newest files first

```bash
find . -type f -printf '%TY-%Tm-%Td %TH:%TM %p\n' | sort -r | head -n 50   # <- GNU find
```
