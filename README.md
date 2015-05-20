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

Reset working copy to remote repo (discard changes):

    $ git reset --hard


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
    $ git push origin delete <feature_branch>


### Resources

http://nvie.com/posts/a-successful-git-branching-model/

https://www.atlassian.com/git/tutorials/
