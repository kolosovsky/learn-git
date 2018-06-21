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
git branch master -f <commit>
# make a branch point at a specific commit
```

```
git branch master -f <commit>
# make a branch point at a specific commit
```

