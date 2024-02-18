### Description
This file contains PowerShell commands for managing event logs.

### Get event logs
```ps1
Get-WinEvent -LogName "Application" -MaxEvents 100 | Export-Csv -Path "C:\ApplicationEvents.csv" -NoTypeInformation
```
