# git cheat sheet

**deleting branches**
``` bash
# delete local branch
git branch -d branch_name
# delete remote branch
git push --delete origin branch_name
```
**switching branches**
``` bash
# create a local branch
git checkout -b branch_name
# create a local branch from a remote branch
git checkout --track origin/branch_name
```
**git push**
``` bash
# push local branch to remote repository
git push -u origin branch_name
```
