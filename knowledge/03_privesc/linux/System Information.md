Just use this: 
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md
# Operating system, version and architecture
```bash
sudo --version
```

```bash
cat /etc/issue
```

```bash
cat /etc/os-release
```

```bash
uname -r
```

List loaded kernel drivers:
```bash
lsmod
```

Display kernel driver info:
```bash
/sbin/modinfo $(KERNEL_NAME)
```
# Current User Groups
```bash
id
```
# Services
```bash
ps aux
```

```bash
watch -n 1 "ps -aux | grep pass"
```
# Users
```bash
cat /home
```

```bash
cat /etc/passwd
```
# History
```bash
cat ~/.bash_history
```
# List Sudo Permissions
```bash
sudo -l
```
# Environment Variables
```bash
env
```

```bash
cat .bashrc
```
## Network Information
```bash
ip a
```

```bash
route
```
Or
```bash
routel
```
...depending on distro.

```bash
ss -anp
```

```bash
sudo tcpdump -i $(INTERFACE) -A | grep "pass"
```
### Firewall Rules
```bash
ls /etc/iptables
```

```bash
ls /etc | grep "ip"
```
## Enumerate installed packages
Debian:
```bash
dpkg -l
```
## Every writeable directory by current user
```bash
find / -writable -type d 2>/dev/null
```
## List mounted filesystems
List drives that will be mounted on boot:
```bash
cat /etc/fstab
```
List all mounted filesystems:
```bash
mount
```
List all available disks:
```bash
lsblk
```
