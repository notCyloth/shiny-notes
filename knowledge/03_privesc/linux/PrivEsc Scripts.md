# Linpeas
```bash
wget https://github.com/carlospolop/PEASS-ng/releases/download/2021.02.20/linpeas.sh
```

```bash
chmod +x linpeas.sh
```

```bash
./linpeas.sh
```
# unix-privesc-check
Transfer unix-privesc-check to target machine:
```bash
cp /usr/bin/unix-privesc-check .
```
Run on target machine:
```bash
./unix-privesc-check standard > output.txt
```