## branches

A **branch** in Git is simply a lightweight movable pointer to one of commits. 
Every time you commit, it moves forward automatically.

How does Git know what branch you’re currently on? It keeps a special pointer called **HEAD**.

```
git branch --list
# list branches
```

```
git branch <branchname>
# create new branch
```

```
git checkout <branchname>
# switch branch
```

```
git branch <branchname> -f <commit>
# make a branch point at a specific commit
```

```
git checkout <tree-ish> <pathspec>
# restore older file version and add these changes to the index
```

```
git checkout <pathspec>
# is the opposite of git add <paths>
```

when the argument is both a valid tree-ish and a valid pathspec and you want to checkout these paths out of the index then use ```git checkout -- <pathspec>```

```
git log
# show commit logs
```

```
git show [options] [<object>…​]
# show one or more objects (blobs, trees, tags and commits)
```

```
git show HEAD~2:README.MD
# show the contents of the README.MD as they were current in the HEAD~2
```

```
git show :/major fix
# show the contents of the README.MD as they were current in the HEAD~2
```