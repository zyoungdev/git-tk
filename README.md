# Git Time Keeper

Time tracking bash script where state is kept in a git branch. No daemon or binary to install. Run ```git-tk``` to record starting and ending timestamps. You may even reboot after recording a starting timestamp.

To use:
```Bash
$ git-tk init                               # Initialize the tk branch
 
$ git-tk                                    # Create a starting timestamp
$ git commit --allow-empty -m "Test commit" # Do some work
$ git-tk                                    # Create an ending timestamp
 
$ git-tk rebase                             # Use an interactive rebase to edit timestamps
$ git-tk rebase start "$(date)"             # Convert commit to a starting timestamp
$ git-tk rebase end "$(date)"               # Convert commit to a starting timestamp
 
$ git-tk create start "$(date)"             # Create a starting timestamp manually
$ git-tk create end "$(date)"               # Create an ending timestamp manually
 
$ git-tk log                                # List commits with timestamps in an easy to read format
$ git-tk log -v                             # List whole commits with timestamps in an easy to read format
```

## Using Git Alias
```
# ~/.gitconfig
...

[alias]
    tk = !"/path/to/git-tk"
```
