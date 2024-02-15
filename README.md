# Windows Update Management
#### Check for updates
```ps1
Get-WindowsUpdate
```
#### Install updates
```ps1
Install-WindowsUpdate -AcceptAll
```
# User Account Management
#### Create new user account
```ps1
New-ADUser -Name "John Doe" -SamAccountName "jdoe" -AccountPassword (ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force) -Enabled $true
```
#### Disable user account
```ps1
Disable-ADAccount -Identity "jdoe"
```
#### Enable user account
```ps1
Enable-ADAccount -Identity "jdoe"
```
#### Reset user password
```ps1
Set-ADAccountPassword -Identity "jdoe" -Reset -NewPassword (ConvertTo-SecureString "NewP@ssw0rd" -AsPlainText -Force)
```
# Group Policy Management
#### Backup GPO
```ps1
Backup-GPO -All -Path "C:\GPOBackups"
```
#### Restore GPO
```ps1
Restore-GPO -All -Path "C:\GPOBackups"
```

#Active Directory Management:
#### Get user information
```ps1
Get-ADUser -Filter * | Export-Csv -Path "C:\ADUsers.csv" -NoTypeInformation
```
#### Add user to group
```ps1
Add-ADGroupMember -Identity "GroupName" -Members "jdoe"
```
#### Find inactive users
```ps1
Search-ADAccount -AccountInactive -TimeSpan "90.00:00:00" | Where-Object { $_.ObjectClass -eq 'user' } | Export-Csv -Path "C:\InactiveUsers.csv" -NoTypeInformation
```
# Server Management:
#### Get server information
```ps1
Get-WmiObject Win32_OperatingSystem
```
#### Restart server
```ps1
Restart-Computer -ComputerName "ServerName" -Force
```
# Software Deployment and Management
#### Install software
```ps1
Start-Process -FilePath "installer.exe" -ArgumentList "/S" -Wait
```
# Uninstall software
```ps1
Start-Process -FilePath "uninstaller.exe" -ArgumentList "/S" -Wait
```
# Network Configuration
#### Set IP address
```ps1
New-NetIPAddress -InterfaceAlias "Ethernet" -IPAddress "192.168.1.100" -PrefixLength 24 -DefaultGateway "192.168.1.1"
```
#### Check network connectivity
```ps1
Test-NetConnection -ComputerName "example.com"
```
# Event Log Management
#### Get event logs
```ps1
Get-WinEvent -LogName "Application" -MaxEvents 100 | Export-Csv -Path "C:\ApplicationEvents.csv" -NoTypeInformation
```
# Disk Management
#### Get disk information
```ps1
Get-WmiObject Win32_LogicalDisk
```
# Check disk space
```ps1
Get-WmiObject Win32_LogicalDisk | Where-Object { $_.DeviceID -eq "C:" } | Select-Object Size, FreeSpace
```
# Service Management
#### Start service
```ps1
Start-Service -Name "ServiceName"
```
#### Stop service
```ps1
Stop-Service -Name "ServiceName"
```
# File and Folder Management
#### Copy files
```ps1
Copy-Item -Path "C:\Source" -Destination "C:\Destination" -Recurse
```
#### Delete folder
```ps1
Remove-Item -Path "C:\FolderToDelete" -Recurse -Force
```
# Security and Permissions 
#### Audit file permissions
```ps1
Get-Acl -Path "C:\Path\To\File.txt" | Format-List
```
#### Grant NTFS permissions
```ps1
icacls "C:\Path\To\File.txt" /grant Users:(OI)(CI)F
```
# Remote Desktop Management
####Connect to remote desktop
```ps1
mstsc.exe /v:ComputerName
```
#### Disconnect session
```ps1
Disconnect-RDUserSession -SessionId 1
```
# Exchange Server Management
##### Get mailbox information
```ps1
Get-Mailbox -ResultSize Unlimited | Export-Csv -Path "C:\Mailboxes.csv" -NoTypeInformation
```

# SQL Server Management
#### Get mailbox information
```ps1
Get-Mailbox -ResultSize Unlimited | Export-Csv -Path "C:\Mailboxes.csv" -NoTypeInformation
```
# VMware or Hyper-V Management
#### Start virtual machine
```ps1
Start-VM -Name "VMName"
```
#### Get VM information
```ps1
Get-VM | Export-Csv -Path "C:\VMs.csv" -NoTypeInformation
```
# Monitoring and Alerting
#### Monitor CPU usage
```ps1
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 10 | Export-Csv -Path "C:\CPUUsage.csv" -NoTypeInformation
```
# Automated Reporting
#### Generate system report
```ps1
Get-WmiObject -Class Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture, LastBootUpTime | Export-Csv -Path "C:\SystemReport.csv" -NoTypeInformation
```
