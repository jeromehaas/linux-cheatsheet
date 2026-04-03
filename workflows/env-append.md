# Workflow: Append to .env

## Add a new line

```bash
printf '\nAPI_URL=http://localhost:3000\n' >> .env   # <- append safely
```

## Only add if missing

```bash
grep -q '^API_URL=' .env || printf '\nAPI_URL=http://localhost:3000\n' >> .env
```

## Replace existing key

```bash
sed -i 's|^API_URL=.*$|API_URL=http://localhost:3000|' .env      # <- GNU sed
sed -i '' 's|^API_URL=.*$|API_URL=http://localhost:3000|' .env   # <- macOS/BSD sed
```
