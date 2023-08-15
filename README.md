# Git
Git is a distributed version control system (VCS) designed to manage changes in source code during software development. It allows multiple developers to work on the same codebase simultaneously while keeping track of changes, facilitating collaboration, and providing a history of the project's evolution.

## Repository

In Git, a repository, often referred to as a "repo," is a data structure that holds and manages the collection of files, directories, and their version history. A repository contains all the information necessary to track changes to files and collaborate with other developers on a project. It serves as the core component of version control, enabling you to keep track of changes, collaborate with others, and manage the evolution of your project over time.

1. **Local Repository:**
    A local repository is the repository that resides on your local machine. It contains the complete history of changes, all the branches, tags, and configuration specific to your machine.
1. Remote Repository:
    A remote repository is hosted on a remote server, often on platforms like GitHub, GitLab, or Bitbucket. Remote repositories provide a central location for collaboration, allowing multiple developers to work on the same project. Changes made to the remote repository can be fetched, pushed, and pulled to and from your local repository.

## Setting up git repository
There are two ways of setting up the repository.
1. Creating a Repository from a Local Directory (Intializing).
1. Creating a Repository on a Remote Platform (Cloning).

## Initialize a git repository

Initializing a repository involves setting up a new Git repository from scratch in a local directory. This is typically done when you're starting a new project or converting an existing project into a Git repository. During the initialization process, Git creates a hidden subdirectory called `.git` within the project directory. This subdirectory contains all the necessary information for version control, including the commit history, configuration settings, and more.

To initialize a new repository, you'll use the following steps.

1. Create a Remote Repository:
Before you can push changes to a remote repository, you need to have a remote repository set up on a platform like GitHub, GitLab, or Bitbucket. You would typically create a remote repository through the web interface of the platform.
If you used git init to make a fresh repo, you'll have no remote repo to push changes to. This can be done by the following command.

1. Initialise git in local:

To initialise git in local system, use the following command:

```
git init
```

1. Link the Remote Repository:

After creating the remote repository and initialising the git in local, you need to establish a connection between your local repository and the remote repository. This is done by adding a remote reference. You can do this using the following command:

```
git remote add <remote_name> <remote_repo_url>
```

Pointing to the existing git repository can be done by adding the repository name to it.

```
git init <repository name>
```

## Cloning a git repository

Cloning a repository involves creating a copy of an existing remote repository onto your local machine. This copy includes the entire commit history, branches, tags, and all the project files. Cloning is a common way to collaborate on a project, as it allows multiple developers to work on the same codebase independently, while also enabling the synchronization of changes.

To clone a remote git repository use the following command:

```
git clone <Https/SSH repository link>
```

`git clone` will automatically configure your repo with a remote pointed to the Git URL you cloned it from. This means that once you make changes to a file and commit them, you can git push those changes to the remote repository.

## Git Basic flow

The basic Git workflow involves
1. Add
1. Commit
1. Push
1. Pull

Between Remote Repository and your local system/repository.

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

<p align="center">
    <img src="https://wac-cdn.atlassian.com/dam/jcr%3Adbf0c59f-848d-4814-bfd5-6b190a092963/03.svg?cdnVersion%3D1162" alt="Alt Text" width="500">
</p>

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

> **origin:** Refers to the remote repository.
> **branch:** Refers to the branch to which you want to push your changes

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

In Git, branches are an essential feature that allow you to create separate lines of development within a repository. Each branch represents an independent timeline of changes, making it possible to work on different features, fixes, or experiments without directly affecting the main project until you're ready to merge your changes.

It's important to understand that branches are just pointers to commits. When you create a branch, all Git needs to do is create a new pointer—it doesn’t create a whole new set of files or folders.

### Default branch

When you initialize a Git repository or clone an existing one, there's usually a default branch like master or main that serves as the mainline of development. This is where the stable and production-ready code resides.

![Alt text](https://wac-cdn.atlassian.com/dam/jcr%3A3b5d663b-0b1c-4321-a32c-0708769e8aeb/04%20Create%20a%20branch%20and%20make%20a%20change.svg?cdnVersion%3D1162)

### Create a new branch

To start working on a new feature or fixing a bug, you create a new branch. This branch will initially be identical to the branch you're branching from (often the default branch). You can create a new branch using the command:

```
git branch future-plans
```

This command creates a new branch called as **future-plans** from the default branch.

![Alt text](https://wac-cdn.atlassian.com/dam/jcr%3A36506d0e-5e8e-4ef8-82a5-368597c66efd/05%20Create%20a%20branch%20and%20make%20a%20change.svg?cdnVersion%3D1162)

To see the status of the branches available you can use the command:

```
git branch
```

It returns the list of all branches available with the active branch in green color.

### Switching between branches

To switch to a different branch, you use the command:

```
git checkout future-plans
```

In more recent versions of Git, you can use the following command for switching:

```
git switch future-plans
```

### Make changes to the new branch

Make changes to the new branch and commit your changes using the command:

```
git commit -m "changes on sub-branch"
```

Now your repository looks like this:

![Alt text](https://wac-cdn.atlassian.com/dam/jcr%3A5331fdcb-bfcf-435a-be7e-5b21d75a5531/06%20Create%20a%20branch%20and%20make%20a%20change.svg?cdnVersion%3D1162)

### Merge branches

Consider you created a new branch from `master/main` branch called as `future-plans` where all your changes goes into.

When you're ready to integrate your changes into the `main/master` branch, you can merge the changes from your `future-plans` branch back into the `main` branch. This combines the changes you made on the feature branch with the code on the main branch. The git merge command is used for this purpose:

Make sure you commit the changes made to your `future-plans` branch using the command:

```
git checkout main
git merge future-plans
```

After Merging your branch your repository looks like:

![Alt text](https://wac-cdn.atlassian.com/dam/jcr%3A72ab245a-391a-4aba-b6a5-741a10c2518b/07%20Create%20a%20branch%20and%20make%20a%20change.svg?cdnVersion%3D1162)


### Deleting a branch

Once there is no more use of a branch. It can be deleted by using the command:

```
git branch -d future-plans
```

### Pushing all the changes to the remote repository

Once all changes are done. The code is pushed to the remote repository using the command:

```
git push origin main
```