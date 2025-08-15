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
#### Install oh-my-posh
Go to [ohmyposh](https://ohmyposh.dev/) and download the latest version for Windows.

### Install PSReadLine
```powershell
Install-Module -Name PSReadLine -Repository PSGallery
```
### Install Terminal-Icons
```powershell
Install-Module -Name Terminal-Icons
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