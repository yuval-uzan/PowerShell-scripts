### Description
This file contains PowerShell commands for managing Active Directory.

### Get user information3
```ps1
Get-ADUser -Filter * | Export-Csv -Path "C:\ADUsers.csv" -NoTypeInformation
```

### Add user to group
```ps1
Add-ADGroupMember -Identity "GroupName" -Members "jdoe"
```

### Find inactive users
```ps1
Search-ADAccount -AccountInactive -TimeSpan "90.00:00:00" | Where-Object { $_.ObjectClass -eq 'user' } | Export-Csv -Path "C:\InactiveUsers.csv" -NoTypeInformation
```

