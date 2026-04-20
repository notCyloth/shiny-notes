# Checklist
- [ ] Nmap SMB Script Scan
- [ ] nbtscan
- [ ] Enumerating off Windows (Living off the Land)
- [ ] Look for SMB Version
- [ ] enum4linux
- [ ] smbclient
## Nmap SMB Script Scan
`nmap -v -p 139,445 -oG smb.txt $IP_RANGE
`grep open smb.txt | cut -d " " -f 2`
`nmap -v -p 139,445 --script smb-os-discovery $IP_ADDRESS`
## nbtscan
`sudo nbtscan -r $IP_ADDRESS/24` e.g. 192.168.50.0/24
## Enumerating off Windows (Living off the Land)
net view lists domains, resources and computers belonging to a given host.
Example listing all shares running on dc01:
``