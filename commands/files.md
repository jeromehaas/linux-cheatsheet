# Files

## Create

```bash
touch hello-world.txt                # <- create empty file
mkdir work-stuff                     # <- create directory
mkdir private-stuff relation-stuff   # <- create multiple directories
mkdir -p ~/projects/top-secret       # <- create nested directories
```

## View

```bash
cat /etc/hosts              # <- print file content
less file.txt               # <- open scrollable view
head -n 20 file.txt         # <- first 20 lines
tail -n 50 file.txt         # <- last 50 lines
tail -f app.log             # <- follow log file
```

## Copy / move / delete

```bash
cp src.txt dst.txt          # <- copy file
cp -a src_dir/ dst_dir/     # <- copy directory and metadata
mv projects playground      # <- rename / move
rm file.txt                 # <- remove file
rm -r directory/            # <- remove directory recursively
rm -rf directory/           # <- force recursive delete
```

## Rename patterns

```bash
rename .css .scss *         # <- rename extension (if rename exists)
```

## Backups

```bash
cp my_config{,.bak}                    # <- create backup file
cp my_config "my_config.$(date +%F)"   # <- backup with date
```

## Symlinks and hard links

```bash
ln my-file.txt hard-link.txt       # <- hard link
ln -s my-file.txt symlink.txt      # <- symbolic link
```

## File sizes

```bash
find ~/ -size +100M                # <- files bigger than 100 MB
find ~/ -size +100M 2>/dev/null    # <- ignore permission errors
du -sh .                           # <- size of current directory
du -h --max-depth=1 . | sort -h    # <- folder sizes
```

## Hashes and compare

```bash
sha256sum file.iso         # <- checksum on Linux
shasum -a 256 file.iso     # <- checksum on macOS
diff -u a.txt b.txt        # <- unified diff
cmp a.bin b.bin            # <- byte-by-byte compare
```

## Brace expansion

```bash
touch file-{1..10}.txt                         # <- create file-1.txt up to file-10.txt
mkdir project-{a,b,c}                          # <- create project-a, project-b, and project-c
mkdir -p app/{src,tests,docs}                  # <- create common project subdirectories at once

touch {index,about,contact}.html               # <- create multiple named files in one command
cp .env{,.bak}                                 # <- create a quick backup file like .env.bak
mv access.log{,.old}                           # <- rename access.log to access.log.old

mkdir -pv /hosts/www.{prototype,production,staging}.ch/{www,html}   # <- create three site directories, each with www and html inside
touch image-{01..05}.png                       # <- create numbered files with leading zeros
echo src/{components,pages,utils}              # <- preview the expanded paths without creating them