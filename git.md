![git badge](./assets/git.png)

~~~
- Software for code version control;
- There are two types of Version Control Software (VCS):
   - Centralized
   - Distributed (e.g., Git)
- Some of the advantages of using VCS include: security and facilitating teamwork.
~~~

### Git Commands
- Check the Git version and see if it's installed:
~~~
   - git --version
~~~

- Configure user and registered email (for the entire machine):
~~~
   - git config --global user.email you@example.com
   - git config --global user.name "Your Name"
~~~
- Verify the configurations:
~~~
   - git config user.name
   - git config user.email
~~~
- Initialize a repository:
~~~
   - git init
~~~
- Check the status:
~~~
   - git status 
~~~
- Add files to the staging area:
~~~
   - git add file_name
   - git add . 
~~~
- Commit files:
~~~
   - git commit -m "comment"
~~~
- Map remote repository:
~~~
   - git remote add origin "http://...remote_rep_url..." 
~~~
- Push changes to the remote repo:
~~~
   - git push -u origin master
   - git push 
~~~
- Update local repo according to remote repo:
~~~
   - git pull
~~~
- Rename branch:
~~~
   - git branch -M main 
~~~
- Clone remote repo:
~~~
   - git clone "http://...remote_rep_url...
~~~
- Removing files:
~~~
   - git rm --> removes from the repository (<mark>DELETES</mark> file)
   - git rm --cached <file> --> file is no longer tracked (untracked)
~~~
- Use Add along with Commit (stage and commit together):
~~~
   - git commit -am "creating commit"
~~~
- Check changes:
~~~
   - git log
   - git log --oneline --> more concise form
~~~
- To ignore files:
~~~
   - Create the ".gitignore" file
   - Files inside ".gitignore" are ignored and not tracked by Git
~~~
- Check differences between commits:
~~~
   - git diff <commit_code> <commit_code2>
~~~
- Discard changes before adding:
~~~
   - git checkout <file>
~~~

- All commands
~~~
# GIT BASICS
- git init <directory>
- git clone <repo>
- git config user.name <name>
- git add <directory>
- git commit -m "<message>"
- git status 
- git log
- git diff

# GIT BRANCHES
- git branch 
- git checkout -b <branch>
- git merge <branch>

# REMOTE REPOSITORIES
- git remote add <name> <url>
- git fetch <remote> <branch>
- git pull <remote>
- git push <remote> <branch>

# UNDOING CHANGES 
- git revert <commit>
- git reset <file>
- git clean -n 

# GIT REBASE
- git rebase -i <base>

# GIT RESET
- git reset
- git reset --hard
- git reset <commit>
- git reset --hard <commit>

# GIT LOG
- git log -<limit>
- git log --oneline
- git log -p
- git log --stat
- git log --author= "<pattern>"
- git log --grep= "<pattern>"
- git log <since>..<until>
- git log <file>
- git log --graph --decorate

# REWRITTING GIT HISTORY
- git commit --amend
- git rebase <base>
- git reflog

# GIT CONFIG
- git config --global user.name <name>
- git config --global user.email <email>
- git config --global alias.<alias-name> <git-command>
- git config --system core.editor <editor>
- git config --global --edit
~~~

### Git Flow

~~~
## Simplified workflow for individual work

1. Create a remote repository on GitHub.
2. Clone the remote repository (Master/main branch).
3. Work/Develop on the project.
4. Add changes to the Staged Area (Git add).
5. Commit the changes (Git commit).
6. Synchronize the remote repository (Git push origin <branchName>).

## Workflow for teamwork

1. Create a remote repository on GitHub.
2. Clone the remote repository (Master/main branch).
3. Create a new branch.
4. Checkout to the new branch.
5. Work/Develop on the project.
6. Git add <file-name>.
7. Git commit.
8. Git push origin <branchName>.
9. Create a pull request (On GitHub).
10. Resolve any conflicts.
11. Merge the worked branch into the Master branch (On GitHub).
12. Delete the worked branch.
~~~

