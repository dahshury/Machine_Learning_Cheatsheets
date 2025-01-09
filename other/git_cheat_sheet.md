# **Git Cheat Sheet**

## Table 1: Git Configuration

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git config --global user.name "[Name]"` | Set the global username for commits. | `git config --global user.name "John Doe"` |
| `git config --global user.email "[Email]"` | Set the global email address for commits. | `git config --global user.email "john@example.com"` |
| `git config --global color.ui auto` | Enable colorized output in the terminal. | `git config --global color.ui auto` |
| `git config --list` | View the current Git configuration. | `git config --list` |

---

## Table 2: Repository Management

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git init` | Initialize a new Git repository in the current directory. | `git init` |
| `git clone [URL]` | Clone a remote repository. | `git clone https://github.com/example/repo.git` |
| `git status` | Show the status of changes in the working directory. | `git status` |
| `git add [file]` | Add a specific file to the staging area. | `git add README.md` |
| `git add .` | Add all changes to the staging area. | `git add .` |
| `git commit -m "[Message]"` | Commit staged changes with a message. | `git commit -m "Initial commit"` |

---

## Table 3: Branch Management

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git branch` | List all local branches. | `git branch` |
| `git branch [branch-name]` | Create a new branch. | `git branch feature/login` |
| `git checkout [branch-name]` | Switch to an existing branch. | `git checkout feature/login` |
| `git checkout -b [branch-name]` | Create and switch to a new branch. | `git checkout -b feature/login` |
| `git branch -d [branch-name]` | Delete a branch (if merged). | `git branch -d feature/login` |
| `git merge [branch-name]` | Merge the specified branch into the current branch. | `git merge feature/login` |

---

## Table 4: Viewing and Comparing Changes

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git log` | Show the commit history. | `git log` |
| `git log --oneline` | Display commit history in one line per commit. | `git log --oneline` |
| `git diff` | Show differences between the working directory and staging area. | `git diff` |
| `git diff --staged` | Show differences between the staging area and the last commit. | `git diff --staged` |
| `git show [commit-id]` | Display details of a specific commit. | `git show abc1234` |

---

## Table 5: Undoing Changes

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git checkout -- [file]` | Discard changes in the working directory. | `git checkout -- README.md` |
| `git reset [file]` | Unstage a file but keep changes in the working directory. | `git reset README.md` |
| `git reset --hard [commit-id]` | Reset the working directory to a specific commit, discarding all changes. | `git reset --hard abc1234` |
| `git revert [commit-id]` | Create a new commit that undoes the changes in a specific commit. | `git revert abc1234` |

---

## Table 6: Remote Repositories

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git remote add [alias] [URL]` | Add a remote repository. | `git remote add origin https://github.com/example/repo.git` |
| `git remote -v` | View the URLs of remote repositories. | `git remote -v` |
| `git fetch [remote]` | Fetch changes from a remote repository without merging. | `git fetch origin` |
| `git pull [remote]` | Fetch and merge changes from a remote repository. | `git pull origin main` |
| `git push [remote] [branch]` | Push commits to a remote branch. | `git push origin main` |
| `git push -u [remote] [branch]` | Push commits and set upstream branch. | `git push -u origin main` |

---

## Table 7: Stashing Changes

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git stash` | Save uncommitted changes for later use. | `git stash` |
| `git stash list` | List all stashed changes. | `git stash list` |
| `git stash pop` | Reapply the latest stash and remove it from the stash list. | `git stash pop` |
| `git stash drop` | Remove the latest stash without applying it. | `git stash drop` |

---

## Table 8: Tagging

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git tag` | List all tags in the repository. | `git tag` |
| `git tag [name]` | Create a lightweight tag for the current commit. | `git tag v1.0` |
| `git tag -a [name] -m "[Message]"` | Create an annotated tag with a message. | `git tag -a v1.0 -m "Release v1.0"` |
| `git push --tags` | Push all tags to the remote repository. | `git push --tags` |
| `git tag -d [name]` | Delete a tag locally. | `git tag -d v1.0` |

---

## Table 9: Advanced Operations

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git cherry-pick [commit-id]` | Apply changes from a specific commit to the current branch. | `git cherry-pick abc1234` |
| `git rebase [branch-name]` | Reapply commits on top of another base branch. | `git rebase main` |
| `git reflog` | Show a log of all reference updates in the repository. | `git reflog` |
| `git clean -n` | Show which files would be removed from working directory (dry run). | `git clean -n` |
| `git clean -f` | Remove untracked files from working directory. | `git clean -f` |
| `git blame [file]` | Show who last modified each line of a file. | `git blame README.md` |

## Table 10: Submodules and Large Files

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git submodule add [URL]` | Add a new submodule to the repository. | `git submodule add https://github.com/example/lib.git` |
| `git submodule update --init` | Initialize and update all submodules. | `git submodule update --init` |
| `git lfs install` | Set up Git Large File Storage in the repository. | `git lfs install` |
| `git lfs track "[file-pattern]"` | Start tracking files with Git LFS. | `git lfs track "*.psd"` |

## Table 11: Maintenance and Optimization

| **Command** | **Description** | **Usage Example** |
|-------------|-----------------|--------------------|
| `git gc` | Clean up unnecessary files and optimize local repository. | `git gc` |
| `git prune` | Remove objects that are no longer referenced. | `git prune` |
| `git fsck` | Check the integrity of objects in the repository. | `git fsck` |
| `git archive --format=zip HEAD > archive.zip` | Create a zip archive of the repository. | `git archive --format=zip HEAD > project.zip` |