## configuration

### --local (default)
```
git config user.name "Ed Kolosovsky"
```

```git config --list``` or ```cat <project>/.git/config```

### --global
```
git config --global user.email ed.kolosovsky@gmail.com
```
```git config --list --global``` or ``` cat ~/.gitnconfig ```

### --system
```
git config --system user.email ed.kolosovsky@gmail.com
```
```git config --list --system``` or ``` cat /etc/gitconfig```

### unset
```
git config --unset --local user.name
git config --remove-section --local user
```

### alias
```
git config --global alias.c 'config --global'
git c --list
```

```
git config --global alias.gg '!git add .; git commit' 
```

```

```

```

```

```

```

```

```

```

```