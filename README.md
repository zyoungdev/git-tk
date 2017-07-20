# Git Time Keeper

Time tracking bash script where state is kept in a git branch. No daemon or binary to install. Run ```git-tk``` to record starting and ending timestamps. You may even reboot after recording a starting timestamp.

To use:
```Bash
# Initialize the tk branch
$ git-tk init
 
# Create a starting timestamp
$ git-tk
# Do some work
$ git commit --allow-empty -m "Test commit"
# Create an ending timestamp
$ git-tk
 
# Use an interactive rebase to edit timestamps 
# OR continue while rebasing
$ git-tk rebase
# Override timestamp
$ git-tk rebase "$(date)"
 
# Do some work
$ git commit --allow-empty -m "Test commit"
# Create a starting timestamp manually
$ git-tk "$(date -d '10 minutes ago')"
# Create an ending timestamp manually
$ git-tk "$(date -d '5 minutes ago')"
 
# List commits with timestamps in an easy to read format
$ git-tk log
# List whole commits with timestamps in an easy to read format
$ git-tk log -v
```

## Using Git Alias
```
# ~/.gitconfig
...

[alias]
    tk = !"/path/to/git-tk"
```
