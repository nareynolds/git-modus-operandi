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

Discard changes in working copy since the latest commit:

    $ git reset --hard
    
Discard changes in working copy since and including the latest commit:
    
    $ git reset --hard HEAD~1


### Feature branching

Create a local feature branch:

    $ git checkout -b <feature_branch> <branch>

Switch to / work on / checkout branch:

    $ git checkout <branch>

Save local feature branch to remote repo (usually "origin"):

    $ git push origin <feature_branch>

Save changes made to feature branch:

    $ git add --all
    $ git commit -m '<message>'
    $ git push origin <feature_branch>

Update feature branch with any recent commits on the base branch (usually "develop"):

    $ git checkout <feature_branch>
    $ git rebase develop

Incorporate feature into develop branch:

    $ git checkout develop
    $ git merge --no-ff <feature_branch>
    $ git push origin develop

Delete local and remote feature branches:

    $ git branch -d <feature_branch>
    $ git push origin --delete <feature_branch>


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
    
Incorporate final release back into develop, and delete branch:

    $ git checkout develop
    $ git merge --no-ff <release-X.X.X>
    $ git branch -d <release-X.X.X>
    $ git push origin --delete <release-x.x.x>
    

### Resources

- http://nvie.com/posts/a-successful-git-branching-model/

- https://www.atlassian.com/git/tutorials/

### Author

Nathaniel Reynolds (nathaniel.reynolds@gmail.com)

