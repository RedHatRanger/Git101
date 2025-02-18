# Git101 Labs

Welcome to the Git101 practice labs! Here’s how the repository is organized:

- **/labs**: Contains all the practice labs. Each lab folder is numbered and named according to its topic.
- **/solutions** (optional): Contains solutions to the labs (if provided).

Start with [01-introduction](labs/01-introduction/README.md) to begin your journey!

## To get the git bash prompt, add this to your ~/.bashrc:
```bash
source /usr/share/git-core/contrib/completion/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=true
export GIT_PS1_SHOWUNTRACKEDFILES=true
export PS1='[\u@\h \W$(declare -F __git_ps1 &>/dev/null && __git_ps1 " (%s)")]\$ '
```
