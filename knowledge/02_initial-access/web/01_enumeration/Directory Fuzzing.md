# Checklist
- [ ] feroxbuster
- [ ] ffuf
- [ ] dirbuster
- [ ] dirb
- [ ] gobuster
- [ ] Other wordlists
# Feroxbuster
```bash
feroxbuster -u http://$IP_ADDRESS --silent --output results.txt # optional -w [WORDLIST]
```
# dirbuster
```bash
dirbuster&
```
# ffuf
```bash
ffuf -w /usr/share/seclists/Discovery/Web-Content/big.txt:FUZZ -u http://$IP_ADDRESS:$PORT/FUZZ -recursion -recursion-depth=1 -s
```
# dirb
# gobuster
```bash
gobuster dir -u $IP_ADDRESS -w /usr/share/wordlists/dirb/common.txt -t 5
```
Remember to check for other filetypes (pdf, txt, aspx, php, etc):
```bash
gobuster dir -u $IP_ADDRESS -w /usr/share/wordlists/dirb/common.txt -t 5 -x pdf,txt
```
Also remember to download any files found (exiftool the files to see who made them, are they a user? etc...)!

Other wordlists:
* /usr/share/wfuzz/wordlist/general/megabeast.txt
* /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt