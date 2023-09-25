Git Commands
============

These are common Git commands used in various situations:

To get details about all the git commands use the `git --help` or `git -h` command.

To get details and options available for specific commands use, command `git <command> --help` or `git <command> -h`.

Example:
`git init --help`, `git clone --help`

Start a working area (see also: git help tutorial):
```
   clone     Clone a repository into a new directory
   init      Create an empty Git repository or reinitialize an existing one
```

Work on the current change (see also: git help every day):
```
   add       Add file contents to the index
   mv        Move or rename a file, a directory, or a symlink
   restore   Restore working tree files
   rm        Remove files from the working tree and from the index
```
Examine the history and state (see also: git help revisions):
```
   bisect    Use binary search to find the commit that introduced a bug
   diff      Show changes between commits, commit and working tree, etc
   grep      Print lines matching a pattern
   log       Show commit logs
   show      Show various types of objects
   status    Show the working tree status
```

Grow, mark and tweak your common history:
```
   branch    List, create, or delete branches
   commit    Record changes to the repository
   merge     Join two or more development histories together
   rebase    Reapply commits on top of another base tip
   reset     Reset current HEAD to the specified state
   switch    Switch branches
   tag       Create, list, delete, or verify a tag object signed with GPG
```

Collaborate (see also: git help workflows):
```
   fetch     Download objects and refs from another repository
   pull      Fetch from and integrate with another repository or a local branch
   push      Update remote refs along with associated objects
```
## Ignoring Files

   Create a `.gitignore` file in your repository to specify files or patterns to ignore.


  
## Init

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git init --bare` | Initialize a bare repository |
## Config

| Command | Description |
| ------- | ----------- |
|`git config --global user.name "<username>"`| Configure the author name |
|`git config --global user.email <email address>`| Configure the author email address |
## Clone

| Command | Description |
| ------- | ----------- |
| `git clone <repo-link>` | Create a local copy of a remote repository |
| `git clone --bare <repo-link>` | Creates a bare clone, which doesn't have a working directory and is used for server-side repositories |
| `git clone --mirror <repo-link>` | Create a mirrored clone, which is a bare clone that reflects updates pushed to the original repository |

## Status

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
## Add

| Command | Description |
| ------- | ----------- |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` or `git add .` | Add all new and changed files to the staging area |

## Remove

| Command | Description |
| ------- | ----------- |
| `git rm [file-name.txt]` | Remove a file (or folder) |
| `git rm -r [file-name.txt]` | Remove a file (or folder) recursively|

## Commit

| Command | Description |
| ------- | ----------- |
| `git commit -m "[commit message]"` | Commit changes |
| `git commit -a -m "[commit message]"` | Add all changes to stage and commit changes |


## Branch

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git push --delete origin [branch name]` | Delete a branch on remote repository |

## Checkout

| Command | Description |
| ------- | ----------- |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |

## Merge
| Command | Description |
| ------- | ----------- |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |

## Stash
| Command | Description |
| ------- | ----------- |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |
| `git stash list` | Lists all the stashes made |
| `git stash show` | See the changes in the file before stash and after stash |
| `git stash apply` | Apply latest stash made |
| `git stash pop` | Apply the latest stash made and removes from the stash |
| `git stash apply stash@{i}` | Apply particular stash made (i stands for index) |
| `git stash save <stashing message>` | Saving Stashes with the message |
| `git stash drop` | Deletes the recent stash made |
| `git stash drop stash@{i}` | Deletes the specific stash made (i stands for index) |
| `git stash clear` | Deletes the all the stash made |
| `git stash branch <branch_name>` | Creates a new branch and transfers the stashed work on that |

## Push

| Command | Description |
| ------- | ----------- |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push --delete origin [branch name]` | Delete a branch on remote repository |

## Pull

| Command | Description |
| ------- | ----------- |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |

## Remote

| Command | Description |
| ------- | ----------- |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

## Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |

## Undoing Changes

| Command | Description |
| ------- | ----------- |
|`git restore <file>`| Discard changes in a file (unstaged). |
|`git reset --hard <commit_hash>` | Reset your working directory to a specific commit. |
|`git revert <commit_hash>` | Create a new commit that undoes changes from a specific commit. |
|`git revert -m 1 <commit_hash>` | Create a new commit that undoes changes from a specific merge commit. |
