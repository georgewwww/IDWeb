# Laborator 1 IDW
### Resolve a conflict between 2 branches
For this we need to have 2 branches with common base(commit), after that we commit some changes at the same part of a file. Using command `git merge <branch_name>` will lead us to a merge conflict, and to resolve it we should edit the file with desired changes, and after that we can use the command `git rebase --continue` and commit the following merge.

### To reset a branch to previous commit
- HARD Method
If we want to totally remove a commit and push it on remote we should use the following commands
~~~bash
git reset --hard HEAD~1
git push --force origin master
~~~

- SOFT Method
If we simply want to remove the commit but the changes to remain instacts we should use the following:
~~~bash
git reset --soft HEAD~1
~~~

### Configure connection to Github via SSH
1. Generating a new SSH key with github email
~~~bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
[Enter][Enter][Enter]
~~~
2. Ensure the ssh-agent is running
~~~bash
eval $(ssh-agent -s)
> Agent pid 11111
~~~
3. Add SSH private key to the ssh-agent
~~~bash
sh-add ~/.ssh/id_rsa
~~~
4. Copy SSH key to clipboard
~~~bash
clip < ~/.ssh/id_rsa.pub
~~~
Open Github *Profile* -> *Settings* -> *SSH and GPG keys* -> *New SSH Key* -> *Insert a name and copied key* -> *Add SSH Key*
5. Testing connection with Github
~~~bash
sh -T git@github.com
yes
~~~
You're done, now you can push to remote!