# Checklist
- [ ] Nmap SMTP Script Scan
- [ ] Metasploit SMTP Enumeration
- [ ] SMTP VRFY Command
## Nmap SMTP Script Scan
```
```

## Metasploit SMTP Enumeration
`use auxiliary/scanner/smtp/smtp_version`
`set RHOSTS $IP_ADDRESS`
`run`
## SMTP VRFY Command
`telnet $IP_ADDRESS 25`
`VRFY $EMAIL`