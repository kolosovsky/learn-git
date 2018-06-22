## garbage collection

```
git gc
# run gargabe collection
```

garbage collection runs a number of housekeeping tasks within the current repository, such as:
- compressing file revisions
- **removing unreachable objects**

`gc.pruneExpire` controls how old the unreferenced loose objects have to be before they are pruned

garbage collection will keep objects referenced by:
- your current set of branches and tags
- the index
- remote-tracking branches
- refs saved by git filter-branch in refs/original/
- reflogs (see options below)

`gc.reflogExpire` can be set to indicate how long historical entries within each branch’s reflog should remain available in this repository. it defaults to 90 days.

`gc.reflogExpireUnreachable` can be set to indicate how long historical reflog entries which are not part of the current branch should remain available in this repository. it defaults to 30 days.

some git commands may automatically run `git gc`