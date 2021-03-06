# git-modus-operandi
What I've found to be common, best-practice approaches to development with git...


### Getting (re)started

Clone repo:

    $ git clone https://github.com/<username>/<reponame>.git

Update local branch from remote repo (usually "origin"):

    $ git pull origin <branch>

... or

    $ git fetch
    $ git merge origin/<branch>

Discard changes in your working copy since the latest commit:

    $ git reset --hard
    
Discard changes in your working copy and the latest commit:
    
    $ git reset --hard HEAD~1

Reset your working copy to match the head of its remote branch:
    
    $ git fetch origin
    $ git reset --hard origin/<branch>


### Feature branching

Create a local feature branch:

    $ git checkout -b <feature-branch> <branch>

Switch to / work on / checkout branch:

    $ git checkout <branch>

Save local feature branch to remote repo (usually "origin"):

    $ git push origin <feature-branch>

Save changes made to feature branch:

    $ git add --all
    $ git commit -m '<message>'
    $ git push origin <feature-branch>

Update feature branch with any recent commits on the base branch (usually "develop"):

    $ git checkout <feature-branch>
    $ git rebase develop

Incorporate feature into develop branch:

    $ git checkout develop
    $ git merge --no-ff <feature-branch>
    $ git push origin develop

Delete local and remote feature branches:

    $ git branch -d <feature-branch>
    $ git push origin --delete <feature-branch>


### Release branching

Create and save release branch for final tweaks/testing:

    $ git checkout -b <release-X.X.X> develop
    $ git push origin <release-X.X.X>
    
When production ready, incorporate it into master branch, and tag it:

    $ git checkout master
    $ git merge --no-ff <release-X.X.X>
    $ git tag -a <vX.X.X> -m 'release version X.X.X'
    $ git push origin master
    $ git push origin <vX.X.X>
    
Incorporate final release back into develop, and delete its branch:

    $ git checkout develop
    $ git merge --no-ff <release-X.X.X>
    $ git branch -d <release-X.X.X>
    $ git push origin --delete <release-x.x.x>
    

### Hotfix branching

Create and save a new branch to make the fixes on:

    $ git checkout -b <hotfix-X.X.Z> master
    $ git push origin <hotfix-X.X.Z>
    
When production ready, incorporate it into master branch, and tag it:

    $ git checkout master
    $ git merge --no-ff <hotfix-X.X.Z>
    $ git tag -a <vX.X.Z> -m 'hotfix X.X.Z'
    $ git push origin master
    $ git push origin <vX.X.Z>

Incorporate hotfix back into develop, and delete its branch:

    $ git checkout develop
    $ git merge --no-ff <hotfix-X.X.Z>
    $ git branch -d <hotfix-X.X.Z>
    $ git push origin --delete <hotfix-X.X.Z>
    

### Resources

- http://nvie.com/posts/a-successful-git-branching-model/

- https://www.atlassian.com/git/tutorials/

### Author

Nathaniel Reynolds (nathaniel.reynolds@gmail.com)

