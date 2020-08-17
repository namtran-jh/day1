# We have 2 branches: production and feature (payment). Solve the problem when we want to delete temporarily the feature branch (disable that payment feature)
![Popular scenario](/important.png)

> Scope: `Large history commits`

|    ###    | Different files                     | Same files                          |
|:---------:| ----------------------------------- | ----------------------------------- |
| syntax    | git rebase                          | git revert                          |


> Scope: `Small history commits`

|    ###    | Different files                     | Same files                          |
|:---------:| ----------------------------------- | ----------------------------------- |
| syntax    | git reset --hard                    | git diff (delete specific changes)  |
|           | git cherry-pick                     | create new commit                   |

> Other solution for **Different files**

`small {feature} big {product}` to the the merge point, then reset hard to the checkout point then apply stash (absolutely lose all history)
`big {feature} small {product}` find differences between each commit then copy the change out

> **Worst** scenario HERE: Feature branch (payment) is coded by A, Product branch after merge feature (schedule) is coded by B. Now the time when C have to resolve the problem, in case both product and feature branch are enormous (maybe > 50 commits, > 50 file changes, ...). Some commit in `production` included the **change** and the **import** of `feature`

  1. Set flag on production (to turn on/off feature) then create new commits
  2. Checkout temporary branch to save the current state of production branch (for future maintain and rework of team), then fix manually in your way

`ALWAYS PAY ATTENTION TO` checkout new branch to save current state of master branch (in hard scenario)