Git Commands
============

### Init

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |

### Config

| Command | Description |
| ------- | ----------- |
|`git config --global user.name "<username>"`| Configure the author name |
|`git config --global user.email <email address>`| Configure the author email address |
### Clone

| Command | Description |
| ------- | ----------- |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Status

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
### Add

| Command | Description |
| ------- | ----------- |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` or `git add .` | Add all new and changed files to the staging area |

### Remove

| Command | Description |
| ------- | ----------- |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Commit

| Command | Description |
| ------- | ----------- |
| `git commit -m "[commit message]"` | Commit changes |
| `git commit -a -m "[commit message]"` | Add all changes to stage and commit changes |


### Branch

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |


### Checkout

| Command | Description |
| ------- | ----------- |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |

### Merge
| Command | Description |
| ------- | ----------- |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |

### Stash
| Command | Description |
| ------- | ----------- |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Push

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |

### Pull

| Command | Description |
| ------- | ----------- |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |

### Remote

| Command | Description |
| ------- | ----------- |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |