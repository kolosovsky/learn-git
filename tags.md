## tags
Git supports two types of tags: **lightweight** and **annotated**.

A **lightweight tag** is very much like a branch that doesn’t change — it’s just a pointer to a specific commit.

**Annotated tags**, however, are stored as full objects in the Git database. They’re:
 - checksummed; 
 - contain the tagger name, email, and date; 
 - have a tagging message; 
 - and can be signed and verified with GNU Privacy Guard (GPG). 

```
git tag -a v1.4 -m "my version 1.4"
# create an annotated tag
# the -m specifies a tagging message
```

```
git tag v1.4-lw
# create a lightweight tag
```

```
git tag --list 
# or 
git tag -l 
# or 
git tag
# list the available tags
```

```
git tag --contains HEAD
# list all tags for a certain commit
```
