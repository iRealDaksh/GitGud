# GitGud

## Index

- [GitGud](#gitgud)
  - [Index](#index)
  - [Why use git/github or version control](#why-use-gitgithub-or-version-control)
  - [Getting started with github](#getting-started-with-github)
    - [Create a github account](#create-a-github-account)
    - [How to install git](#how-to-install-git)
    - [How to setup remote access on github](#how-to-setup-remote-access-on-github)
  - [Making your first commit](#making-your-first-commit)
    - [How to make a github repository](#how-to-make-a-github-repository)
    - [Necessary git commands](#necessary-git-commands)
    - [Begin working on the repository](#begin-working-on-the-repository)
    - [What if you already have code written?](#what-if-you-already-have-code-written)
  - [Making your first open source contribution](#making-your-first-open-source-contribution)
  - [Merge and Rebase](#merge-and-rebase)
    - [Git Merge](#git-merge)
    - [Git Rebase](#git-rebase)
  - [FAQs](#faqs)
  - [What we learnt](#what-we-learnt)

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

| Command                  | Description                                                                                                                              | Example                                                          |
| :----------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------- |
| init                     | initializes a new git repository in current directory                                                                                    | `$git init`                                                      |
| clone \[repo url\]       | create a local copy (clone) of an existing repository                                                                                    | `$git clone https://github.com/<username>/<repository-name>.git` |
| add \[file(s) \| <.>\]   | adds file changes to the staging area so that they can be committed                                                                      | `$git add file1 file2 folder`                                    |
| commit -m \<message\>    | records changes to the repository, creating a new commit with a descriptive message                                                      | `$git commit -m "Placeholder message"`                           |
| status                   | displays the current state of the repository, including changes that have been staged or not staged for commit, untracked files and more | `$git status`                                                    |
| log                      | displays a chronological list of commits in the repository, showing commit hashes, authors, dates, and commit messages                   | `$git log`                                                       |
| branch                   | creates a new branch with the specified name. branches allow for parallel development and isolation of features or fixes                 | `$git branch <branch-name>`                                      |
| checkout \<branch-name\> | switches to a different branch or a specific commit, updating the working directory to match the state of the chosen branch or commit    | `$git checkout <branch-name>`                                    |
| pull                     | fetches changes from the remote repository and merges them into the current branch                                                       | `$git pull`                                                      |
| push                     | uploads local changes to the remote repository, making them accessible to others                                                         | `$git push`                                                      |

### Begin working on the repository

1. Clone the repository `$git clone https://<username>//<username>.git`
2. Open the repository and the README.md in your favorite text editor
3. Make changes, example add a description of yourself
4. Add the file to staging `$git add README.md`
5. Add a descriptive commit message `$git commit -m "Update readme"`
6. Push the repository to github `$git push`

### What if you already have code written?

There are times when you have already written down some code so cloning a repo then adding your changes becomes a pain. Thats where `git init` command shines.

Here's how you initialize a git repo locally and then add it globally to github.

1. Go to any folder which you want to make a git repo of
2. Type in `git init .` this should make the current folder a git repo (adds a .git file)
3. Now go to github and create a black repo
4. Copy its clone link (http/ssh)
5. Come over to where you initialized a new repo and add a new remote

```bash
git remote add origin <url>
```

6. Add, Commit and Push your changes

Now you can use your repo normally like you would anytime else.

## Making your first open source contribution

Head on over to your first open source project called [Introduce Yourself](https://github.com/Aditya-Jyoti/Introduce-Yourself/) and read its [CONTRIBUTING.md](https://github.com/Aditya-Jyoti/Introduce-Yourself/blob/main/CONTRIBUTING.md) file. It should have all instructions provided and should get you started with contributing to that project.

## Merge and Rebase

Pray to god that you don't have to come to this, but now that you have here's what merge hell is

### Git Merge

<p align="center">
<img src="/assets/git-merge.png">
</p>

Think of merging like stacking your new Lego pieces on top of your existing structure.
You keep both the original bricks and the new ones, creating a taller tower.
This is like when you have your main project (let's say a castle), and you want to add a tower (new feature) to it.
You just put the tower on top, and now your castle has a new addition.

**How to git merge?**

1. First move to the branch you want to merge changes into

```bash
git checkout <branch-name>
```

2. Now it is a good practice to fetch your changes

```bash
git fetch
```

The main difference between `git pull` and `git fetch` is that git pull auto merges for you,
hence why it may and may not work during merging.

3. Now merge the branch onto your current branch

```bash
git merge <merging branch>
```

4. Resolve conflicts

- Go to your code and you'll see some arrow `>>>` or `<<<` and equals `===`
- `>>>` means the start of the change
- `<<<` means the end of the change
- Everything on top of the `===` is the content from current branch and everything below is the content from branch being merged.
- delete arrows and equals as you go keeping or removing stuff as you go

5. Add, Commit and Push your changes

### Git Rebase

<p align="center">
<img src="/assets/git-rebase.png" />
</p>

It's like taking your tower apart and rebuilding it with the new pieces added in between.
So, instead of stacking the new pieces on top, you sort them out and insert them into your original tower one by one.
This way, everything stays in order. This is similar to realizing you built your tower (branch)
in the wrong spot, so you take it apart and rebuild it in the right place with
the new pieces added in where they fit better.

**How to git rebase**

1. Set rebase to true

```bash
git config pull.rebase true
```

2. Git pull

- Now you should see a bunch of warnings and it should pop you into rebase mode
- Use `git rebase --continue` to move on to the next commit, if its the end of the rebasing commits then it moves to main
- Use `git rebase --abort` to get back to the state before you ran `git rebase`
- Just like merge go on and keep/remove changes that you want/don't want and keep adding and committing then

3. Once done `git push`

## FAQs

## What we learnt
