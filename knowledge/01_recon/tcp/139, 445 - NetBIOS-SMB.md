# Checklist
- [ ] Nmap SMB Script Scan
- [ ] nbtscan
- [ ] Enumerating off Windows (Living off the Land)
- [ ] Look for SMB Version
- [ ] enum4linux
- [ ] smbclient
- [ ] rpcclient
## Nmap SMB Script Scan
```bash
nmap -v -p 139,445 -oG smb.txt $IP_RANGE
```
```bash
grep open smb.txt | cut -d " " -f 2
```
```bash
nmap -v -p 139,445 --script smb-os-discovery $IP_ADDRESS
```
## nbtscan
```bash
sudo nbtscan -r $IP_ADDRESS/24 
```
e.g. 192.168.50.0/24
## Enumerating off Windows (Living off the Land)
net view lists domains, resources and computers belonging to a given host.
Example listing all shares running on dc01:
```cmd
net view \\dc01 /all
```
## Look for SMB Version
```
msfconsole
```

```
use auxiliary/scanner/smb/smb_version
```
## enum4linux
This will apply all enumeration options:
```bash
enum4linux-ng -a $IP_ADDRESS -oA output
```
How to loop enum4linux for multiple IP's...
```bash
for ip in $(cat smb_hosts.txt); do enum4linux -a $ip; done
```
# How to Connect
## smbclient
This will attempt to list shares with anonymous access. If prompted for a root password, just enter nothing:
```bash
smbclient -L \\\\$IP_ADDRESS\\
```
List specific shares content:
```
smbclient -L \\\\$IP_ADDRESS\\share
```
## rpcclient
```bash
rpcclient -U "" -N $IP_ADDRESS
```