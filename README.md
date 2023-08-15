# Git
Git is a distributed version control system (VCS) designed to manage changes in source code during software development. It allows multiple developers to work on the same codebase simultaneously while keeping track of changes, facilitating collaboration, and providing a history of the project's evolution.

To make the learning fun I have included link for Git visualiser where one can visualise how git works. Feel free to make use of it. 
`https://git-school.github.io/visualizing-git/`

## How git is organized

Git organizes the version control process using the following three components.

1. Working Directory
2. Index or Staging
3. Repository

These components work together to manage changes, track history, and facilitate collaboration.
<p align="center">
    <img src="https://git-scm.com/images/about/index1%402x.png" alt="Alt Text" width="500">
</p>

## Working Directory

In Git, the working directory, also known as the working tree, refers to the directory on your local machine where you have all your project files. It's the place where you create, modify, and organize your code and other project-related files. The working directory is where you actively work on your project, making changes, adding new files, and editing existing ones.

## Staging

The index, or staging area, is an intermediate step between the working directory and the repository. It's a snapshot of the changes you plan to include in your next commit. 

Let us consider an anology,

Imagine you're a chef cooking a delicious meal. You have all your ingredients in your kitchen (your working directory), and you want to put together a new recipe (make changes to your project files). Now, before you serve the meal (commit your changes), you need to prepare everything nicely and ensure it tastes great.

In Git, staging is like setting up your kitchen counter. It's where you place all the ingredients you're planning to use for your recipe. But just because the ingredients are on the counter doesn't mean you've already cooked them together. Similarly, when you stage changes in Git, you're not yet committing them to your project history, but you're getting ready to.

## Repository

In Git, a repository, often referred to as a "repo," is a data structure that holds and manages the collection of files, directories, and their version history. A repository contains all the information necessary to track changes to files and collaborate with other developers on a project. It serves as the core component of version control, enabling you to keep track of changes, collaborate with others, and manage the evolution of your project over time.

1. **Local Repository:**
    A local repository is the repository that resides on your local machine. It contains the complete history of changes, all the branches, tags, and configuration specific to your machine.
1. **Remote Repository:**
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

2. Initialise git in local:

To initialise git in local system, use the following command:

```
git init
```

3. Link the Remote Repository:

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

## git clone vs git init

`git init` and `git clone` can be easily confused. At a high level, they can both be used to "initialize a new git repository." However, `git clone` is dependent on `git init`. `git clone` is used to create a copy of an existing repository. Internally, `git clone` first calls `git init` to create a new repository. It then copies the data from the existing repository, and checks out a new set of working files.

## Bare repository

A bare repository is a special type of repository that does not have a working directory. It only contains the version history, branches, tags, and other Git-specific information, making it ideal for use as a remote repository that multiple developers can push and pull from.

To create a bare repository you can use the command:

`git init --bare <repository_name>.git`

Bare repositories are often used as centralized remote repositories in team environments where collaboration is essential. Developers can push their changes to a bare repository, and other team members can pull those changes from the same repository. They are best suited for serving as shared remote repositories that multiple developers interact with.

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

<p align="center">
    <img src="https://wac-cdn.atlassian.com/dam/jcr%3A3b5d663b-0b1c-4321-a32c-0708769e8aeb/04%20Create%20a%20branch%20and%20make%20a%20change.svg?cdnVersion%3D1162" alt="Alt Text" width="500">
</p>

### Create a new branch

To start working on a new feature or fixing a bug, you create a new branch. This branch will initially be identical to the branch you're branching from (often the default branch). You can create a new branch using the command:

```
git branch future-plans
```

This command creates a new branch called as **future-plans** from the default branch.

<p align="center">
    <img src="https://wac-cdn.atlassian.com/dam/jcr%3A36506d0e-5e8e-4ef8-82a5-368597c66efd/05%20Create%20a%20branch%20and%20make%20a%20change.svg?cdnVersion%3D1162" alt="Alt Text" width="500">
</p>


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

<p align="center">
    <img src="https://wac-cdn.atlassian.com/dam/jcr%3A5331fdcb-bfcf-435a-be7e-5b21d75a5531/06%20Create%20a%20branch%20and%20make%20a%20change.svg?cdnVersion%3D1162" alt="Alt Text" width="500">
