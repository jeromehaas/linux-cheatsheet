# Filesystem layout

## Important directories

```bash
ls /                     # <- top-level directories
ls /home                 # <- user home directories
ls /root                 # <- root user's home
ls /etc                  # <- system configuration
ls /var                  # <- variable data: logs, caches, DBs
ls /usr                  # <- userland programs and shared data
ls /tmp                  # <- temporary files
ls /var/tmp              # <- temp files kept longer
ls /boot                 # <- boot files
ls /dev                  # <- device files
ls /opt                  # <- optional third-party software
ls /srv                  # <- service data
```

## Quick meanings

```text
/etc   <- system configuration
/bin   <- user binaries / executable commands
/sbin  <- system administration binaries
/home  <- home directories for users
/tmp   <- temporary files
/var   <- logs, cache, databases, spool
/usr   <- user system resources
/dev   <- hardware / device access files
/boot  <- bootloader and kernel files
```

## Navigation

```bash
pwd                     # <- show current directory
ls -la                  # <- list all files with details
cd /etc                 # <- go to a specific directory
cd ..                   # <- one level up
cd ~                    # <- current user's home
cd -                    # <- previous directory
```

## Useful filesystem checks

```bash
tree -L 3 /             # <- show directory tree 3 levels deep
ls -ld /data            # <- show directory itself, not contents
df -h                   # <- disk usage by filesystem
du -h --max-depth=1 .   # <- folder sizes in current directory
```

## Links

```bash
touch my-file.txt
ln my-file.txt hard-link.txt     # <- create hard link
ln -s my-file.txt sym-link.txt   # <- create symbolic link
readlink -f sym-link.txt         # <- resolve symlink target
```

## Wildcards and brace expansion

```bash
ls a*                   # <- names starting with a
ls *a*                  # <- names containing a
ls [ac]*                # <- names starting with a or c
ls ????                 # <- names with exactly 4 characters

echo {Sunday,Monday,Tuesday}.log    # <- brace expansion
echo file{2..4}.log                 # <- file2.log file3.log file4.log
touch file-{1..10}.txt              # <- create multiple files
mkdir project-{a,b,c}               # <- create multiple directories
cp my_config{,.bak}                 # <- quick backup copy
```

## Find by name

```bash
find . -maxdepth 3 -iname "*docker*"  # <- search nearby
locate docker-compose.yml             # <- very fast if locate DB exists
```
