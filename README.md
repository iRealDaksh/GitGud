# All about Git and Github

## Index

- [All about Git and Github](#all-about-git-and-github)
  - [Index](#index)
  - [Why use git/github or version control](#why-use-gitgithub-or-version-control)
  - [Getting started with github](#getting-started-with-github)
    - [Create a github account](#create-a-github-account)
    - [How to install git](#how-to-install-git)
    - [How to setup remote access on github](#how-to-setup-remote-access-on-github)
  - [Making your first commit](#making-your-first-commit)
    - [How to make a github repository](#how-to-make-a-github-repository)
    - [Necessary git commands](#necessary-git-commands)

## Why use git/github or version control


## Getting started with github


### Create a github account


**What is "github"?**

GitHub is a web-based platform built around Git, a distributed version control system.
It provides hosting for software development projects using Git repositories and offers a wide
range of features aimed towards collaboration, code review, and project management.

Go to [github](https://github.com) and sign up to create a new account if you don't already have one.

### How to install git


**What is "git?"**

Git is a version control system made to track changes during development of a software based project.
It is used by developers to manage collaboration, different versions of files and much more

**Linux**

Use your respective package managers to install git, for example on debian based systems
`$sudo apt install git-all`

**Windows**

1. Download the installer -> [exe link](https://git-scm.com/download/win)
2. Follow the installation wizard (gui)
3. Set your username and email
   - username: `$git config --global user.username <username>`
   - email: `$git config --global user.email <email>`

_NOTE: Do not change any preset installation setting in the wizard (unless you know what you are doing)_

[reference link](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### How to setup remote access on github


There are two ways of setting up remote access privilege on github HTTP and SSH, but in this session we will be focusing on only one of them, ie, HTTP

**HTTPS**

1. Create a public access key
2. Enable github credential caching `git config --global credential.helper 'cache --timeout=31536000'`
3. Go to settings page (click on user icon on top right then settings)
4. Scroll down till you see developer settings and click on it
5. Go to personal access tokens, then tokens classic
6. Generate a new token, then click classic
7. Give it necessary permissions
8. Copy access token
9. Pull a repo using http, then paste access token when prompted for a password

_NOTE: The access token is only visible once and when the tab is closed its not viewable again so don't forget to save it_

## Making your first commit


For this example we will be creating your own personalized `README.md` file which gets displayed whenever someone views your page.

### How to make a github repository


**What is a "repository"?**

So has everyone use google drive to store things before? Good, a repository is like google drive but for code.
It is a cloud storage space where typically software projects are stored and managed for hosting and collaboration purposes.
Basically it is one big folder filled with code files necessary to make a project work out of the box, so that it becomes easy to share projects with others.

**Steps to create one**

1. Go to your repositories tab -> `https://github.com/<username>?tab=repositories` and click on `New`
2. Name your repository your username, ie for example my repository is called `Aditya-Jyoti` which is my `<username>`
3. Give it a description (optional)
4. Make it public
5. Click on `Add a README file`
6. Select a license (pick MIT)
7. Click on `Create repository`

### Necessary git commands


| Command                | Description                                                                                                                              | Example                                                          |
| :--------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------- |
| init                   | initializes a new git repository in current directory                                                                                    | `$git init`                                                      |
| clone \[repo url\]       | create a local copy (clone) of an existing repository                                                                                    | `$git clone https://github.com/<username>/<repository-name>.git` |
| add \[file(s) \| <.>\]   | adds file changes to the staging area so that they can be committed                                                                      | `$git add file1 file2 folder`                                    |
| commit -m \<message\>    | records changes to the repository, creating a new commit with a descriptive message                                                      | `$git commit -m "Placeholder message"`                           |
| status                 | displays the current state of the repository, including changes that have been staged or not staged for commit, untracked files and more | `$git status`                                                    |
| log                    | displays a chronological list of commits in the repository, showing commit hashes, authors, dates, and commit messages                   | `$git log`                                                       |
| branch                 | creates a new branch with the specified name. branches allow for parallel development and isolation of features or fixes                 | `$git branch <branch-name>`                                      |
| checkout \<branch-name\> | switches to a different branch or a specific commit, updating the working directory to match the state of the chosen branch or commit    | `$git checkout <branch-name>`                                    |
| pull                   | fetches changes from the remote repository and merges them into the current branch                                                       | `$git pull`                                                      |
| push                   | uploads local changes to the remote repository, making them accessible to others                                                         | `$git push`                                                      |
