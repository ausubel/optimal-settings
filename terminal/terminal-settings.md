# PowerShell Setup
## Prerequisites

#### Install oh-my-posh
Go to [ohmyposh](https://ohmyposh.dev/) and download the latest version for Windows.

#### Install PSReadLine
```powershell
Install-Module -Name PSReadLine -Repository PSGallery
```
#### Install Terminal-Icons
```powershell
Install-Module -Name Terminal-Icons
```

## Windows PowerShell Profile
### $PROFILE
Create $PROFILE if not exists:
```powershell
if (!(Test-Path -Path $PROFILE)) {
    New-Item -ItemType File -Path $PROFILE -Force
}
```
Add this to $PROFILE:
```powershell
oh-my-posh init pwsh --config "C:/Users/ausub/AppData/Local/Programs/oh-my-posh/themes/material.omp.json" | Invoke-Expression
Set-PSReadLineOption -PredictionViewStyle ListView
Import-Module Terminal-Icons
cls
```

### Linux Powershell Profile

#### PROFILE:

Create ~/.config/powershell/profile.ps1:
```bash
if (!(Test-Path -Path $PROFILE)) {
    New-Item -ItemType File -Path $PROFILE -Force
}
```

Add this to ~/.config/powershell/profile.ps1:
```powershell
$env:PATH = "$env:HOME/.local/bin:$env:PATH"

oh-my-posh init pwsh --config ~/.mytheme.omp.json | Invoke-Expression

Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView

Set-PSReadLineKeyHandler -Key "RightArrow" -Function AcceptNextSuggestionWord
Set-PSReadLineKeyHandler -Key "F2" -Function AcceptSuggestion

Import-Module Terminal-Icons
Remove-Item Alias:ls -ErrorAction SilentlyContinue
Set-Alias -Name ls -Value Get-ChildItem

Clear-Host
```

### Git config
```powershell
git config --global user.name "ausubel"
git config --global user.email "ausubelvc@gmail.com"
git config --global core.autocrlf true
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h\n%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```


