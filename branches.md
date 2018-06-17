## branches

A **branch** in Git is simply a lightweight movable pointer to one of commits. 
Every time you commit, it moves forward automatically.

How does Git know what branch you’re currently on? It keeps a special pointer called **HEAD**.

```
git branch --list
# list branches
```

```
git branch 'feature'
# create new branch
```

```
git checkout feature
# switch branch
```

