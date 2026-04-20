# Checklist
- [ ] DNS Zone Transfer (AXFR)
- [ ] DNS Recon (Subdomain Enumeration)
## DNS Zone Transfer (AXFR)
```bash
dig @<$DNS_SERVER> $DOMAIN_NAME axfr
```
## DNS Recon (Subdomain Enumeration)
```bash
dnsrecon -d $DOMAIN_NAME
```