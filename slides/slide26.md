## 6.4 Git Branches

![git Log](images/git-branches.png)
######Git Branches

- One way to view your git commit history is as a list of linear nodes on a master branch. Where each node represents a successful change (commit) to your code base.
- Often you want to add a new feature to your app but want to retain the integrity of the master branch. We do this by branching off from the master branch, adding the new feature and then merging back in.
- To create a branch - `$git checkout -b <branch name>`
- To merge your branch back into master:
    - first checkout master - `$git checkout master`
    - then merge your branch into the master branch - `$git merge <branch name>`
