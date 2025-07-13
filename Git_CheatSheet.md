# Git CheatSheet

## Clone a Repository
```bash
git clone <url>
```
## Reverting Changes
* Soft Reset
| go back to a previous commit, but keep all of your changes staged. (Committed changes will be uncommitted and staged, uncommitted changes will remain staged or unstaged)
```bash
git reset --soft <commithash> # commit hash is the hash of the commit you want to rever too
```
* Hard Reset
:
## Credential Management
Add Credentials to GIT
```bash
git config --global credential.helper store
# Username: <Github Username>
# Password: <Github PAT>
```
## History
* View the git Log (History of commits)
```bash
git log
# --decorate=full Shows the full ref name
# --decorate=no - Hides the branch names
# --online - Shows only one line of the log
```
* View a graphical log
```bash
git log --oneline --graph --all
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

## Branch Management
* New Branch
```bash
# Create a new branch but don't switch to it
git branch my_new_branch
```
```bash
# Create a new branch and switch to it (-c flag creates the new branch)
git switch -c my_new_branch
```
```bash
# Old alternative to git switch
git checkout
```
* Merge Branch
```bash
git merge <branch name>
```
* Delete a branch
| *warning* Make sure you've merged that branch or otherwise don't need any of the changes
```bash
git branch -d <branch name>
```
* Rebase
| Brings the contents of main into working branch.
```bash
# While on the branch
git rebase main
```
```bash
# Current commit history

A - B - C    main
   \
    D - E    feature_branch

# Commit history after a rebase

A - B - C         main
         \
          D - E   feature_branch
```
## Config
* Rename a branch
```bash
git branch -m oldname newname
```

