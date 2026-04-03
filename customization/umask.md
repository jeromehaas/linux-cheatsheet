# Customization: umask

## Check current umask

```bash
umask                  # <- numeric form
umask -S               # <- symbolic form
```

## Common values

```text
022 <- new files usually 644, dirs 755
027 <- group read, others no access
077 <- private by default
```

## Set for current shell

```bash
umask 027   # <- set default permissions for new files and directories in the current shell
```

## Persist in shell config

```bash
echo 'umask 027' >> ~/.bashrc   # <- add the umask setting to your Bash config
source ~/.bashrc                # <- reload the Bash config in the current shell
```
