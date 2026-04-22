# Username and Hostname
```powershell
whoami
```
# Privileges of the current user
```batch
whoami /priv
```
# Group memberships of the current user
```powershell
whoami /groups
```
# Existing users and groups
## Enumerating Users
```batch
net user $USER
```

```powershell
Get-LocalUser
```

### Enumerating Groups
```batch
net localgroup
```

```powershell
Get-LocalGroup
```

```powershell
Get-LocalGroupMember $GROUP
```
# Operating system, version and architecture
## System Information
```batch
systeminfo
```

```powershell
Get-CimInstance -Class win32_quickfixengineering | Where-Object { $_.Description -eq "Security Update" }
```
# Network Information
```batch
ipconfig /all
```

```batch
route print
```

```batch
netstat -ano
```
# Installed Applications and Running Services
```powershell
Get-ItemProperty "HKLM:\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\*" | select displayname
```

```powershell
Get-ItemProperty "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\*" | select displayname
```

```batch
dir "C:\Program Files"
```

```batch
dir "C:\Program Files (x86)"
```

```batch
dir $env:userprofile\Downloads
```

```powershell
Get-Process
```
## Enumerate filesystem for sensitive details
Enumerate for password manager databases (i.e. .kbdx):
```powershell
Get-ChildItem -Path C:\ -Include *.kdbx -File -Recurse -ErrorAction SilentlyContinue
```
Enumerate application filesystem for interesting files (i.e. XAMPP):
```powershell
Get-ChildItem -Path C:\xampp -Include *.txt,*.ini -File -Recurse -ErrorAction SilentlyContinue
```
Enumerate home directory for interesting files:
```powershell
Get-ChildItem -Path $env:userprofile -Include *.txt,*.pdf,*.xls,*.doc,*.docx,*.ini -File -Recurse -ErrorAction SilentlyContinue
```
Also check other paths such as C:\, C:\Users.
# Powershell Logs
```powershell
Get-History
```

```powershell
(Get-PSReadlineOption).HistorySavePath
```
## View Script Block Logging
1. Open Event Viewer.
2. Windows Logs > Applications and Services Logs > Microsoft > Windows > PowerShell > Operational
3. On the right hand pane, select the following:

![image](https://github.com/user-attachments/assets/8d95086d-93d9-4e9e-9142-ff8b1c7be51d)

5. Add 4104 as the Event ID to filter:

![image](https://github.com/user-attachments/assets/dabce7a7-d406-47c3-9c02-2c57c0e481ad)

6. Look for interesting commands or plaintext creds... For example:

![image](https://github.com/user-attachments/assets/73336dbe-c73d-4831-a160-d808aab7db65)
# No GUI?
If a compromised user isn't part of "Remote Desktop Users" or "Remote Management Users", this means RDP access can't be gained as that user.

Instead, use runas on an account with GUI access to run a cmd or powershell:
```powershell
runas /user:$USER cmd
```
