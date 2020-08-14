# COMPARISON between [git cherry-pick], [git checkout --] and [git rebase -i]

|    ###    | git cherry-pick                     | git checkout --                     | git rebase -i                       |
|:---------:|:-----------------------------------:|:-----------------------------------:|:-----------------------------------:|
| syntax    | `git cherry-pick ${id}`             | `git checkout ${id} -- ${filename}` | `git rebase -i ${id}`               |
| priority  | **1st**                             |                                     |                                     |

> **git cherry-pick**

 - Checkout a specific commit to the current branch (apply changes of specific branch to current branch)
 - Easy to use with 1 command line

> **git checkout --**

 - Write the file contents from the last commit (or checkout-ed specific commit if we include the id)
 - We have to track the changes of file contents, we just use it for a specific file name. If that commit change many files at the same time, this's not the best solution (we have to do this many time)

> **git rebase -i**

 - Show a list of commits from that specfic commit up to now in the editor, it also allows us to edit the list
 - We have to edit the list, delete the commit we don't want it appeared in the history log (accidentally merged commit), save and close the file then our branch will be in the state we wish. But this will change the history, and it'll mess with anyone who's been collaborating on this branch
