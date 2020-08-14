# We have 2 big branch call master (to hold test features for test site) and production

> `When we are creating new feature, what branch should we based on and why?`

When we creating new feature, we should base on branch **Production** because this branch is holding the lastest and the most stable code. Everything on this branch is suitable for adding new feature because of the smoothly working code.

> `If we have a feature branch that haven't been merged to production and that branch have bug, what course of action are you going to do with Git to before resolving the bug?`

We do nothing with Git because the problem at here is resolving the bug. After that, we will do with Git (we can stage it again, commit it, create pull request and review code with partners and then push it/merge it to production.

> `If someone accidentally merge a feature (feature/delete-user) onto production and have a list of commitId ended with (0492978, fc9348c, k101100), then another commit (a1fsas8) is added on top of the production branch. How do we remove that merged feature?`

In this case, we use **git revert** with 3 commitID of merged feature than we create 3 new commits confirm that changes of 3 commitID (0492978, fc9348c, k101100) had been deleted. -> **WRONG**
[1] Other case, if we want to remove that merged feature. We will use **git reset --hard** to the commitId before the list of commit on feature branch (commitId 0492978). We use **git cherry-pick commitID** or [Then we **git checkout a1fsas8 -- FILENAME** (just get changes not the commit)]
[2] We use **git rebase -i commitID** then delete **pick 3commitID**


# Bonus

> When we merge f/delete to master, what will happen with history log?
`master <- f/delete (a, b, c)`
`master: x, y, z, a, b, c`
`revert 3 commit: x, y, z, a, b, c, i, j,k`
`d fix bug`
`f/delete (a,b,c,d)`
`master <- f/delete`

**History log** add 2 new commits (`d` and `merge commit`): x, y, z, a, b, c, i, j, k, d, merge commit

> Write 1 git command for releasing f/delete? What happened if we merge f/delete to master many times
`master <- f/delete  (a, b, c)`
`commit d master`
`master: x, y, z, a, b, c, d`
`revert f/delete`
`master: x, y, z, a, b, c, d, i, j, k`
`master lost delete`
`Release f/delete?`
`master <- f/delete (what happened if merge 1 branch 2,3 times)`

**Command for release f/delete** git reset --hard commentId at the point before we revert f/delete
**Merge many times** cause nothing, because all commits of f/delete merged to master, everything `Already up to date`

> When we **git push origin master**, what will happened
`master (remote): a, b, c`
`git reset --hard b`
`master(local): a, b`

**Push to remote after git reset** error fail to push