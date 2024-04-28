# active_directory
```ps
Install-WindowsFeature -name AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName int.madao.com -InstallDNS
New-ADOrganizationalUnit -Name "UserAccounts"
New-NetIPAddress -InterfaceIndex 3 -IPaddress 192.168.1.2
$splat = @{
    Name = 'WindowsServer'
    AccountPassword = (Read-Host -AsSecureString 'AccountPassword')
    Enabled = $true
}
New-ADUser @splat
$splat = @{
    Name = 'Alice'
    AccountPassword = (Read-Host -AsSecureString 'AccountPassword')
    Enabled = $true
}
New-ADUser @splat
```

```ps
New-NetIPAddress -InterfaceIndex 2 -IPaddress 192.168.1.3
Set-DnsClientServerAddress -InterfaceIndex 2 -ServerAddress("192.168.1.2")
Add-Computer -DomainName int.madao.com -Restart
```
