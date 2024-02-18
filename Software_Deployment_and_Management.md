### Description: 
This file contains PowerShell commands for deploying and managing software.

### Install software
```ps1
Start-Process -FilePath "installer.exe" -ArgumentList "/S" -Wait
```

### Uninstall software
```ps1
Start-Process -FilePath "uninstaller.exe" -ArgumentList "/S" -Wait
```
