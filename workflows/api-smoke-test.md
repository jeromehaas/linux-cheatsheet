# Workflow: API smoke test

## Reachability

```bash
curl -sS https://api.example.com/health        # <- body only
curl -i https://api.example.com/health         # <- headers + body
curl -I https://api.example.com/health         # <- headers only
curl -v https://api.example.com/health         # <- verbose request/response
```

## Status code and JSON

```bash
curl -sS -w '\n%{http_code}\n' https://api.example.com/health   # <- append status code
curl -sS https://api.example.com/health | jq .                  # <- pretty-print JSON
curl -sS https://api.example.com/health | jq -r '.status'       # <- extract field
```
