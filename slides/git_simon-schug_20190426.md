---
title: "Git Workshop"
author: Simon Schug
date: 26 April 2019
---

# I. Introduction {data-background=#FF4081}

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

1. Go to [git-scm.com](https://git-scm.com/downloads)
2. Download latest source release for Windows
3. Step through the installer (keep defaults)
\

> In case the _Windows Subsystem for Linux_ is installed, you could also use the Linux instructions (it's up to you 👈️).

## Mac OS 🍎️
You have 2 options:

1. Use [brew](https://brew.sh/) (_preferred 👍️_)

	- Install brew as outlined in section _Install Homebrew_
	- Enter `brew install git` into the terminal
	- Check if it works by entering `git`

2. Use the [*.dmg installer](https://git-scm.com/downloads)

	- Download latest source release for MacOS
	- Open the dmg and right-click open the *pkg to install
	- Open a terminal & check if it works by entering `git`

## Quick Bash Primer
Git is primarily used in the command line (Bash). To get started, here are some useful commands 

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
Creating a local git repository is easy:

1. Create a new directory for the repository
2. Change into the newly created directory with `cd`
3. Run `git init` to initialize the repository
4. Check the status of the repository with `git status` 
\

> _Where does git store its information?_\
> _Which files & folders will it track?_


## Tracking changes I
<img src="./figures/git_tracking-changes.svg" alt="tracking-changes" width="130%"/>
Commits with small changes are easier to read & review💡️

## Tracking changes II
Let's go through the [modify-add-commit cycle](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository):

1. Create/Change files & folders within your new repository
2. Add files/folders you want to track: `git add filename`
3. Record changes as a commit:\
`git commit -m "Meaningful commit message"`

> Use `git status` at every step to monitor what happened

## Traveling back through time

- git checkout
- git diff
- gitk/gitg/github-desktop

## Ignoring things

- Use the .gitignore file to ignore certain files/folders

## Summary of basic git commands



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
