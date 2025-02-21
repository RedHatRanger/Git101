# Git101 Labs

Welcome to the Git101 practice labs! Here’s how the repository is organized:

- **/labs**: Contains all the practice labs. Each lab folder is numbered and named according to its topic.

Start with [01-introduction](labs/01-introduction/README.md) to begin your journey!

## To make git to show your current branch in `Linux`, add this to your ~/.bashrc:
```bash
source /usr/share/git-core/contrib/completion/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=true
export GIT_PS1_SHOWUNTRACKEDFILES=true
export PS1='[\u@\h \W$(declare -F __git_ps1 &>/dev/null && __git_ps1 " (%s)")]\$ '
```

## To make git to show your current branch in `Windows`:
1. Copy the text below to Notepad.
2. Name the file `.\setup-posh-git.ps1` or something similar.
3. Right-click and `Run As Administrator`.
```
# Show Git Branch Names in PowerShell with Posh-Git

# Step 1: Set Execution Policy for Current User (Requires Admin Privileges)
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser -Force

# Step 2: Install Posh-Git (Requires Internet Connection)
Install-Module posh-git -Scope CurrentUser -Force

# Step 3: Ensure the PowerShell Profile Exists
if (!(Test-Path $PROFILE)) {
    New-Item -ItemType File -Path $PROFILE -Force
}

# Step 4: Add Posh-Git to PowerShell Profile (if not already added)
$profileContent = Get-Content $PROFILE -Raw
if ($profileContent -notmatch "Import-Module posh-git") {
    Add-Content -Path $PROFILE -Value "`nImport-Module posh-git`n"
}

# Step 5: Reload the PowerShell Profile
. $PROFILE

Write-Host "Posh-Git installation complete! Restart PowerShell to see Git branch names in your prompt." -ForegroundColor Green
```
