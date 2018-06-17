## gitignore

source: https://www.atlassian.com/git/tutorials/saving-changes/gitignore

### patterns
<table>

<thead>

<tr>

<th>Pattern</th>

<th>Example matches</th>

<th>Explanation*</th>

</tr>

</thead>

<tbody>

<tr>

<td>**/logs</td>

<td>logs/debug.log  
logs/monday/foo.bar  
build/logs/debug.log</td>

<td>You can prepend a pattern with a double asterisk to match directories anywhere in the repository.</td>

</tr>

<tr>

<td>**/logs/debug.log</td>

<td>logs/debug.log  
build/logs/debug.log  
<br>BUT NOT<br>
logs/build/debug.log</td>

<td>You can also use a double asterisk to match files based on their name and the name of their parent directory.</td>

</tr>

<tr>

<td>*.log</td>

<td>debug.log  
foo.log  
.log  
logs/debug.log</td>

<td>An asterisk is a wildcard that matches zero or more characters.</td>

</tr>

<tr>

<td>*.log  
!important.log</td>

<td>debug.log  
trace.log  
<br>BUT NOT<br>
important.log  
logs/important.log</td>

<td>Prepending an exclamation mark to a pattern negates it. If a file matches a pattern, but _also_ matches a negating pattern defined later in the file, it will not be ignored.</td>

</tr>

<tr>

<td>*.log  
!important/*.log  
trace.*</td>

<td>debug.log  
important/trace.log  
<br>BUT NOT<br>
important/debug.log</td>

<td>Patterns defined after a negating pattern will re-ignore any previously negated files.</td>

</tr>

<tr>

<td>/debug.log</td>

<td>debug.log  
<br>BUT NOT<br>
logs/debug.log</td>

<td>Prepending a slash matches files only in the repository root.</td>

</tr>

<tr>

<td>debug.log</td>

<td>debug.log  
logs/debug.log</td>

<td>By default, patterns match files in any directory</td>

</tr>

<tr>

<td>debug?.log</td>

<td>debug0.log  
debugg.log  
<br>BUT NOT<br>
debug10.log</td>

<td>A question mark matches exactly one character.</td>

</tr>

<tr>

<td>debug[0-9].log</td>

<td>debug0.log  
debug1.log  
<br>BUT NOT<br>
debug10.log</td>

<td>Square brackets can also be used to match a single character from a specified range.</td>

</tr>

<tr>

<td>debug[01].log</td>

<td>debug0.log  
debug1.log  
<br>BUT NOT<br>
debug2.log  
debug01.log</td>

<td>Square brackets match a single character form the specified set.</td>

</tr>

<tr>

<td>debug[!01].log</td>

<td>debug2.log  
<br>BUT NOT<br>
debug0.log  
debug1.log  
debug01.log</td>

<td>An exclamation mark can be used to match any character except one from the specified set.</td>

</tr>

<tr>

<td>debug[a-z].log</td>

<td>debuga.log  
debugb.log  
<br>BUT NOT<br>
debug1.log</td>

<td>Ranges can be numeric or alphabetic.</td>

</tr>

<tr>

<td>logs</td>

<td>logs  
logs/debug.log  
logs/latest/foo.bar  
build/logs  
build/logs/debug.log</td>

<td>If you don't append a slash, the pattern will match both files and the contents of directories with that name. In the example matches on the left, both directories and files named _logs_ are ignored</td>

</tr>

<tr>

<td>logs/</td>

<td>logs/debug.log  
logs/latest/foo.bar  
build/logs/foo.bar  
build/logs/latest/debug.log</td>

<td>Appending a slash indicates the pattern is a directory. The entire contents of any directory in the repository matching that name – including all of its files and subdirectories – will be ignored</td>

</tr>

<tr>

<td>logs/  
!logs/important.log</td>

<td>logs/debug.log  
logs/important.log</td>

<td>Wait a minute! Shouldn't logs/important.log be negated in the example on the left  

Nope! Due to a performance-related quirk in Git, you _can not_ negate a file that is ignored due to a pattern matching a directory</td>

</tr>

<tr>

<td>logs/**/debug.log</td>

<td>logs/debug.log  
logs/monday/debug.log  
logs/monday/pm/debug.log</td>

<td>A double asterisk matches zero or more directories.</td>

</tr>

<tr>

<td>logs/*day/debug.log</td>

<td>logs/monday/debug.log  
logs/tuesday/debug.log  
<br>BUT NOT<br>
logs/latest/debug.log</td>

<td>Wildcards can be used in directory names as well.</td>

</tr>

<tr>

<td>logs/debug.log</td>

<td>logs/debug.log  
<br>BUT NOT<br>
debug.log  
build/logs/debug.log</td>

<td>Patterns specifying a file in a particular directory are relative to the repository root. (You can prepend a slash if you like, but it doesn't do anything special.)</td>

</tr>

</tbody>

</table>

### personal git ignore rules
you can also define personal ignore patterns for a particular repository in a special file at ```.<project>/.git/info/exclude```

### global git ignore rules
in addition, you can define global git ignore patterns for all repositories on your local system by setting the git core.excludesFile property 
```
touch ~/.gitignore
git config --global core.excludesFile ~/.gitignore
```

### debugging .gitignore files
you can use the git check-ignore command with the -v (or --verbose) option to determine which pattern is causing a particular file to be ignored
```
git check-ignore -v debug.log
```