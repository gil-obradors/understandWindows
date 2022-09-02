# Windows Tricks and tests



## Add ssh capability to Windows
```
Get-WindowsCapability -Online | ? Name -like 'OpenSSH*'
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0
```

```
Start-Service sshd
Get-Service sshd
Set-Service -Name sshd -StartupType 'Automatic'
```

## Change passwords
```
net user USERNAME NEWPASS
net user /domain USERNAME NEWPASS

Set-ADAccountPassword -Identity $user -Reset -NewPassword (ConvertTo-SecureString -AsPlainText "$newPass" -Force)



```
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```
