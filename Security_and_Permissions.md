### Description: 
This file contains PowerShell commands for managing security and permissions.

### Audit file permissions
```ps1
Get-Acl -Path "C:\Path\To\File.txt" | Format-List
```

### Grant NTFS
 ```ps1
icacls "C:\Path\To\File.txt" /grant Users:(OI)(CI)F
```
