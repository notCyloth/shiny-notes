# Checklist
- [ ] Footprint the service
- [ ] Login to the service
# Footprint the service
```bash
sudo nmap -A -p $IP_ADDRESS
```
# Login to the service
```bash
impacket-mssqlclient $USERNAME@$IP_ADRESS -windows-auth
```