# Table of Contents

- **[Prelims](#)**
- **[Installing a Git GUI](#)**
- **[Installing Git from CLI](#)**
- **[Fork](#)**
- **[Git Clone](#)**
- **[Markdown](#)**
- **[Git Commands](#)**
- **[The .gitignore File](#)**
- **[Removing Files](#)**
- **[Recovering a file](#)**
- **[Reverting to a Previous Version](#)**
- **[Pushing Commits to your remote repository](#)**
- **[Git Merge vs Git Rebase workflow](#)**
- **[Git cherry-pick](#)**
- **[Pulling Updates from an Upstream remote repository](#)**
- **[Issue Tracker](#)**
- **[Pull Request](#)**
- **[Atom IDE](#)**
- **[Contributors](#)**

<br>
<div align="center">
  <a href="#"><img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Logo.png" alt="placeholder for env. gif" width="200" /></a>
  <a href="#"><img src="https://github.githubassets.com/images/modules/logos_page/Octocat.png" alt="placeholder for env. gif" width="200" /></a>
</div> 
<br>

>The present README is intentionally overkilling for educational purposes. It can be daunting for first-timers. <br />
**A quick walkthrough of [GitHub](https://docs.github.com/en/get-started/quickstart/hello-world) and [Git](https://docs.github.com/en/get-started/using-git/about-git) how-tos for dummies. <br /> For more information, resort to the [full reference guide to Git commands](https://git-scm.com/docs) or the [Git Cheat Sheets](https://training.github.com/).**

<br />
<div align=center>
  <b><a href="https://en.wikipedia.org/wiki/It%27s_dangerous_to_go_alone!">"It's dangerous to go alone! Take this."</a></b>
</div>
<br />


<!--- ############################################################################################################################################### -->


# Prelims

Beware: the angle brackets punctuation mark denoted by "`<>`" (voiced chevrons) is only used as a placeholder, i.e, it's not a special character.

- GitHub: a cloud-based hosting platform running on a server that ues git as its command-line tool.
- Git: an open-source version control that runs on a CLI completely independent of GitHub.

# Installing a Git GUI

One can choose to install a Git GUI in a local machine rather than using Git via Terminal. To this end, simply:

1. Download the [source tree](https://www.sourcetreeapp.com/) application.

# [Installing Git](https://github.com/git-guides/install-git) from the command-line Terminal

For more information, see the [Git from source](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) guide.

## On Windows

1. Download the latest version on [gitforwindows.org](https://gitforwindows.org/);

2. Follow the instructions as provided in the Git Setup wizard as they appear.

## On Linux

For debian-based distros (Ubuntu/Ubuntu-derivatives):

```sh
sudo apt update && apt install git-all
```

And for your own sanity, install pip (a python package manager):

```bash
sudo apt update && apt install python3-pip && pip -V
```
Note: in pip, the flag `-V` is shorthand for `--version`.

## With Anaconda

1. Download [Anaconda](https://www.anaconda.com/products/individual) latest version;
  - On Windows: follow the installation wizard.
  - On Linux: follow [these steps](https://github.com/QuCAI-Lab/educational-resources/tree/main/Conda_Essentials).
2. With open Anaconda command-line prompt, [simply](https://anaconda.org/anaconda/git):
```sh
conda install -c anaconda git && git --version
```
Note: the `-c` flag (abbreviated from --channel) points to the channel (Anaconda) from which git will be installed.


# [Fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo)

One can choose to make a copy of a public/private GitHub repository from his own [Organization](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/about-organizations) or someone else's GitHub account by clicking on the [Fork](https://github.com/octocat/Spoon-Knife) button. For instance, you can Fork this repository by clicking [here](https://github.com/QuCAI-Lab/educational-resources/fork).

# [Git Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) 

You can set up a Git linkage by cloning your private/public repository to a custom folder/directory of your Local Machine using the Command-line interface ([Unix-like](https://github.com/QuCAI-Lab/educational-resources/tree/main/Linux_Essentials) terminal or [Anaconda environment](https://github.com/QuCAI-Lab/educational-resources/tree/main/Conda_Essentials) prompt with [Git](https://anaconda.org/anaconda/git) installed).

## Git clone with different protocols

- There are four possible [protocol choices](https://git-scm.com/book/en/v2/Git-on-the-Server-The-Protocols): Local, HTTP, Secure Shell (SSH) and Git.
  - Cloning over HTTPS: the protocol uses private key authentication to clone a private repository using a git username and an access token. It is also the git recommend way for cloning public repositories.
  - Cloning with SSH: the protocol uses SSH keys for authentication.

To clone a public repository over HTTPS:
```bash
git clone https://github.com/<github_username>/<public_repo_name>.git
```
To clone a private repository over HTTPS:
```bash
git clone https://github.com/<git_username/private_repo_name>.git
<username>
<token>
```
Hands-on example cloning this public repository over HTTPS:
```bash
git clone https://github.com/qucai-lab/educational-resources.git
``` 

To clone a repository over SSH:
```bash
git clone ssh://<user>@<server>/<project_name>.git
```
or
```bash
git clone <user>@<server>:<git_username>/<repo_name>.git
```
Hands-on example cloning this public repository with a github server over SSH:
```bash
git clone git@github.com:qucai-lab/educational-resources.git
```

# Markdown

After `git clone`, to vizualize a README.md (markdown) file on the web browser, one can use grip via the CLI:
```sh
pip install grip && grip -b README.md
```


<!--- ############################################################################################################################################### -->

# Git Commands

- [git clone](https://git-scm.com/docs/git-clone) - To clone a remote repository into a local (on-prem) directory.
- [git log](https://git-scm.com/docs/git-log) - Show the latest commits (logs) and hash-id.
- [git status](https://git-scm.com/docs/git-status) - Show the working tree (uncommitted files) status of the current GitHub repository.
- [git diff](https://git-scm.com/docs/git-diff) - Show differences/changes between the original file and the new version of said file before track/stage (`git add`) and commit (`git commit`).
- [git restore \<filename1> \<filename2> ...](https://git-scm.com/docs/git-restore) - To discard untracked/unstaged (**before `git add`**) and uncommitted (**before `git commit`**) file changes in the working directory and restore the originals from the index (Git staging area).
- [git add --all](https://git-scm.com/docs/git-add) - To **Track/stage** all changed (or new) files to the staging area/index.
- [git restore --staged \<filename>](https://git-scm.com/docs/git-restore) - Restores a file from HEAD after it has been staged (**after `git add`**) and **before `git commit`**.
- [git fsck](https://git-scm.com/docs/git-fsck) - File system check for dangling blobs (a staged file that was not committed). Used to [restore a file](https://git-scm.com/book/en/v2/Git-Internals-Maintenance-and-Data-Recovery) after it has been staged (**after git add**) and after **hard reset** (`git reset --hard HEAD`) but **before `git commit`**.
- [git show \<id> > <filename>.txt](https://git-scm.com/docs/git-show) - Export/save data of a file change to an external file. Use `git fsck` to find the id.
- [git commit -m "<commit_message>"](https://git-scm.com/docs/git-commit) - Records staged modifications to the local repository and define a message.
- [git checkout \<hash-id>](https://git-scm.com/docs/git-checkout) - [Recovers/restores](https://git-scm.com/book/en/v2/Git-Internals-Maintenance-and-Data-Recovery) a file **after commiting** and hard reset (`git reset --hard HEAD`). Use `git log` to find the hash-id.
- [git reflog](https://git-scm.com/docs/git-reflog) - List the hash-id of current changes.
- [git reflog \<hash-id>](https://git-scm.com/docs/git-reflog) - Recovers/restores a file **after commiting** and hard reset (`git reset --hard HEAD`). Use `git reflog` to find the hash-id.
- [git remote -v](https://git-scm.com/docs/git-remote) - Show the url name of the remote repository. The standard name is "origin".
- [git branch \<newbranch>](https://git-scm.com/docs/git-branch) - Create a new branch named `<newbranch>`.
- [git branch](https://git-scm.com/docs/git-branch) - Show available branches and highlight the current branch.
- [git checkout \<branch-name>](https://git-scm.com/docs/git-checkout) - Switch to an existing branch named `<branch-name>`.
- [git checkout -b \<newbranch>](https://git-scm.com/docs/git-checkout) - Create a new branch named `<newbranch>` and then checkout.
- [git pull](https://git-scm.com/docs/git-pull) - A shortcut for completing both `$ git fetch` and `$ git merge` or `$ git rebase` in the same command. **Make sure to run this command before git push to sync your local clone with the upstream repository.**
- [git push -u origin \<branch-name>](https://git-scm.com/docs/git-push) - Push your changes to a branch named `<branch-name>` from the remote (cloud-based) GitHub repository.
- [git reset](https://git-scm.com/docs/git-reset) - Reverts the **HEAD branch** (current branch).


Note that `$ git checkout -b <newbranch>` is shorthand for:
```sh
$ git branch <newbranch>
$ git checkout <newbranch>
```

<!--- ############################################################################################################################################### -->

# The [.gitignore](https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files) File

The `.gitignore` file instructs Git to ignore/untrack specific files or folders from a project.

- Common special characters:
  - `*` denotes a wildcard match (placeholder).
  - `/` is used to ignore pathnames relative to the .gitignore file.
  - `#` the hash symbol denotes the comment syntax.

- Gitignore Cheat Sheet:
  - `/filename.txt` will ignore a filename.txt file located in the root directory.
  - `filename.txt` will ignore all files (located anywhere) named filename.txt.
  - `filename` will ignore any file or directory named "filename".
  - `.filename` will ignore any file or directory named ".filename".
  - `filename*` will ignore all files and directories starting with "filename".
  - `*.name` will ignore all files (located anywhere) with extension ".name".
  - `!filename.mdv` will ignore all files with extension .md except the filename.md file.
  - `dir/` will ignore all directories named dir and all its contents.

## Adding the .gitignore file

To add a `.gitignore` file to your cloned repository using the command-line interpreter, follow these steps.

1. Navigate to the relative/absolute path of the directory containing the cloned Git repository in your local machine:
```sh
cd ~/<repo_pathname> 
```
2. Create a .gitignore file:
```sh
touch .gitignore
```
or
```sh
cat > .gitignore
```
or simply (to open gedit text editor)
```sh
gedit .gitignore
```
Note: after saving, the file will be hidden by default, to view hidden files type `ll` in the command-line interpreter.

3. Add the file to staging area:
```
git add .gitignore
```
4. Commit changes:

```
git commit -m "<message>" .gitignore
```

- To add a `.gitignore_global` file to all Git repositories cloned in your local machine:

```sh
git config --global core.excludesfile ~/.gitignore_global
```

## Minimal template

```gitignore

# Ignoring files whose filename ends with the suffix ~
*~

# Ignoring text files
*.txt

# Ignoring virtualenv files
.venv
venv/
ENV/

# Ignoring Jupyter Notebook files with extension .ipynb_checkpoints
.ipynb_checkpoints
```

For more .gitignore templates, see the [github/gitignore](https://github.com/github/gitignore) public repository.

<!--- ############################################################################################################################################### -->

# [Removing Files](https://git-scm.com/docs/git-rm)

To remove (delete) multiple files from both your Git repository and the current working directory:

```bash
git rm <filename1> <filename2> <filenameN>
```

To untrack a file or remove a file from the staging area of your remote repository without deleting it from the working directory of your local machine:

```bash
git rm --cached <filename>
```

To override Git **safety check**, use the `-f` or `--force` flag:

```bash
git rm -f <filename>
```

Note: Git **safety check** makes sure that the files on your current branch match those in the staging index.


<!--- ############################################################################################################################################### -->

# Recovering a file

- Suppose one accidentally changed a file, and that change was done before  `git add` and `git commit`. The file could be restored using:

```bash
git restore <filename>
```

- Suppose one accidentally changed a file, and that change was done after `git add` and `hard reset` and before `git commit`. The file could be restored using:

```bash
git fsck >> id
```

```bash
git show <id> > <recovered_file>.txt
```

- Suppose one accidentally changed a file, and that change was done after `git commit` and after `git reset --hard HEAD`. The file could be restored using:

```bash
git checkout \<hash-id>
```
using `git log` to find the hash-id, or via
```bash
git reflog <hash-id
```
using `git reflog` to find the hash-id.

<!--- ############################################################################################################################################### -->
# [Reverting to a Previous Version](https://git-scm.com/docs/git-reset)

- To revert your repository to the last commit:

```bash
git reset HEAD
```

- To revert your repository to a specific version:

```bash
git reset --hard <version_id> 
```
or
```bash
git reset --soft <version_id> 
```

The `--hard` flag resets the **index** (Git staging area) and the working tree (uncommitted files). It discards changes to tracked files (after git add) from `git commit` onwards. Untracked (before git add) files or directories are deleted.

The `--soft` flag resets the **HEAD branch** (current branch) leaving the index and working tree (uncommitted files) unchanged.

- Creating a new branch in a specific version and checking out:

```bash
git checkout -b <newbranch> <version_hash>
```


<!--- ############################################################################################################################################### -->
  
# [Pushing Commits](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository) to your remote repository

Keywords:
- Local repository: a cloned repository on your own computer.
- Remote repository: a repository on a GitHub server.

To push changes to an existing repository on-prem, i.e, from your local cloned repository to a remote repository, run:
```sh
git clone # (Optional) If you haven't cloned the remote repository yet.
git status # (Optional) To show status of the local repository.
git diff # (Optional) To show changes made to the local repository.

git add --all # To add all changes (new/untracked and modified files) to the Git staging area.
git commit -m "<commit_message>" # To define the topic of your commit.
git push -u origin <branch-name> # Push local changes to the <branch-name> branch of the remote repository.
```

- Get your password (access token) at: `Settings` >> `Developer settings` >> `Personal access tokens` >> `Generate new token` >> `Select scopes (repo)`.

Pushing commits from the current branch to a target branch:

```sh
git branch # Show the name of the current branch.
git push -u <remote> <current-branch>:<target-branch>
```

Alternative: initializing an empty repository.
```sh
mkdir <dir_name> # Create an empty folder.
cd <dir_name> # Enter directory.
git init # Initialize an empty Git repository.

git remote add origin https://github.com/<your_githubusername>/<repo-name>.git # Set a remote termed "origin" that points to the upstream repository.
git remote -v # List the configured remote.

git config user.name "<authors_name>" # Sets a Git username for the current repository (Optional).
git config user.email "authors_email@mail.com" # Sets the commit e-mail address for the current repository (Optional).

git add --all # Add all new (untracked) files to the Git staging area.
git commit -m "<commit_message>" # Define the topic of your commit.

git branch -M <newbranch> # (-m | -M) <oldbranch> is renamed to <newbranch>.
git push -u origin <newbranch> # To push local changes to your forked repository.
```

<!--- ############################################################################################################################################### -->

# [Git Merge](https://git-scm.com/docs/git-merge) vs [Git Rebase](https://git-scm.com/docs/git-rebase) workflow

When working collaboratively on a project, one has the choice to join/combine two or more development histories by taking commits from a feature branch and placing them on top of the header of a target branch (main, dev, etc.), for example.


## Git Merge

The git merge command join/combines commits from a feature branch into a target branch. It creates a single merge commit on top of the target branch header with all changes from both feature and target branches.

To merge/join previous commits from a branch named 'feature_branch' into a brand new single merge commit placed on top of the branch 'target_branch', run:
```bash
git checkout feature_branch # Switch to a branch named 'feature_branch'.
git merge target_branch
```

- Git merge commit history visualization:
```bash
   Before merge:      After merge:
                           (*) 
                            |   \
         (F2)               |  (F2) 
          |                 |    |
    (M5)  |                (M5)  |
     |  (F1)                |  (F1)
    (M4) /                 (M4) /
     |                      |
    (M3)                   (M3)
```
Legend:
- M: main branch.
- F: feature branch.

### [Git squash merge](https://git-scm.com/docs/git-merge#Documentation/git-merge.txt---squash)

To merge only the latest commits from a branch named 'feature_branch' into a single merge commit on top of the branch 'target_branch', run:
```bash
git checkout feature_branch
git merge --squash target_branch
```

The above command should be followed by `git merge --abort` whenever a merge results in a conflict, and will fail if there were uncommitted changes before `git merge`. Therefore, make sure to commit all changes before running a merge. If you get hit by the message "stopped before commiting as requested", simply run: `$ git commit -m "<commit-message>"`.
  
## Git Rebase 

Git rebase rewinds the history of the target branch by duplicating all the commits from the source branch on top of the target branch header while leaving commits from the source branch to be garbage collected.

To rebase/move previous commits from a branch named 'feature_branch' to the top of a branch named 'target_branch', run:
```bash
git checkout feature_branch
git rebase -i target_branch # To do a rebase against a branch named <target-branch> within the interactive mode.
```

**Rebasing upon the last `n` commits from a branch named 'feature_branch':**
```bash
git checkout feature_branch
git rebase -i  HEAD~<n> # Operate upon the last n commits within the interactive mode. 
```

*Note:* the `-i` flag enables interactive mode, where the default terminal text editor will pop up to enable the user to edit how a list of commits should be rebased.

- Git rebase commit history visualization:
```bash
Before rebase      After rebase
                       (F2)                                                   
     (F2)               |   
      |                (F1)  
     (F1)               |  
 (M5) /                (M5) 
  |                     |
 (M4)                  (M4)
  |                     |
 (M3)                  (M3)
```
Legend:
- M: main branch.
- F: feature branch.

**Full example rebasing against a target branch named 'main'.**

```bash
git clone <repo-address>.git
git checkout -b feature_branch # Create a new branch named 'feature_branch' to make changes in your local repository.
git add --all
git commit -m "<commit-message>" # Commit all changes before merge.
git checkout main # Switch to a branch named 'main'.
git pull # Make sure to update your local repository in the meantime.
git checkout feature_branch # Switch back to branch 'feature_branch'.
git rebase -i main # To perform a rebase against the latest changes.
git checkout main # Switch back to branch 'main'.
git rebase -i feature_branch # To align the latest commits placing them on top of the main branch.
git push main # Push your local changes to your remote repository.
```

<!--- ############################################################################################################################################### -->

# [Git cherry-pick](https://git-scm.com/docs/git-cherry-pick)

To bring only specific commits from a feature branch into a target branch (main, dev, etc.), run:

```bash
git checkout <feature-branch> # Switch to the branch one wants to bring commits from. 
git log # Show the id of the commits one wants to bring.
git checkout <target-branch> # Switch to the branch one wants to move the commits to.
git cherry-pick <commit-id1> <commit-id2> ... <commit-idN> # To bring one or several commits.
git push -u origin <target-branch> 
```

To stage changes without making any commits, use the `-n` flag:
```bash
git cherry-pick <commit-id1> -n
git commit -m "<commit_message>"
```

<!--- ############################################################################################################################################### -->

# [Pulling Updates](https://docs.github.com/en/get-started/using-git/getting-changes-from-a-remote-repository) from an Upstream remote repository

If you have forked a remote repository owned by another GitHub user, there are two ways you can pull updates from said repository (a.k.a upstream repository) to sync both your local (cloned) copy and your remote forked repository.

- From the web UI:

  - **Before pull (fetch and merge):** `This branch is <N> commit(s) behind <repo-name>:<branch-name>.`

  1. Click on **Fetch upstream:** `Fetch and merge <N> upstream commit(s) from <repo-name>:<branch-name>.`

  2. Click on **Fetch and merge**. Output message should be `This branch is up to date with <repo-name>:<branch-name>.`

- From the command line:

To [sync](https://docs.github.com/github/collaborating-with-issues-and-pull-requests/syncing-a-fork) both the cloned repo and the remote forked repo:

```sh
cd <repo-name> # If you have already forked the repo. Otherwise, run 'git init' to initialize an empty local repo. 
git remote -v # To list the current configured remote repository for your fork.
git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY # Assigning "upstream" as the remote repository that will be synced with the fork.

git fetch upstream # To retrieve all the new remote-tracking branches and tags updates from the upstream repository.
git checkout <branch-name> # To switch to the existing remote-tracking branch (i.e., the branch fetched from the remote repository) named "<branch-name>".

git merge upstream/<branch-name> # To merge the specified upstream branch with your local (cloned) branch without losing your local changes.
                                 # If the local branch didn't have any commits, GIT will fast-forward the cloned repo.
                                     
git push -u origin <branch-name> # Finally, we push the local changes in order to also update your remote forked repository.
```

Alternatively, one can choose to use `$ git pull`. The full process using an empty directory thus becomes:
```sh
cd <dir-name>
git init # For an empty directory.
git remote add upstream <orig_repo_url> # Remote of the the original repo.
git remote add origin <forked_repo_url> # Remote of the forked repo.
git pull upstream <branch-name> # To fetch updates and merge them with your local (cloned) repository.
git add --all
git commit -m '<commit_message>'
git branch -M <branch-name>
git push -u origin <branch-name> # To update your remote forked repository.
```

Make sure to commit all new changes made in your local work before running the pull command to avoid a [merge conflict](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line).

If you made changes to your local repository, then:
```sh
git rebase upstream/<branch-name> # To update your local (cloned) repository if it has been changed.
git push -f origin <branch-name> # To update your remote forked repository.                                
```

<!--- ############################################################################################################################################### -->


# [Issue Tracker](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue)

There are two common ways to report a bug:

1. [Create an issue](hhttps://github.com/QuCAI-Lab/educational-resources/issues/new) through the [Issue Tracker](https://github.com/QuCAI-Lab/educational-resources/issues) from the web UI.

2. Create an `issue` from your computer's command line using [GitHub CLI](https://docs.github.com/en/github-cli/github-cli/about-github-cli).


<!--- ############################################################################################################################################### -->


# [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

You can push changes from your forked repository to a specified branch of a remote repository owned by another GitHub user, as follows:

1 - Fork the desired repository to your GitHub account.

2 - Clone your forked repository:

```bash
git clone https://github.com/<yourgithubusername>/<repo-name>.git 
```

3 - Create a new branch for pull request and check out:

```sh
cd <repo-name>
git checkout -b <newbranch>
```

4 - Check your changes before commit:

```sh
git status
git diff
```

5 - Assigning "upstream" as the original remote repository that will be synced with the fork:

```sh
git remote -v
git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY
```

6 - Set your Local Git Identity:

```sh
git config user.name "<yourgithubusername>"
git config user.email "youremail@mail.com"
git config --list
```

7 - Push changes using your local shell/Anaconda Prompt, as follows:

```sh
git add --all
git commit -m "<topic of your pull request>"
git push -u upstream <newbranch>
```

8 - On the web UI, click the `Compare & pull request` button.

9 - Finally, click on `Create pull request`.

The admin or CI/CD tool of the upstream (original) repository will review the pull request and merge (or ignore) your proposed changes.


<!--- ############################################################################################################################################### -->


# Atom IDE

Just in case you want to skip the above command-line steps. A suggested IDE to manage your GitHub repositories on a local server is [Atom](https://atom.io/).
To install Atom on Linux, see [this manual](https://flight-manual.atom.io/getting-started/sections/installing-atom/). Once installed, you can clone, push changes, fetch/merge (pull) updates and open pull requests using the Atom GUI. 

With open Atom IDE:
- To clone: click on the `GitHub` tab >> click on the `Clone an existing GitHub repository...` tab.
- To push: click on `Git` >> click on `Stage All` >> click on `Commit to main` >> click on `Push`.
- To pull: click on `Fetch` >> click on `Pull`.


<!--- ############################################################################################################################################### -->


# Contributors 

Created and maintained by [@camponogaraviera][1].

[1]: https://github.com/camponogaraviera


