<p align="center">
    <a href="http://files.zeroturnaround.com/pdf/zt_git_cheat_sheet.pdf">
    <img src="images/git_logo.png" >
    <br>#Learn Git
    </a>
</p>

- [Introduction](#introdunction)
- [Configuring Git](#configuring-git)
- [New Local Repository](#new-local-repository)
- [Common Commands](#common-commands)
- [More commands](#more-commands)
- [Create repository](#create-repository)
- [Clone repository](#clone-repository)
- [Submit changes](#submit-changes)
- [Rebase](#rebase)
- [Revert changes](#revert-changes)
- [Stashing](#stashing)
- [Merge branch](#merge-branch)
- [Create a new branch and upstream it](#create-a-new-branch-and-upstream-it)
- [Troubleshoot](#troubleshoot)

## Introduction
- Version control system
A Version control system tracks any kind of changes made to the project file, why these changes were made and references to the problems fixed or enhancements introduced. It allows developer teams to manage and track changes in code over time. It allows a person to switch to the previous states of the file, compare the versions and helps to identify issues in a file in a more efficient way.
- Git (A Version control system)
Git is a distributed version control system (DVCS). **"Distributed"** means that all developers within a team have a complete version of the project. A version control system is simply software that lets you effectively manage application versions. Thanks to Git, you'll be able to do the following:
    - **Keep track of all files in a project**
    - **Record any changes to project files**
    - **Restore previous versions of files**
    - **Compare and analyze code**
    - **Merge code from different computers and different team members.**

These capabilities listed above don't tell how Git actually works, however. In all its complexity, Git works quite simply: you first need to create a local repository in your project's root directory (folder). Afterwards, Git can track project files and directories and add them to the repository. You may be thinking, "Not again! We're talking about a repository now?

A repository is just a directory (a folder) in your project's root directory.**Note:** Throughout the entire article we'll use the term directory, not folder. You can't see repositories in your filesystem as they're hidden. But you can still see a repository in your code editor or IDE:

**What's a local repository?**
If you store your code at on a computer with a Git directory, you store your stuff locally. So a repository on your own computer will be called local. A remote repository is like a public storehouse located in a different building. You may have heard about remote repositories such as GitHub, BitBucket, and GitLab. They're like storehouses for code. **Note:** you can copy your entire project to a remote repository while keeping it in a local repository as well.

## Configuring Git

After Installing the git, we can customize it’s environment accordingly. The customization shall be done on any given computer. Git comes with a tool called git config that helps to set configuration variables, that looks after operation of git. In order to set these configuration values as global, add the –global option, and if you omit –global option, then your configurations are specific for the current Git repository.

When you come to a bank for the first time and ask to store your money there, they give you a bunch of paperwork to fill out. Before you can use banking services, you have to register with the bank. Git wants you to do the same (register with Git) before you start using a repository.

Setting your username

$ git config --global user.name "xxxxx1234"

Setting your email-id

$ git config --global user.email boy1234@xyz

## New Local Repository
- Now that you’re ready, you can return to the main GitHub page and click on the “+” icon in the menu bar.
- Once you click on this button, a new menu appears with a “New repository” entry. Click on it!
- The repository creation page will appear. Choose a cool name for your first repository and put a small description before               clicking on the “Create repository” button.
- Well done! Your first GitHub repository is created. If you want to see all your repositories, you need to click on your profile picture in the menu bar then on “Your repositories”.
- A local version of your project

    - Your first mission is to get a copy of the repository on your computer. To do that, you need to “clone” the repository. On        the repository page, you need to get the “HTTPS” address.
    - Once you had the address of the repositories, you need to use your terminal (through shell commands) to move in the place where you want to put the directory copy (for example you can move in your “Documents” folder). When you are ready, you can enter:
    - $ git clone [HTTPS ADDRESS]
    - **Note:** When you clone, Git will create a repository on your computer. If you want, you can access your project with the computer user interface.

## Common Commands

All commands should be run without the <> brackets

- `git log` shows commit ids. The latest commit is at the top.
    - `git log -p` - lists the changed files
- `git checkout -b develop` checks out a new branch called "develop"
    - `git checkout init_devices` switches branch to _init_devices_
    - `git checkout <commit_number>` goes to a specific commit
    - `git checkout -b 1234 origin/mainline` checks out a new branch called "1234", that "tracks" origin/mainline, meaning "local branch has its upstream set to a remote branch" ([Reference](https://stackoverflow.com/questions/10002239/difference-between-git-checkout-track-origin-branch-and-git-checkout-b-branch)). Here's more info: [Tracking branches](https://stackoverflow.com/questions/4693588/what-is-a-tracking-branch)
- `git status` lists new or modified files not yet committed
- `git diff <commit_number>` compares current code to any commit
- `git add *` adds all files to "Staging". Ready for commit
    - `git add <file>` adds a specific file to "Staging". Ready for commit.
- `git commit -m "Put Message Here"` commits locally
    - `git commit --amend`" updates commit by amending your new changes to it. Must run after "add" command.
    - `git commit --amend -m "an updated commit message"` updates the commit, and its commit message.
- `git branch` says which branch we're on
- `git push` pushes code to the branch we're on
    - `git push origin <my_branch>` pushes to specific branch. I think origin is a keyword.
 [Reference](https://www.digitalocean.com/community/tutorials/how-to-use-git-branches)
- `git pull` pulls all changed files

## More commands

- `git rm <file>` removes file from server (Must then do a commit, then push)
- `git ls-files | xargs wc -l` counts # of lines of code in a github repo. [Link to Repo](https://gist.github.com/mandiwise/dc53cb9da00856d7cdbb)
- `git config --global --edit` Edit git commit signature
- `git branch -d the_local_branch` Removes local branch. [Link](https://makandracards.com/makandra/621-git-delete-a-branch-local-or-remote)
- `git rebase -i HEAD~3` combines the last 3 commits into 1 commit. Called [Squashing Commits](http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html).
- `git reset filename.txt` undoes adding a file.


## Create repository

1. In command line, type `git init <project name>` to create a folder that's a Git repo.
1. Add the repository to Github Desktop and push it through Github Desktop.

    The "init" command stands for initialize. Once you run "git init", Git will initialize a hidden directory called ".git" in the project's root directory. And you'll get a confirmation that your deposit box is ready! What's next? You might want to know the status of your box: does it store anything yet? To know the Git status, you'll need to run:
    You'll run the command "git status" quite often. It's the same as calling a bank administrator to check if your things arrived or if anything has been moved to a different vault

## Clone Repository
"clone" is a simple command. We only need to pass it a link to the GitHub project. We've used an SSH link, but you can use the HTTPS link with the same command.

What "git clone" does is it copies the entire project to a directory on your computer. The directory will be created automatically and will have the same project name as the remote repository.

If you don't like the name of the repository you're cloning, just pass your preferred name to the command:
- `git clone https://github.com/noahprince22/GridWorldMDP.git` - clones repository and puts into same folder that command is run from. Repository will be in GridWorldMDP folder
- `git clone https://github.com/noahprince22/GridWorldMDP.git putIntoThisFolder` - same as above but puts GridWorldMDP repository into _putIntoThisFolder_.

So far, you've pushed your changes from a local repository to a remote repository and cloned a remote repository. We haven't said anything about the "pull" command, though. Pushing changes to GitHub or BitBucket is great. But when other developers push their changes to a remote repository, you'll want to see their changes on your computer. That is, you'll want to pull their code to your local repository. To do so, run the following command:

$ git pull

Running "git pull" is enough to update your local repository

## Submit changes
Let's start with a quick overview of committing to the Git repository. By now, you should have at least one file tracked by Git (we have three). As we mentioned, tracked files aren't located in the repository yet. We have to commit them: we need to carry our basket with stuff to the lock box. There are several useful Git commands to do (almost) the same: move (commit) files from the staging area (an imaginary basket) to the repository (a lock box).

To commit to a repository, use the "commit" command. Next, pass the "commit" command the "-m" option, which stands for "message". Lastly, type in your commit message. We wrote "Add three files" for our example, but it's recommended that you write more meaningful messages like "Add admin panel" or "Update admin panel". Note that we didn't use the past tense! A commit message must tell what your commit does – adds or removes files, updates app features, and so on.


1. `git status` to list new or modified files not yet committed
1. `git add <file>`
1. `git commit -m "<commit message>"`
1. `git push` to push the code to the repository. If it fails since code needs to be pulled first, do:
    1. `git pull` - this will do a `git fetch` and a `git merge`. (assuming no merge conflicts, go onto next steps)
    1. `git push`


## Revert changes

1. `git revert <commit_number>`
1. then `:wq` to save in VIM
1. then rebase


## Rebase

#### Rebasing with Merge Conflicts

1. Commit my code on mainline
1. `git pull --rebase`
1. If merge conflicts, read the super-helpful tips in terminal. Basically just
    1. Do a `git diff` to resolve the merge conflicts I have
    1. I think next do a `git rebase --continue`

#### Head is not on main branch - Put changes on top of head

Somewhat useful [tutorial for git pull](https://www.atlassian.com/git/tutorials/syncing#git-remote)

1. Do a `git log` to get the commit number corresponding to the changes you made. Save it for step 5.
1. Get the branch we need. Try: `git pull origin <branch_name>` or  `git checkout <branch>`
1. Do `git branch` to make sure we're on correct branch
1. Do `git reset --hard <commit_number>` using the actual 7-digit (or full) commit number, to put changes on top of branch we just switched to. Use commit number from step 1.
1. If not on latest commit, do a `git pull --rebase`. Note: this command doesn't create a merge commit, so it makes other people's code diverge from what they had.


## Stashing
A staging step in git allows you to continue making changes to the working directory, and when you decide you wanna interact with version control, it allows you to record changes in small commits.
Suppose you have edited three files (a.html, b.html, and c.html). After that you need to commit all the changes so that the changes to a.html and b.html were a single commit, while the changes to c.html were not logically associated with the first two files and were done in a separate commit.

In theory you can do the following:
git add a.html
git add b.html
git commit -m "Changes for a and b"

git add c.html
git commit -m "Unrelated change to c"

Separating staging and committing, you get the chance to easily customize what goes into a commit.

- `git stash` - moves your changes to a stash (a location where changes can be saved)
- `git stash save "Custom Message"` - stashes changes, with custom message.
- `git stash apply` - applies saved changes to your branch. Code also stays in stash.
- `git stash pop` - applies saved changes to your branch. Code is removed stash.
- `git stash show stash@{1} -p` - shows diff for stash@{1} (the 1st entry in the stash). Remove the `-p` to get abbreviated diff.
- `git stash list` - shows all stashes.
- [More stash commands](https://www.atlassian.com/git/tutorials/saving-changes/git-stash), and [even More stash commands](https://medium.freecodecamp.org/useful-tricks-you-might-not-know-about-git-stash-e8a9490f0a1a)

__Stash topmost commit__

1. `git reset HEAD^` - basically like an uncommit
1. `git stash` (this may not stash new files. Maybe try "tracking" the new files to see if this works)


## Merge Branch

To merge 1 branch into another, go to the "giving branch" and do a `git pull`. Then go to receiving branch, and run 1 of the following merge commands:
- `git merge <branch_name>` - Run this from receiving branch. More info [here](https://www.atlassian.com/git/tutorials/using-branches/git-merge)
- `git merge <commit_number_from_another_branch>` - Merges another branch (up to the commit number) into this branch.

## Push and Pull
Git has a "remote" command to deal with remote repositories. But before we jump into an explanation of how the "remote" command works, we have to do a little bit of setup.

First things first, you need to create a remote repository. We'll use GitHub for this section. You can create an account on GitHub and create a new repository for your project. Just start a project and give it a name. You then need to grab the HTTPS link to this new repository. The link will look similar to this – https://github.com/YourUsername/some-small-app.git – where YourUsername will be your GitHub username and "some-small-app.git" will be the name of your app.
Now you need to bind this remote repository to your local repository:
$ git remote add origin https://github.com/YourUsername/some-small-app.git
We tell Git to "add" a repository. The "origin" option is the default name for the server on which your remote repository is located. Lastly, there's a link to your project on GitHub

Once you run the command above, Git will connect your local and remote repositories. But what does this liaison actually mean? Can you already access your code online? Unfortunately, not yet.

All you did for now is signed papers so that the remote lock box (GitHub) can accept various items (your code) from your home drawer (local repository). To actually copy your things to a remote lock box, you need to personally carry them to it. With Git, copying your code to a remote repository looks like this:
$ git push -u origin master
It's obvious that the command "push" tells Git to push your files to a remote repository. What we also specified is the server our local repo is connected to (origin) and the branch we're pushing, which is master. There's also that strange "-u" option. What it means is that we're lazy enough not to run a long "git push -u origin master" command each time we push code to the cloud. Thanks to "-u", we can run only "git push" next time!"

Once you've pushed changes to a remote repository, you can develop another feature and commit changes to the local repository. Then you can push all changes to the remote repository once again, but using only the "git push" command this time around. As we can see, Git tries to simplify things as much as possible.
Is this the happy ending? Not yet. Once you push code to a remote repository, you have to enter your username and password registered with that remote repository.

The current problem with "git push" is that you have to enter your credentials each time you push code to GitHub. That's not convenient. The root of this problem is the HTTPS link you used to connect repositories. Git offers a way out of this inconvenience, however.
As we can see, there's an SSH option that we can use instead of HTTPS. If you set up Git on your computer to work with SSH, then you won't have to enter GitHub credentials every time you push code to GitHub. You'll only need to add a remote origin with this SSH link, like this
$ git remote add origin git@github.com:YourUsername/your-app.git
As you can see, to connect repositories via SSH we only changed the link. Keep in mind that HTTPS is the default protocol used for connecting with GitHub, and you need to manually set up SSH.

Now that you've added a remote repository, you can view the list of repositories by running the following command:
$ git remote -v
The "-v" option will list all remote repositories you've connected to. This is what we've got:
origin	https://github.com/YourName/some-app.git (fetch)
origin	https://github.com/YourName/some-app.git (push)

## Troubleshoot

__"Checkout" or "Pull" not working__

Common mistake is to modify files on local machine, and then try to do a "checkout" or "pull". Problem is the checkout/pull will overwrite what we have. If we do want to OVERWRITE our files, we can erase our changes by typing `git reset --hard HEAD`. Then we can checkout/pull without problems, which gets us the remote files.

## Review for all basic Commands
  - git config --global user.email "jack@gmail.com"
  - git config --global user.name "jackman"
  - 1) git init
  - 2) git add (Filename) || -A
  - 3) git status
  - 4) git commit -m "msg"
  - 5) git remote add origin repoName
  - 6) git push origin (branch name)
  - 7) git clone repoName
  - 8) git pull origin (branch name)

## Links

[Fun way to learn git](https://learngitbranching.js.org)
