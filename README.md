
# Git and GitHub Tutorial

This repository contains a text file that serves as a tutorial for learning important features of Git and GitHub. Whether you're new to version control or looking to expand your knowledge, this tutorial covers essential commands and concepts to help you effectively manage your projects using Git and GitHub.

## Getting Started

To get started with Git and GitHub, make sure you have Git installed on your system. You can download Git from [here](https://git-scm.com/downloads).

## Tutorial Contents

The tutorial covers the following topics:

### Setting Up Git Configuration

```bash
git config --global user.name "parham doustkani"
git config --global user.email parham.dskn@gmail.com
git config --list
```

### Initializing a Git Repository

```bash
git init
```

### Basic Git Commands

```bash
git status // see if there is any uncommitted changes
git add file_name
git commit -am "note"
git diff
```

### Working with Files

```bash
touch file_name // create file 
git log // shows last 10 commits
git log --author="jafar" // shows commits of jafar (username or email)
git log --oneline // shows each commit in one line (better view)
git log --oneline --graph // to track merges
```

### Cloning a Repository

```bash
git clone -b main git_repo_link // -b for selecting branch
```

### Branch Operations

```bash
git branch // show branches
git branch branch_name // create a branch
git switch branch_name // change current branch (alternative = git checkout branch_name)
git push origin branch_name // push to a branch (create automatically branch if not present)
git pull -b branch_name // -b for selecting branch
```

### Merging Branches

```bash
git branch <dest_branch>
git pull -b <dest_branch> // first update the dest branch
git merge <src_branch> // then merge
git commit -am "note"
git push -b <dest_branch>
```

### Reverting Changes

```bash
git log --oneline // see the commit_id that we want to get back to
git reset --soft commit_id // just delete the commit (do not revert the changes on files)
git reset --hard commit_id // delete the commit and revert the changes on files
git revert HEAD~3 // revert every changes which was done in 3 commits (revert to fourth last commit)
git push
```

### Comparing Changes

```bash
git diff file_name // see changes of specific file 
git log --oneline // see the commit_ids that we want to compare
git diff commit_id1 commit_id2
```

### Managing Branches

```bash
git branch -m old_name new_name // rename a branch
git branch -d branch_name // delete a branch (current branch can not be deleted => change branch before deletion)
```

### Merging with Conflicts

```bash
git branch <dest_branch>
git merge <src_branch> // raise conflict for file f1
vim f1 // edit f1 (delete git generated parts, and keep the wanted codes, save the file)
git commit -am "note"
git push -b <dest_branch>
```

### Stashing Changes

```bash
git stash // delete every changes related to new feature from tracked files, but keep the changes in somewhere
git stash -a // if we created some untracked files during new feature development
git commit -am "note"
git push -b b1
git stash apply // add deleted changes to files
git commit -am "note"
git push -b b1
git stash list // stash is not removed automatically after commit
git stash drop
```

### Managing Multiple Stashes

```bash
git stash -a save "note" // stash with message
git stash list // see stash indices (like stash@{0})
git stash show stash@{0} // show changes of this stash (only works for tracked files)
git stash pop stash@{0} // apply and delete specific stash
```

## Contributing

If you find any issues or have suggestions for improvement, feel free to open an issue or create a pull request. Contributions are welcome!

Happy coding!
```

This formatted `README.md` file presents the tutorial content in a clear and organized manner, making it easy for users to navigate and learn from the provided information.