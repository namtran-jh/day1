1. Why STAGED state exists?
There are 3 states of Git: MODIFIED (Working directory) - STAGED (Index) - COMMITED (Local repository - HEAD)
 - `MODIFIED`: you have changed the files but not commited and stored it in local repository
 - `STAGED`: you have marked the modified file in its current version for including the changes in the next commit (stores information about what will go into the next commit)
 - `COMMITED`: you have stored changes in local repository

2. Differences between commitID at local/remote repository?
It is the same

3. Differences between rebase/merge - which related to commits?
 - `History logs`: **rebase** has a clean history log than **merge**
 -  Merge preserves history whereas rebase rewrites it (**merge** easily trace history commit because the history remains same, **rebase** is more difficult because of its obliteration -> should be local repository)
 - `Revert conflicts`: **merge** is better than **rebase**

4. Merge/rebase test branch a/b/c/d/e to master
 - `Merge`: first merge auto solve conflicts, second merge manual solve conflicts..
 - `Rebase`: first rebase auto solve conflicts, second rebase manual solve conflicts and second branch commit rewrite the first

 > Conclusion:
 > `git merge`: history log is complicated but it preserves all commits (though those are merged), easy to trace
 > `git rebase`: history log is a straight beautiful simple line (easy to look) but it's complicated because all the commit records is not clear (often use in individual/small project, but not advice, still should use merge)
 
5. What is the [origin] in Git
It is a shorthand name for the remote repository. More precisely, it is used instead of that original repository's URL - and thereby makes referencing much easier
 - `git push`: assumes that you already have a remote repository defined for that branch. In this case, the default remote origin is used.
 - `git push origin master`: indicates that you are pushing to a specific remote, in this case, origin (multiple remote repositories)

 # Read again: git, commit, HEAD, origin/HEAD, ORIG_HEAD