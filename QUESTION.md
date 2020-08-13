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
 