---
title: "Git Workshop"
author: Simon Schug
date: 26 April 2019
---

# I. Introduction {data-background=##FF4081}

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


# III. Version Control {data-background=#FF4081}

## Setting up git

## Creating a local repository

- git init


## Tracking changes
- Many commits with smaller changes are easier to read and review

## Traveling back through time

- git checkout
- git diff
- gitk/gitg/github-desktop

## Ignoring things

- Use the .gitignore file to ignore certain files/folders





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
