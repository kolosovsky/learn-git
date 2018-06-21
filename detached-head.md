## detached head 
HEAD normally refers to a named branch. 
Meanwhile, each branch refers to a specific commit.

**Detached head** means simply that HEAD refers to a specific commit, as opposed to referring to a named branch.

If you crate a commit in this state nothing will refer to this commit. 

```
git checkout <commit>
# detach HEAD at <commit> and update the index and the files in the working tree
# local modifications to the files in the working tree are kept
# the most useful thing you can do with it is explore an older state of a repository
```

Return from detached HEAD state to your branch

```git checkout -``` or ```git checkout <branchname>```