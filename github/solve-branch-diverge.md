# Divergent Branches

This error occurs when we trying to merge two branches that have [diverged](./src/solve-branch-diverge/diverge.md).

##### Message

> [Error]
> fatal: Need to specify how to [reconcile](./src/solve-branch-diverge/reconciling.md) divergent branches.

##### Steps to Resolve

1. `git merge <branch_name>`
2. `git rebase <branch_name>`
3. `git merge --abort`
