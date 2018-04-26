![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/Gnu-bash-logo.svg/2000px-Gnu-bash-logo.svg.png)
---

### [rebase](https://github.com/gjstoychev/Bash/blob/master/rebase)
The purpose of this script is to fetch data from github and rebase the repository.

**Requirements**:
The only configuration requirement is the repository variable that needs to be set on [line 3](https://github.com/gjstoychev/Bash/blob/master/rebase):
```
repo="clouway/tgps" # SET YOUR REPOSITORY HERE
```


**Conditions**
The script will exit if one of the following occurs:

* Current directory is not a git repository
```
Error: /home/g is not a git repository. Please, run me in your project folder.
```

* There are local changes to the repository
```
On branch test | upstream: upstream

Error: Local changes detected! Please, stash them before rebasing.
```

* Repository not properly configured (line 3)
```
Error: clouway/tgps not found! Please, add a correct repository and try again.
```


**Usage**
This is a Linux script that can also be used as a command this way:

* Copy/paste the [source code](https://github.com/gjstoychev/Bash/blob/master/rebase) into a file called `rebase` or [download zip](https://github.com/gjstoychev/Bash/archive/master.zip)
* Enter the directory where you just saved the file and make it executable:
```
sudo chmod +x rebase
```
* Add it to /usr/local/bin so you can execute it anytime anywhere:
```
sudo mv rebase /usr/local/bin/
```
* Start using the script:
```
rebase

On branch test | upstream: upstream
----------------------------------------------------------------
g@batman /home/.../frontend $ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

----------------------------------------------------------------
g@batman /home/.../frontend $ git fetch upstream

----------------------------------------------------------------
g@batman /home/.../frontend $ git rebase upstream/master
Current branch master is up to date.

----------------------------------------------------------------
g@batman /home/.../frontend $ git checkout test
Switched to branch 'test'
Your branch is up-to-date with 'upstream/master'.

----------------------------------------------------------------
g@batman /home/.../frontend $ git rebase master
Current branch test is up to date.

```

---