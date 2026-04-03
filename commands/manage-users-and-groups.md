# Manage users and groups

## Who am I?

```bash
whoami                  # <- current user
id                      # <- uid, gid, groups
groups                  # <- group names
```

## Switch user

```bash
su - deployer           # <- login shell as deployer
su -l deployer          # <- same idea
su --login deployer     # <- same idea
sudo -i                 # <- root login shell via sudo
sudo vim /etc/hosts     # <- run one command as root
```

## Create users

```bash
sudo adduser devops                              # <- friendly Debian/Ubuntu helper
sudo useradd -m -s /bin/bash devops              # <- lower-level user creation
sudo useradd -G devs,pipeline,cto devops         # <- add supplementary groups
sudo useradd -s /sbin/nologin patricia_mueller   # <- no interactive shell
```

## Passwords

```bash
sudo passwd devops             # <- set password
passwd                         # <- change your own password
passwd -S devops               # <- password status
chage -l operator1             # <- password ageing info
chage -M 15 user1              # <- expire password in 15 days
date -d "+180 days" +%F        # <- calculate expiry date
chage -E 2026-09-10 devops     # <- set account expiry date
chage -d 0 devops              # <- force password change at next login
grep PASS_ /etc/login.defs     # <- default password policy values
```

## Groups

```bash
sudo groupadd group01              # <- create group
sudo groupadd -g 10000 group01     # <- create group with fixed gid
getent group                       # <- list groups
getent group devs                  # <- inspect one group
sudo groupdel group01              # <- delete group
```

## Add users to groups

```bash
sudo usermod -aG devs user1            # <- append user to supplementary group
sudo usermod -g wheel deployer         # <- change primary group
sudo usermod -G wheel deployer         # <- replace supplementary groups
sudo usermod -c "deployer" deployer    # <- change comment field
```

## Delete / lock users

```bash
sudo userdel devops           # <- delete user
sudo userdel -r devops        # <- delete user and home directory
sudo usermod -L devops        # <- lock user
sudo usermod -U devops        # <- unlock user
```

## Where account data lives

```bash
/etc/passwd  # <- user account info
/etc/group   # <- group info
/etc/shadow  # <- password hashes and ageing info
```

## Sudo groups

```bash
sudo usermod -aG sudo <USER>   # <- Debian/Ubuntu
sudo usermod -aG wheel <USER>  # <- Fedora/Arch/RHEL common pattern
sudo visudo                    # <- edit sudoers safely
```
