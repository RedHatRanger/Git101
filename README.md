# 🚀 Git101: Let's Get Started with Git! (5th Grader Edition)

Hey there, future Git expert! Welcome to **Git101 Labs**, where you'll learn how to use Git and have fun while doing it! 🎉

## What's Inside?
Inside this Git101 repository, you'll find:
- **/labs**: This is where all the practice labs live. Each lab is numbered and focuses on a cool Git skill.
- Start with [Lab 1 - Git Setup and Basic Workflows](labs/01_git_setup_and_basic_workflows.md) to begin your Git adventure!

---

<br><br><br><br>
## 🐧 Make Git Show Your Branch in Linux
![image](https://github.com/user-attachments/assets/52e80ee4-c539-4771-b629-5380a6158342)

Want to see what Git branch you're on every time you use the terminal? Add this magic spell to your `~/.bashrc`:

### For RHEL, Fedora, Rocky, Centos Varieties
```bash
source /usr/share/git-core/contrib/completion/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=true
export GIT_PS1_SHOWUNTRACKEDFILES=true
export PS1='[\u@\h \W$(declare -F __git_ps1 &>/dev/null && __git_ps1 " (%s)")]\$ '
```

Then run:
```bash
source ~/.bashrc
```
Now, your terminal will always tell you what Git branch you're on! 🌟

<br>

### For Debian, Ubuntu, Arch, etc. Varieties
```bash
curl -o ~/.git-prompt.sh https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
```

Then add this to your `~/.bashrc`
```
source ~/.git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=true
export GIT_PS1_SHOWUNTRACKEDFILES=true
export PS1='[\u@\h \W$(declare -F __git_ps1 &>/dev/null && __git_ps1 " (%s)")]\$ '
```

Then run:
```bash
source ~/.bashrc
```
Now, your terminal will always tell you what Git branch you're on! 🌟

---

<br><br>
## 🖥️ Make Git Show Your Branch in Windows 
![image](https://github.com/user-attachments/assets/cd8731e9-41c0-40a1-a8c6-1501fe091d55)

Want your **PowerShell** to tell you what branch you're on? Follow these steps:

1️⃣ Open Notepad 📝 \
2️⃣ Copy and paste the text below into Notepad. \
3️⃣ Save it as `setup-posh-git.ps1` or something cool. \
4️⃣ **Right-click and Run As Administrator!**

```powershell
# 🚀 Show Git Branch Names in PowerShell with Posh-Git

# Step 1: Set Execution Policy (Needs Admin Privileges)
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser -Force

# Step 2: Install Posh-Git (Requires Internet Connection)
Install-Module posh-git -Scope CurrentUser -Force

# Step 3: Ensure PowerShell Profile Exists
if (!(Test-Path $PROFILE)) {
    New-Item -ItemType File -Path $PROFILE -Force
}

# Step 4: Add Posh-Git to PowerShell Profile
$profileContent = Get-Content $PROFILE -Raw
if ($profileContent -notmatch "Import-Module posh-git") {
    Add-Content -Path $PROFILE -Value "`nImport-Module posh-git`n"
}

# Step 5: Reload the PowerShell Profile
. $PROFILE

Write-Host "🎉 Posh-Git is installed! Restart PowerShell to see Git branch names in your prompt." -ForegroundColor Green
```

Now, every time you open PowerShell, you'll see your Git branch right in the prompt! 🚀✨

Time to start coding like a Git pro! 🏆

<br><br>
**Next:** [Lab 1 - Git Setup and Basic Workflows](labs/01_git_setup_and_basic_workflows.md)
