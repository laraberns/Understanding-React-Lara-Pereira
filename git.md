## Git

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
