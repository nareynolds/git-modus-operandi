# git-branching-model
What I've found to be common, best-practices approach to development with git

clone repo:

    $ git clone <https://github.com/.../....git>

switch to / work on / checkout branch:
    $ git checkout <branch>

update local branch from remote repo (usually “origin”):
  $ git fetch
  $ git merge origin/<branch>

... or
  $ git pull origin <branch>

reset working copy to remote repo (discard changes):
  $ git reset --hard

create a local feature branch:
  $ git checkout -b <feature_branch> <branch>

save local feature branch to remote repo (usually “origin”):
  $ git push origin <feature_branch>

save changes made to feature branch:
  $ git add --all
  $ git commit -m ‘<message>’
  $ git push origin <feature_branch>

incorporate feature into develop branch:
  $ git checkout develop
  $ git merge --no-ff <feature_branch>
  $ git push origin develop

delete local and remote feature branch:
  $ git branch -d <feature_branch>
  $ git push origin delete <feature_branch>


### Resources
http://nvie.com/posts/a-successful-git-branching-model/
