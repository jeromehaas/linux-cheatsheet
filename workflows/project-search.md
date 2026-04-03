# Workflow: Project search

## Search for a string, class, env var, or endpoint

```bash
rg "API_URL" .                              # <- fast search
rg -n "class\s+User" .                      # <- regex class search
rg -g'*.{js,ts,tsx,vue}' "GET /api/v1" .    # <- only selected file types
```

## Universal fallback

```bash
grep -RIn "API_URL" .                                                 # <- recursive grep
grep -RIn --exclude-dir=node_modules --exclude-dir=.git "API_URL" .   # <- skip noisy dirs
```

## Git-aware search

```bash
git grep "API_URL"                       # <- only tracked files
git log -S "API_URL" --oneline           # <- commits that added/removed it
```
