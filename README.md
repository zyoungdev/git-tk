# Git Time Keeper

Time tracking bash script where state is kept in a git branch. No daemon or binary to install. Run ```git-tk``` to record starting and ending timestamps. You may even reboot after recording a starting timestamp.

To use:
```bash
###########################
# Initialize the tk branch
###########################
# Git must be initialized with at least one commit
$ git init
$ git commit --allow-empty -m "Initial Commit"
# Initialize the git-tk branch
$ git-tk init
 
###########################
# Start and stop the timer
###########################
# Create a starting timestamp
$ git-tk
# Do some work
$ git commit --allow-empty -m "Test commit"
# Create an ending timestamp
$ git-tk
 
###########################
# Change the timestamps
###########################
# This command will initiate rebasing interactively
# It will also continue/skip during the rebase
$ git-tk rebase

# Now, select the timestamps you'd like to edit
#   by changing 'pick' to one of 'edit' or 'reword'

# For each timestamp you are changing,
#   run this command with your chosen timestamp
# You can also copy, paste and edit the timestamp from
#   the output of git status
$ git-tk rebase "$(date)"
 
##############################
# Placing arbitrary timestamps
##############################
# Do some work
$ git commit --allow-empty -m "Test commit"
# Create a starting timestamp manually
$ git-tk "$(date -d '10 minutes ago')"
# Create an ending timestamp manually
$ git-tk "$(date -d '5 minutes ago')"
 
###############################
# Viewing the log of timestamps
###############################
# List commits with timestamps in an easy to read format
$ git-tk log
# List whole commits with timestamps in an easy to read format
$ git-tk log -v
```

## Using Git Alias
```bash
# ~/.gitconfig
...

[alias]
    tk = !"/path/to/git-tk"
```
