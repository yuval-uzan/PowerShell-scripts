### Description
This file contains PowerShell commands for managing disks.

### Get disk information
```ps1
Get-WmiObject Win32_LogicalDisk
```

### Check disk space
```ps1
Get-WmiObject Win32_LogicalDisk | Where-Object { $_.DeviceID -eq "C:" } | Select-Object Size, FreeSpace
```
