---
title: "Git Workshop"
author: Simon Schug
date: 26. April 2019
---
# I. Introduction {data-background=#FF4081}

## Why are you here?
<a href="https://xkcd.com/1597/"><img src="https://imgs.xkcd.com/comics/git_2x.png" alt="xkcd-1597" width="40%"/></a>

<aside class="notes">

- Git is powerful, but with great power comes great complexity
- Git is primarily used on the command line (although GUIs and web interfaces exist)
- Git has a little bit of a learning curve, but today we will tackle it
</aside>

## What is git?

<img src="./figures/git.svg" alt="git-logo" width="15%"/>

[Version Control System](https://en.wikipedia.org/wiki/Version_control) for tracking changes in files.

>- Unlimited undo for your files using snapshots 📸️
>- Distributed repositories - online and offline 🌍️
>- See who made what changes when and why 👀️

<aside class="notes">
- You decide when to take a snapshot 💪️
- Many people can work in parallel  👨‍👩‍👧‍👦️
- You can use it as your personal lab notebook

</aside>

## Why do you need it?
<a href="http://phdcomics.com/comics/archive.php?comicid=1531"><img src="http://phdcomics.com/comics/archive/phd101212s.gif" alt="phd_comics-1531" width="40%"/></a>

<aside class="notes">
- Collaborating without git: taking turns or excessive communication with duplicates, lost and overlooked things
- Hosted repositories can be turned into citable objects. The conceptual stages of your work are transparently documented, including who did what and when.
</aside>

# II. Setup {data-background=#FF4081}

## Linux 🐧️
You are nearly done 🍵️.

1. Run the following command in a terminal:
```
sudo apt install git-all # Ubuntu / DEB-based
sudo dnf install git-all # Fedora / RPM-based
```
2. Read [a short history of git](https://git-scm.com/book/en/v2/Getting-Started-A-Short-History-of-Git)

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
	- Open the dmg and right-click open the *.pkg to install
	- Open a terminal & check if it works by entering `git`

## Quick Bash Primer
Some useful commands to get started with Bash 🤖️

- `pwd` to print the working directory
- `cd <folder>` to change the working directory
- `ls` to list files/folders
- `mkdir` to make a new directory
- `nano <filename>` as a simple text editor
- `man <command>` reference manual


# III. Version Control {data-background=#FF4081}

## Configuring git
Since this is your first time with git, tell it who you are 🙋️
```
git config --global user.name "Your Name"
git config --global user.email "youremail@email.com"
```
which [text editor](https://swcarpentry.github.io/git-novice/02-setup/index.html) ✍️ you prefer
```
git config --global core.editor "nano"
```
and check ☑️ if everything is set up properly
```
git config --list
```

## Creating a local repository
Creating a local git repository is easy 👯️

1. Create a new directory for the repository
2. Change into the newly created directory with `cd`
3. Run `git init` to initialize the repository
4. Check the status of the repository with `git status` 
\

> _Where does git store its information?_\
> _Which files & folders will it track?_


## Tracking changes I
<img src="./figures/git_tracking-changes.svg" alt="tracking-changes" width="130%"/>
_Commits with small changes are easier to read & review_ 💡️.

<aside class="notes">

- Think of git as taking snapshots of changes over the life of a project.
- `git add` specifies what will go in a snapshot by putting things in the staging area
- `git commit` takes the snapshot, and makes a permanent record of it
- You could use `git commit --all`, but it’s almost always better to explicitly add things to the staging area to avoid committing changes you forgot you made.

</aside>

## Tracking changes II
Let's go through the [modify-add-commit cycle](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository) 🌀️

1. Create/Change files & folders within your new repository
2. Add files/folders you want to track: `git add filename`
3. Record changes as a commit:\
`git commit -m "Meaningful commit message"`
4. Repeat 🔁️

> Use `git status` to monitor the current status of your repository. What tricks does it tell you?

## Ignoring things
Files you don't want to track can be ignored 😑️

- Create a .gitignore text file
- Add `files`, `folders/` or whole patterns `*.dat`
- Exclude specific files from being ignored with `!filename `

> For common use-cases prefabricated .gitignore files most likely already exist, e.g. check <span style="background:rgba(21.2, 21.2, 21.2, 0.8)">.[gitignore.io](https://www.gitignore.io/)</span>.

## Exploring history
How can you see the tracked changes 👁️? 

- `git log` shows the commit history of the repository
- `git diff` shows changes within files
- Use commit IDs to compare between specific commits

> The most recent commit is referred to by the identifier `HEAD`. What does `git diff HEAD~2` do?
 
<aside class="notes">
Git log:

- Limit log size with `-3` and show diffs with `-p`
- Press `/` and type something to search. Navigate with `N`

git diff:

- `--color-words` shows changes on word level
- `--staged` shows changes between staging area and repository
- Compare two commit ids: `git diff b12a52e a983d1 -- [filename]`

A Git commit ID is a SHA-1 hash of every important thing about the commit, e.g.:

- A checksum of the tree contents
- The parent commit id (if this is a merge, there will be more parents)
- The author of the commit with timestamp
- The committer of the commit with timestamp
- The commit message

</aside>

## Alternate realities I
<img src="./figures/branches.svg" alt="tracking-changes" width="100%"/>
_Branch operations are inexpensive in git_ 💸️.

<aside class="notes">

- A branch represents an independent line of development. 
- You can think of them as a way to request a brand new working directory, staging area, and project history.
- Example: Using a branch for a new feature for the data analysis. When an urgent error is discovered, you can just switch the branch to fix it in your original data analysis
</aside>

## Alternate realities II
Exploring an idea without changing the main project 💫️

- Use `git branch <new-branch>` to create a new branch
- Switch to it with `git checkout <new-branch>`
- Switch back to master and merge your changes with\
`git merge <new-branch>`

> What happens when both the master and the branch change the same part of a file?

## Conflicting realities
Merge conflicts can arise when the same file is changed in multiple branches ⚔️

- Create a merge conflict between two branches
- Resolve the conflict manually and look at the resulting graph with `git log --graph`
- See [Stackoverflow](https://stackoverflow.com/questions/161813/how-to-resolve-merge-conflicts-in-git) for information on mergetools

## Avoiding conflicts
Resolving conflicts takes time, try to avoid them ✋️

1. Modularize your files into smaller ones
2. Make smaller and more atomic commits
3. Use separate branches to segregate work

## Time traveling
_Oops I made some bad choices, how can I go back in time?_ 🕓️

- Revert a single file (**this deletes non-commited changes**❗️) with `git checkout <commit-id> <filename>`
- Time travel with all files using\
`git checkout -b <new-branch> <commit-id>`
- Careful, don't use `git checkout <commit-id>`. It will make you [loose your HEAD](https://www.git-tower.com/learn/git/faq/detached-head-when-checkout-commit)

> What is the detached HEAD state? How can you avoid it?

<aside class="notes">
In 'detached HEAD' state you can look around, make experimental changes and commit them without impacting any branches (i.e. commits are not recorded (but they exist)).

Since files can be reverted individually, it makes sense to heavily modularize your work.
</aside>

## Basic git commands
```
git init		// Initialize local git repository
git status		// Check status of working tree
git add			// Add file(s) to staging area
git commit		// Commit changes to repository
git log			// Show commit logs
git diff		// Show changes between commits
git branch		// Create, list and delete branches
git checkout	// Switch branches or restore files
```
Get a more elaborate git cheat sheet from [GitHub Help](https://github.github.com/training-kit/). 


# IV. Collaboration {data-background=#FF4081}

## Hosting services
To collaborate with others we need a remote 🌐️

- [GitHub](https://github.com/) is the de facto standard with a big community
- [GitLab](https://gitlab.com/) is an open source alternative often preferred for self-hosted instances

> Both offer many additional features like permission management, issue tracking, pull requests...

<aside class="notes">
Version control comes into its own when we collaborate with others 
</aside>

## Setting up GitHub
We use [GitHub](https://github.com/) for the demonstration 🐈️

- Sign up on GitHub
- _Optional_: [Keep your email address private](https://help.github.com/en/articles/setting-your-commit-email-address-on-github)
- _Optional_: [Set up SSH](https://help.github.com/en/articles/connecting-to-github-with-ssh)


## Create a remote repository
Create a new, empty repository on GitHub 👶️

- Connect your local repository to the new remote with\
`git remote add origin <url>`
- Push your local changes to the remote with `git push -u origin master`
- Create and edit the README file, it uses [Markdown](https://guides.github.com/features/mastering-markdown/) syntax

> Repositories should contain a license to handle copyright. <span style="background:rgba(21.2, 21.2, 21.2, 0.8)">.[choosealicense](https://choosealicense.com/)</span> can help you.

## Push & Pull
To synchronize changes in the local and the remote repository, you can use push & pull 🏋️

- Change the README in the web interface and use\
`git pull origin master` to copy the changes into your local repository
- Commit a local file change and push it to the remote using `git push origin master`


> While `git commit` only updates your local repository, `git push` updates the remote with the local changes. 

## Pull requests
With pull requests, you can propose changes to a repository and ask someone to review, pull and merge your contribution 💌️

- Create a new branch via the web interface and try to discover it locally with `git fetch` && `git branch -r`
- Check out the new branch locally by creating a new local branch with the same name: \
`git checkout -b <branch> <remote>/<branch>`
- Push local changes to the remote and perform a pull request via the web interface

<aside class="notes">
If someone wants to know about the different merge possibilities, this is what [Stackoverflow](https://stackoverflow.com/questions/2427238/in-git-what-is-the-difference-between-merge-squash-and-rebase) has to say.
</aside>

## Basic Collaborative Workflow
You are now ready to collaborate with others using git 🏁️

0. Retrieve an existing, hosted repository with `git clone`
1. Update your local repository with `git pull`
2. Make local changes and stage them with `git add`
3. Commit your changes with `git commit`
4. Upload the changes to the remote with `git push`


# +++Moooore {data-background=#FF4081}

## There is...
... so much more to discover 🔭️

- Many text editors and IDEs have a deep git integration
- GitHub/GitLab integrate many more tools to simplify collaboration: Issue tracker, wiki's, website hosting
- [Numerous GUI's](https://en.wikipedia.org/wiki/Comparison_of_Git_GUIs) try to streamline your git experience

> You are prepared to discover those things on your own 🚀️
