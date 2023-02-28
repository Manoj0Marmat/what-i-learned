[👈 **_Back_**](./index.md)

# Failed to push some refs to git_repo

When we are trying to push changes to a Git branch but your local branch has [diverged](./src/solve-branch-diverge/diverge.md) from the remote branch, meaning that there are changes on the remote branch that you do not have locally.

##### Message

> [Error]
> ! [rejected] main -> main (non-fast-forward)
> error: failed to push some refs to 'git_repo'.

##### Steps to Resolve

1. `git fetch`
2. `git checkout <branch_name>`
3. `git merge origin/<branch_name>` or `git merge --allow-unrelated-histories origin/<branch_name>`
4. Resolve any merge conflicts that may arise
5. `git push`

> [NOTE]
> If you are still getting same error message, it is possible that someone else has pushed changes to the remote branch while you were working on your local branch.
