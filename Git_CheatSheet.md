# Git CheatSheet

* Set up folder as a git managed folder  
    ```bash
    git init
    ```

## Change Management
* Managing files and commits  
    ```bash                                                                                                                                                                                      # Track all files in the folder                                                                                                                                                              git add -all
    # Track just one file in the folder
    git add <filename>
    # Commit changes with comment (-m)
    git commit -m <"Comment">
    # Track and commit in the same command
    git commit -a -m <"Comment">                                                                                                                                                                 ```
## Reverting Changes
* Soft Reset  
| go back to a previous commit, but keep all of your changes staged. (Committed changes will be uncommitted and staged, uncommitted changes will remain staged or unstaged)
    ```bash
    git reset --soft <commithash> # commit hash is the hash of the commit you want to rever too
    ```
* Hard Reset  
| Useful if you just won't to go back to a previous commit and lose all your changes
    ```bash
    git reset --hard <commithash>
    ```
## Repository Management                                                                                                                                                                     
* Clone a repository
    ```bash                                                                                                                                                                                  
    git clone <url>
    ```
* Adding a remote repository
    ```bash
    git remote add <name> <url>
    ```
* Fetch the bookkeeping info from the remote repo  
| This does not bring down all of the files, just commit info
    ```bash
    git fetch
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
* View log of remote repo
    ```bash
    git log remote/branch
    # Example: git log origin/prime
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
* Rename a branch
    ```bash
    git branch -m oldname newname
    ```
* Merge Branch
    ```bash
    git merge <branch name>
    ```
* Merge Remote Branch
    ```bash
    git merge remote/branch
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

## Credential Management                                                                                                                                                                     
Add Credentials to GIT                                                                                                                                                                       
```bash                                                                                                                                                                                      
git config --global credential.helper store                                                                                                                                                  
# Username: <Github Username>                                                                                                                                                                
# Password: <Github PAT>                                                                                                                                                                     
```


## Prime's Workflow
### Keep stuff on GitHub  

I keep all my serious projects on GitHub. That way if my computer explodes, I have a backup, and if I'm ever on another computer, I can just clone the repo and get back to work.  

### Rebase vs. Merge  

    I've configured Git to rebase by default on pull, rather than merge so I keep a linear history. If you want to do the same, you can add this to your global Git config:  

    ```bash
    git config --global pull.rebase true
    ```
### Solo Workflow  

    When I'm working by myself, I usually stick to a single branch, main. I mostly use Git on solo projects to keep a backup remotely and to keep a history of my changes. I only rarely use separate branches.  

        1. Make changes to files  
        2. `git add .` (or `git add <files>` if I only want to add specific files)  
        3. `git commit -m "a message describing the changes"`  
        4. `git push origin main`    

### Team Workflow  

    When you're working with a team, Git gets a bit more involved (and we'll cover more of this in part 2 of this course). Here's what I do:When you're working with a team, Git gets a bit more involved (and we'll cover more of this in part 2 of this course).  
    Here's what I do:   
    
        - Update my local main branch with `git pull origin main`  
        - Checkout a new branch for the changes I want to make with `git switch -c <branchname>`  
        - Make changes to files  
        - `git add .`   
        - `git commit -m "a message describing the changes"`  
        - `git push origin <branchname>`(I push to the new branch name, not main)   
        - Open a pull request on GitHub to merge my changes into main  
        - Ask a team member to review my pull request  
        - Once approved, click the "Merge" button on GitHub to merge my changes into main  
        - Delete my feature branch, and repeat with a new branch for the next set of changes  
