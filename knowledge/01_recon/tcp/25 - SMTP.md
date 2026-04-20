# Checklist
- [ ] Nmap SMTP Script Scan
- [ ] Metasploit SMTP Enumeration
- [ ] SMTP VRFY Command
## Nmap SMTP Script Scan
`nmap -p 25 --script smtp* $IP_ADDRESS`
## Metasploit SMTP Enumeration
`use auxiliary/scanner/smtp/smtp_version`
`set RHOSTS $IP_ADDRESS`
`run`
## SMTP VRFY Command
`telnet $IP_ADDRESS 25`
`VRFY $EMAIL`