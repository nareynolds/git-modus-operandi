# git-branching-model
What I've found to be common, best-practice approaches to development with git


### getting (re)started

clone repo:

    $ git clone https://github.com/<username>/<reponame>.git

update local branch from remote repo (usually “origin”):

    $ git pull origin <branch>

... or

    $ git fetch
    $ git merge origin/<branch>

reset working copy to remote repo (discard changes):

    $ git reset --hard


### feature branching

create a local feature branch:

    $ git checkout -b <feature_branch> <branch>

switch to / work on / checkout branch:

    $ git checkout <branch>

save local feature branch to remote repo (usually “origin”):

    $ git push origin <feature_branch>

save changes made to feature branch:

    $ git add --all
    $ git commit -m '<message>'
    $ git push origin <feature_branch>

update feature branch with any recent commits on the develop branch:

    $ git checkout <feature_branch>
    $ git rebase develop

incorporate feature into develop branch:

    $ git checkout develop
    $ git merge --no-ff <feature_branch>
    $ git push origin develop

delete local and remote feature branch:

    $ git branch -d <feature_branch>
    $ git push origin delete <feature_branch>


### Resources
http://nvie.com/posts/a-successful-git-branching-model/
https://www.atlassian.com/git/tutorials/
