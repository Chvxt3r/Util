# Sharepoint Snippets

## Connect to sharepoint online
```powershell
Connect-SPOService -Credential $creds -Url https://<tenant>-admin.sharepoint.com -ModernAuth $true -AuthenticationUrl https://login.microsoftonline.com/organizations
```

## OneDrive

### List all recoverable onedrive folders
```powershell
Get-SPODeletedSite -IncludeOnlyPersonalSite | FT url
```

### Recover the onedrive to an active state
```powershell
Restore-SPODeletedSite -Identity <URL>
```

### Assign an administrator to review
```powershell
Set-SPOUser -Site <URL> -LoginName <UPNofDesiredAdmin> -IsSiteCollectionAdmin $True
```

### Access
Files can now be accessed by using the URL of the onedrive site.

### Permanently delete a users OneDrive
```powershell
Remove-SPOSite -Identity <URL>
Remove-SPODeletedSite -Identity <URL>
```
