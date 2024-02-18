### Description: 
This file contains PowerShell commands for managing servers.

### Get server information
```ps1
Get-WmiObject Win32_OperatingSystem
```

### Restart server
```ps1
Restart-Computer -ComputerName "ServerName" -Force
```
