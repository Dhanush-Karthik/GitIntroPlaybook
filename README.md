# Git-Basics
Basic commands and concepts of Git

## Git Basic flow

The basic Git workflow involves
1. Clone
2. Add
3. Commit
4. Push
5. Pull

Between Remote Repository and your local system/repository.
## Clone a remote repository

To clone a remote git repository use the following command:

```
git clone <Https/SSH repository link>
```

## Get the status of the local repository

To get the status of the local repository use the following command:

```
git status
```

## Staging area

The staging area, also commonly referred to as the "index," is an intermediate step in the Git version control system that allows you to prepare and organize changes before committing them to the repository. It acts as a buffer between your working directory (where you make edits) and the repository's history (where your changes are permanently recorded).

1. **Working Directory:** This is where you create, modify, and delete files as you work on your project.

1. **Staging Area:** After you make changes to your files in the working directory, you can use the git add command to stage these changes. Staging is the process of selecting specific changes to include in the next commit. When you stage changes, Git takes a snapshot of the current state of the modified files and places them in the staging area.

1. **Commit:** Once your changes are staged in the staging area, you can create a commit using the git commit command. A commit is a permanent record of the changes you've staged. It includes a snapshot of the staged changes, a unique identifier (SHA-1 hash), a timestamp, and the author's information. Committing effectively saves your changes to the repository's history.

## Tell git to track your new file

To tell git to track your new file use the command:

```
git add <file name>
```

The `git add` command moves changes from the working directory to the Git staging area. The staging area is where you prepare a snapshot of a set of changes before committing them to the official history.

`git add .` adds all the changes to the staging area.
![Alt text](https://wac-cdn.atlassian.com/dam/jcr%3Adbf0c59f-848d-4814-bfd5-6b190a092963/03.svg?cdnVersion%3D1162)
## Commit changes to git

You can commit the changes to your local repository using the command:

```
git commit -m "your commit message"
```

The git commit takes the staged snapshot and commits it to the project history.

Up until this point, everything you have done is on your local system and invisible to your Remote repository until you push those changes.

## Pushing your changes to remote repository

You can push your changes to remote repository using the command:

```
git push origin branch_name
```

**origin:** Refers to the remote repository.
**branch:** Refers to the branch to which you want to push your changes

## Pulling changes from remote repository to the local repository

You can pull changes from the remote repository using the command:

```
git pull
```

## Stash your changes 

On trying to update the changes made on the remote repository in your local you might get an error

error: Your local changes to the following files would be overwritten by merge:
        README.md
Please commit your changes or stash them before you merge

Inorder to overcome this error you can either commit your changes or you can stash them

To stash your changes use the command:

```
git stash
```

Stashing allows you to save your changes in a hidden area and revert your working directory to a clean state.

## Merge changes to your working repository

To merge the changes made on your remote repository to your local repository you can use the command:

```
git merge
```

## Branch your project 

Making changes to your project as seen above is not an efficient way. Updating every thing to the main branch makes difficult to manage and organize the changes. 

In Git, branches are an essential feature that allow you to create separate lines of development within a repository. Each branch represents an independent timeline of changes, making it possible to work on different features, fixes, or experiments without directly affecting the main project until you're ready to merge your changes

### Default branch

When you initialize a Git repository or clone an existing one, there's usually a default branch like master or main that serves as the mainline of development. This is where the stable and production-ready code resides.

### Create a new branch

To start working on a new feature or fixing a bug, you create a new branch. This branch will initially be identical to the branch you're branching from (often the default branch). You can create a new branch using the command:

```
git branch branch-name
```

This command creates a new branch called as **branch-name** from the default branch.

To see the status of the branches available you can use the command:

```
git branch
```

It returns the list of all branches available with the active branch in green color.

### Switching between branches

To switch to a different branch, you use the command:

```
git checkout branch_name
```

In more recent versions of Git, you can use the following command for switching:

```
git switch branch_name
```

### Merge branches

Consider you created a new branch from `master/main` branch called as `editing` where all your changes goes into.

When you're ready to integrate your changes into the `main/master` branch, you can merge the changes from your `editing` branch back into the `main` branch. This combines the changes you made on the feature branch with the code on the main branch. The git merge command is used for this purpose:

Make sure you commit the changes made to your `editing` branch using the command:

```
git commit -m "changes on sub-branch
```

```
git checkout main
git merge editing
```