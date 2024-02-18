### Description
This file contains PowerShell commands for managing user accounts.

### Create new user account
```ps1
New-ADUser -Name "John Doe" -SamAccountName "jdoe" -AccountPassword (ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force) -Enabled $true
```

### Disable user account
```ps1
Disable-ADAccount -Identity "jdoe"
```


### Enable user account
```ps1
Enable-ADAccount -Identity "jdoe"
```


### Reset user password
```ps1
Set-ADAccountPassword -Identity "jdoe" -Reset -NewPassword (ConvertTo-SecureString "NewP@ssw0rd" -AsPlainText -Force)
```

