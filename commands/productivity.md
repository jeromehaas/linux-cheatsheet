# Productivity

## Search in a project

```bash
rg "API_URL" .                                                        # <- fast repo search
rg -n "class User" src/                                               # <- line numbers
rg -g'*.{js,ts,tsx,vue}' "fetch\(" .                                  # <- filter by extension

grep -RIn "API_URL" .                                                 # <- universal fallback
grep -RIn --exclude-dir=node_modules --exclude-dir=.git "API_URL" .   # <- skip noisy dirs

git grep "API_URL"                                                    # <- only tracked files
git log -S "API_URL" --oneline                                        # <- commits that changed a string
```

## Find by time / size

```bash
find . -type f -mmin -60             # <- modified in last hour
find . -type f -daystart -mtime -0   # <- modified today
find . -type f -size +100M           # <- bigger than 100 MB
```

## Text tools

```bash
sort file.txt                   # <- sort lines
uniq file.txt                   # <- remove repeated neighbouring lines
wc -l file.txt                  # <- line count
cut -d: -f1 /etc/passwd         # <- first field
tr '[:lower:]' '[:upper:]'      # <- lower to upper
sed -n '1,20p' file.txt         # <- print first 20 lines
awk '{print $1}' file.txt       # <- print first column
tee output.log                  # <- save and display output
```

## JSON

```bash
curl -sS https://api.example.com/health | jq .              # <- pretty JSON
curl -sS https://api.example.com/health | jq -r '.status'   # <- extract value
```

## Reusable helper function

```bash
mcd() {
  mkdir -pv "$1" && cd "$1"
}
```
