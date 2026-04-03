# Customization: allow specific IPs

## UFW examples

```bash
sudo ufw status
sudo ufw allow proto tcp from <YOUR_IP>/32 to any port 22       # <- allow one IP
sudo ufw allow proto tcp from <YOUR_SUBNET>/24 to any port 22   # <- allow one subnet
sudo ufw deny 22/tcp                                            # <- deny everyone else
sudo ufw enable                                                 # <- enable the firewall
sudo ufw status numbered                                        # <- show current firewall rules with rule numbers
```

## sshd_config examples

```bash
sudo sshd -t     # <- validate config syntax
```

```text
# /etc/ssh/sshd_config

AllowUsers <USER>@<YOUR_IP>

Match Address <YOUR_IP>/32
  AllowUsers <USER>
```

## Reload SSH daemon

```bash
sudo systemctl reload ssh    # <- Debian/Ubuntu common name
sudo systemctl reload sshd   # <- Fedora/RHEL/Arch common name
ssh <USER>@<HOST>            # <- test from another terminal first
```
