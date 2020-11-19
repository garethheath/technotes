# Change keyboard layout

```powershell
$UserLanguageList = New-WinUserLanguageList -Language en-US
Set-WinUserLanguageList -LanguageList $UserLanguageList
```