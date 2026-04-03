# Workflow: Compare changes

## Compare two files

```bash
diff -u old.txt new.txt          # <- unified diff
diff -w -u old.txt new.txt       # <- ignore whitespace
cmp a.bin b.bin                  # <- byte-by-byte compare
```

## Compare two directories

```bash
diff -ruN dir_old/ dir_new/      # <- recursive diff
```

## Preview what rsync would change

```bash
rsync -avzn --delete --itemize-changes dir_old/ dir_new/   # <- dry-run sync diff
```
