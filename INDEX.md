# We have 2 big branch call master (to hold test features for test site) and production

> `When we are creating new feature, what branch should we based on and why?`

When we creating new feature, we should base on branch **Production** because this branch is holding the lastest and the most stable code. Everything on this branch is suitable for adding new feature because of the smoothly working code.

> `If we have a feature branch that haven't been merged to production and that branch have bug, what course of action are you going to do with Git to before resolving the bug?`

We do nothing with Git because the problem at here is resolving the bug. After that, we will do with Git (we can stage it again, commit it, create pull request and review code with partners and then push it/merge it to production.

> `If someone accidentally merge a feature (feature/delete-user) onto production and have a list of commitId ended with (0492978, fc9348c, k101100), then another commit (a1fsas8) is added on top of the production branch. How do we remove that merged feature?`

In this case, if we want to remove that merged feature we will remove the commitID a1fsas8 too. We will use **git reset --hard** to the commitId before the list of commit on feature branch (commitId 0492978).