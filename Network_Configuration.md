### Description
This file contains PowerShell commands for configuring networks.

### Set IP address
```ps1
New-NetIPAddress -InterfaceAlias "Ethernet" -IPAddress "192.168.1.100" -PrefixLength 24 -DefaultGateway "192.168.1.1"
```

### Check network connectivity
```ps1
Test-NetConnection -ComputerName "example.com"
```
