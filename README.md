# Git Guide

Welcome to the **Git Guide repository**! This repository provides practical examples and tutorials to help you learn Git, the widely-used distributed version control system.

---

## Table of Contents
- [What is Git?](#what-is-git)
- [Why Use Git?](#why-use-git)
- [Getting Started](#getting-started)
  - [Installing Git](#installing-git)
  - [Configuring Git](#configuring-git)
- [Basic Git Workflow](#basic-git-workflow)
  - [Initializing a Repository](#initializing-a-repository)
  - [Cloning a Repository](#cloning-a-repository)
  - [Staging and Committing Changes](#staging-and-committing-changes)
  - [Multiple Authors in a Commit](#multiple-authors-in-a-commit)
  - [Checking Status](#checking-status)
  - [Viewing Commit History](#viewing-commit-history)
- [Branching and Merging](#branching-and-merging)
- [Working with Remotes](#working-with-remotes)
- [Common Git Commands](#common-git-commands)
- [Ignoring Files with .gitignore](#ignoring-files-with-gitignore)
- [Git Stash](#git-stash)
- [Guidelines](#guidelines)

---

## What is Git?  
Git is a **distributed version control system** that tracks changes to files and enables multiple developers to collaborate efficiently. Git helps you:

- **Track versions** of your project files  
- **Collaborate** with other developers  
- **Backup** code on remote platforms like GitHub  

---

## Why Use Git?
- **Version Control:** Easily roll back changes and track project history.  
- **Collaboration:** Work with multiple developers without overwriting each other’s work.  
- **Backup:** Keep your code safe by pushing it to remote repositories.

---

## Getting Started

### Installing Git
#### Windows
1. Download Git: [git-scm.com](https://git-scm.com/download/win)  
2. Run the installer and follow prompts.  
3. Use **Git Bash** (recommended) or the command line for commands.

### Configuring Git
Set up your Git identity (name and email):
```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --list
```

You can check your Git configuration at any time by running:
```
git config --list
```

## Basic Git Workflow 
Here’s an overview of the basic Git commands you'll use in your workflow:

### Initialize a Git Repository
To create a new Git repository, navigate to your project folder and run:

```git init```
This creates a .git folder where Git will track changes.

### 2. Cloning an Existing Repository
To get a copy of an existing repository, use:

```git clone https://github.com/username/repository.git```

This will download the repository and all its files to your local machine.

### 3. Staging and Committing Changes
Adding Files to the Staging Area:
Once you've made changes to your files, you need to stage them before committing:
```
git add <filename>  # Add a specific file
git add .           # Add all changes in the current directory
```

Committing Changes:
Once staged, commit the changes with a message describing what you did:
```git commit -m "Descriptive commit message"```

## Defining Multiple Authors for a Commit

Each commit in Git has a default author, which is the person who made the changes to the code.

However, when working in teams, some code may be written collaboratively by a pair or a group. So how do we define the co-authorship for these additional contributors in a commit?

Git provides the ability to add multiple authors to a commit. To do this, after writing the commit message, skip two lines and use the keyword `Co-authored-by:`, followed by the name and the email associated with GitHub (within `< >`) of each co-author.

Each co-author should be on a separate line, as shown in the example below:

```bash
$ git commit -m "Add new functionality.
>
>
Co-authored-by: NAME <name@email.com>
Co-authored-by: OTHER-NAME <other@email.com>"
```
### 4. Checking the Status
You can check the status of your repository to see which files have changed and which are staged for commit:
```git status```

### 5. Viewing Commit History
To see the commit history of your project, run:
```git log```

## Branching and Merging
### 1. Creating a Branch
A branch allows you to work on different versions of your project simultaneously. To create a new branch:
```git branch my-new-branch```

### 2. Switching Branches
To switch to a different branch:
```git checkout my-new-branch```

### 3. Merging Branches
Once your work is complete on a branch, you can merge it back into the main branch:

Switch to the main branch:
```git checkout main```

Merge your feature branch:
```git merge my-new-branch```

## Working with Remotes
Git allows you to work with remote repositories (like those on GitHub). Here are some important commands:

### 1. Adding a Remote Repository
To link your local project with a remote repository, add a remote URL:

```git remote add origin https://github.com/username/repository.git```

### 2. Pushing Changes to Remote
After committing changes, you can upload them to your remote repository (GitHub):
```git push origin main  # Push to the 'main' branch ```

### 3. Pulling Changes from Remote
To download the latest changes from the remote repository:

```git pull origin main```

## Common Git Commands Summary

| Command                      | Description                                        |
|------------------------------|----------------------------------------------------|
| `git init`                   | Initializes a new Git repository                   |
| `git clone <url>`            | Clones an existing repository                      |
| `git status`                 | Shows the status of your files in the working tree |
| `git add <file>`             | Stages a file for commit                           |
| `git commit -m "message"`    | Commits changes with a message                     |
| `git log`                    | Shows the commit history                           |
| `git branch`                 | Lists, creates, or deletes branches                |
| `git checkout <branch>`      | Switches to a specific branch                      |
| `git merge <branch>`         | Merges the given branch into the current branch    |
| `git push origin <branch>`   | Pushes the current branch to the remote repository |
| `git pull origin <branch>`   | Pulls the latest changes from the remote repository|

## Ignoring Files with .gitignore

Teach Git which files and/or directories in your project should be automatically ignored in version control by creating a hidden file called ```.gitignore```.
The ```.gitignore``` is a simple text file that tells Git which files and folders to exclude from version control, keeping your repository clean, organized, and secure.

### Quick Guide to Create a .gitignore in VS Code:
Open the Project Folder: Launch VS Code and navigate to your project's root folder.
Create the ```.gitignore``` File: Go to "File" > "New File", name it .gitignore, and press Enter.
Add Ignore Patterns: List the files or folders to ignore, one per line. For example:
node_modules/: Ignore Node.js modules.
