## reflog (reference logs)

reflogs record when the tips of branches and other references were updated in the local repository.

```
git reflog
# show the reference logs
```

`gc.reflogExpire` can be set to indicate how long historical entries within each branch’s reflog should remain available in this repository. it defaults to 90 days.

`gc.reflogExpireUnreachable` can be set to indicate how long historical reflog entries which are not part of the current branch should remain available in this repository. it defaults to 30 days.