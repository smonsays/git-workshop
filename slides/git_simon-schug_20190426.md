---
title: "Git Workshop"
author: Simon Schug
date: 26 April 2019
---

**TODO** YOU vs WE

# I. Introduction {data-background=#FF4081}

## What is git?

<img src="./figures/git.svg" alt="git-logo" width="15%"/>

[Version Control System](https://en.wikipedia.org/wiki/Version_control) for tracking changes in files.

>- See who made what changes when 👀️
>- Revert back at any time 🕓️
>- Collaborate with others (even yourself) 🤝️


## Concepts

- Keep track of file history by taking snapshots 📸️
- You decide when to take a snapshot 💪️
- Repositories can be used locally or with a server 🌐️

## Organized version control
Overcome

> document_2019_final_FINAL!!.docx

- Good integration into common editors (Rstudio, vscode, PyCharm, etc.)

## Collaboration
Stop sending code per mail to collaborators

> Please find attached code_v3.zip




# II. Setup {data-background=#FF4081}

## Linux 🐧️
You are probably already done 😎️.

1. Open a terminal
2. Enter the command `git`
3. If the command was not found install git:

```
# e.g. under Ubuntu / Debian
sudo apt install git
```

## Windows 🏢️
You have 2 options:

1. [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) (only Windows 10)
	
	- This will install a Linux distribution within Windows
	- You can use the Linux instructions to install git

2. Use the standalone [*.exe installer](https://git-scm.com/downloads)

	- Download latest source release for Windows
	- Step through the installer (keep defaults)

## Mac OS 🍎️
You have 2 options:

1. Use [brew](https://brew.sh/) (_preferred_ 👍️)

	- Install brew as outlined in section _Install Homebrew_
	- Enter `brew install git` into the terminal
	- Check if it works by entering `git`

2. Use the [*.dmg installer](https://git-scm.com/downloads)

	- Download latest source release for MacOS
	- Open the dmg and right-click open the *pkg to install
	- Open a terminal & check if it works by entering `git`

## Quick Bash Primer
Git is primarily used in the command line (Bash). To get started, here are some useful commands:

- `pwd` to print the working directory
- `cd [folder]` to change the working directory
- `ls` to list files/folders
- `mkdir` to make a new directory
- `nano [filename]` as a simple text editor


# III. Version Control {data-background=#FF4081}

## Configuring git
Since this is our first time with git, we tell it who we are 🙋️:
```
git config --global user.name "Your Name"
git config --global user.email "youremail@email.com"
```
which text editor ✍️ we prefer:
```
git config --global core.editor "nano"
```
and check ☑️ if everything is set up properly:
```
git config --list
```

## Creating a local repository
Creating a local git repository is easy 👯️:

1. Create a new directory for the repository
2. Change into the newly created directory with `cd`
3. Run `git init` to initialize the repository
4. Check the status of the repository with `git status` 
\

> _Where does git store its information?_\
> _Which files & folders will it track?_


## Tracking changes I
<img src="./figures/git_tracking-changes.svg" alt="tracking-changes" width="130%"/>
_Commits with small changes are easier to read & review_ 💡️

<aside class="notes">
- Think of git as taking snapshots of changes over the life of a project.
- `git add` specifies what will go in a snapshot by putting things in the staging area
- `git commit` takes the snapshot, and makes a permanent record of it
- You could use `git commit --all`, but it’s almost always better to explicitly add things to the staging area to avoid committing changes you forgot you made.
</aside>

## Tracking changes II
Let's go through the [modify-add-commit cycle](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository) 🌀️:

1. Create/Change files & folders within your new repository
2. Add files/folders you want to track: `git add filename`
3. Record changes as a commit:\
`git commit -m "Meaningful commit message"`
4. Repeat 🔁️

> Use `git status` to monitor the current status of your repository.

## Ignoring things
Files you don't want to track can be ignored 😑️.

- Create a .gitignore text file
- Add `files`, `folders/` or whole patterns `*.dat`
- You can exclude certain files from being ignored `!final.dat `

## Exploring history
How can we look at all the tracked changes? 👁️

- Use `git log` to look at the repository's history 
- Change something in a file and try `git diff`
- Commits can be referred to using its ID. Try comparing a file to a specific commit.

> The most recent commit is referred to by the identifier `HEAD`. What does `git diff HEAD~2` do?
 
<aside class="notes">
- Limit log size with `git log -3` and show diffs with `-p`
- Press `/` and type something to search. Navigate with `N`
- `git diff --color-words` shows changes on word level
- `git diff --staged` shows changes between staging area and repository
- Use only first few characters to compare to commit, e.g. `git diff b12a52e [filename]`

A Git commit ID is a SHA-1 hash of every important thing about the commit, e.g.:

- A checksum of the tree contents
- The parent commit id (if this is a merge, there will be more parents)
- The author of the commit with timestamp
- The committer of the commit with timestamp
- The commit message

</aside>

## Alternate realities
**TODO** branches!


## Time traveling
**TODO: Exploring history done?**
_Oops_ I made some bad choices, how can I go back in time? 🕓️

- Can revert a single file (careful❗️) with\
`git checkout [commit-id] [filename]`
- Time travel with all files using\
`git checkout -b [new-branch] [commit-id]`
- Careful, don't use `git checkout [commit-id]`. It will make you [loose your HEAD](https://www.git-tower.com/learn/git/faq/detached-head-when-checkout-commit)

> What is the detached HEAD state & how can you avoid it?

<aside class="notes">
You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

`git checkout -b <new-branch-name>`

</aside>

## Basic git commands
```
git init				// Initialize local git repository
git status				// Check status of working tree
git add [filename]		// Add file(s) to staging area
git commit -m "message"	// Commit changes to repository
git log					// Show commit logs
git diff				// Show changes between commits
```
Get a more elaborate git cheatsheet from [GitHub Help](https://github.github.com/training-kit/). 


# IV. Collaboration {data-background=#FF4081}

## Git-repository hosting services
- Github vs. Gitlab
- Self-hosting

## Create a remote repository

## Choose a license
- Public work should transparently handle copyright with a license
- You are not a lawyer? Don't write your own!
- Flavors of Open Source: [choosealicense.com](https://choosealicense.com/) helps


## Create a readme
- Markdown 

## Setup SSH keys
- SSH keys

## Push & Pull

## Conflicts
- When multiple people change the same file simultaneously, conflicts can arise
- Resolve overlapping changes
- [StackOverflow Help](https://stackoverflow.com/questions/161813/how-to-resolve-merge-conflicts-in-git)

## Open Science
Open scientific work is more useful and more highly cited than closed.
- How to handle citations


# +++Moooore (Optional) {data-background=#FF4081}

## Git in RStudio
- Rstudio projects automatically handle git repositories

## Issues tracker

## Wiki

## Github pages
