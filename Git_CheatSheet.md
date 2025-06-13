# Git CheatSheet

## Clone a Repository
```bash
git clone <url>
```

## Credential Management
Add Credentials to GIT
```bash
git config --global credential.helper store
# Username: <Github Username>
# Password: <Github PAT>
```
## Change Management
```bash
# Track all files in the folder
git add -all

# Track just one file in the folder
git add <filename>

# Commit changes with comment (-m)
git commit -m <"Comment">

# Track and commit in the same command
git commit -a -m <"Comment">
```