</p>

### Merge branches

Consider you created a new branch from `master/main` branch called as `future-plans` where all your changes goes into.

When you're ready to integrate your changes into the `main/master` branch, you can merge the changes from your `future-plans` branch back into the `main` branch. This combines the changes you made on the feature branch with the code on the main branch. The git merge command is used for this purpose:

Make sure you commit the changes made to your `future-plans` branch using the command:

```
git checkout main
git merge future-plans
```

After Merging your branch your repository looks like:

<p align="center">
    <img src="https://wac-cdn.atlassian.com/dam/jcr%3A72ab245a-391a-4aba-b6a5-741a10c2518b/07%20Create%20a%20branch%20and%20make%20a%20change.svg?cdnVersion%3D1162" alt="Alt Text" width="500">
</p>


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


## Git Structure

The structure of a Git repository includes various components that work together to manage and track changes in your project's files. Here's an overview of the key elements in a Git repository's structure. The three main structure of git are

1. Working directory
2. Index(Staging Area)
3. HEAD
4. Detached Head


### Working Directory:

The working directory is the directory on your local machine where you have all your project files. It's the place where you edit, modify, and create new files as you work on your project. These changes are initially separate from the version control system. When you make changes to files in the working directory, Git doesn't automatically track those changes. Instead, you need to explicitly tell Git which changes to include in the next commit. The working directory is also sometimes referred to as the "working tree."

### Index (Staging Area):

The index, also known as the staging area, is an intermediate step between the working directory and the repository. It's a place where you assemble and organize changes before you commit them to the version history. When you use the `git add` command, you're actually moving changes from the working directory to the index. This allows you to selectively choose which changes you want to include in your next commit. The index acts as a snapshot of what your next commit will look like. Once you've staged your changes in the index, you can use the `git commit` command to create a new commit that captures those staged changes.

### HEAD:

HEAD is a special pointer/reference in Git that points to the latest commit in the currently checked-out branch.When you commit changes, the branch pointer moves forward to point to the new commit, and HEAD updates to point to the latest commit on that branch. This means that HEAD is always pointing to the tip of the current branch.

> **_NOTE:_**  HEAD does not points directly to the commit itself. Instead it points to the branch name where the recent commit has taken place.

```
git checkout <branch-name>
```
<p align="center">
    <img width="679" alt="Screenshot 2023-08-15 at 6 11 32 PM" src="https://github.com/Dhanush-Karthik/Git-Basics/assets/109062680/24f9044b-fdf1-482f-bf70-88e0b1d21243">
</p>

### Detached HEAD:

Detached HEAD is a state in Git where the HEAD reference points directly to a specific commit rather than to a named branch. This can happen when you checkout a commit directly using its hash or through other means that don't involve checking out a branch.

```
git checkout <commit-hash>
```

One can get the `commit-hash` from the `git log` command.

<p align="center">
    <img width="679" alt="Screenshot 2023-08-15 at 6 10 50 PM" src="https://github.com/Dhanush-Karthik/Git-Basics/assets/109062680/533451e1-d7d9-4465-b2ee-91b08608690f">
</p>

When you make changes and commits in a detached HEAD state, those changes are captured just like regular commits. However, because you're not on a named branch, there's no branch reference pointing to these commits, which means they're not as easily accessible or part of the main project timeline. This is why it's important to handle detached HEAD commits properly to avoid losing your work.

To create commits use the command:
```
git commit -m "your message"
```

<p align="center">
    <img width="679" alt="Screenshot 2023-08-15 at 6 12 12 PM" src="https://github.com/Dhanush-Karthik/Git-Basics/assets/109062680/2bfd3e61-b4b4-40cb-8a93-26e20fa5ed46">
</p>

To keep track of the commits made on the detached HEAD, a new branch is created using the command `git branch <branch-name>`

```
git branch detached-branch
```

<p align="center">
    <img width="679" alt="Screenshot 2023-08-15 at 6 12 31 PM" src="https://github.com/Dhanush-Karthik/Git-Basics/assets/109062680/2855f7e5-603e-4e9c-b5ec-54e812afef04">
</p>