## clean

```
git clean -dxf
# remove files that are not under version control, starting from the current directory
# -d remove untracked directories in addition to untracked files
# -x remove ignored files as well
# -f git clean will refuse to delete files or directories unless given -f, -n or -i or clean.requireForce is set to true
```