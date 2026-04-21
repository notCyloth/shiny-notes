# Checklist
- [ ] Footprint Service
- [ ] Anonymous(?) Login
- [ ] Download all files
- [ ] Upload to web directory
# Footprint Service
```bash
sudo nmap -p 21 -A $IP_ADDRESS
```
# Anonymous(?) Login
```bash
ftp $IP_ADDRESS
```
# Download all files
```bash
wget -m —no-passive ftp://user:password@targetip
```
