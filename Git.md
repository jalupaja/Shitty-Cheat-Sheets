# Git Cheat Sheet
>[Git](https://git-scm.com) is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. 

| **Table of Contents** |
| -- |
[Default](#defaults)
[Commits](#commits)
[Branches](#branches)
[Logs](#logs)
[Other Resources](#other-resources)

## defaults
| Commands | Explanation |
| -- | -- |
```git [<option>] --help``` | get help on a specific topic
|
```git clone <link to remote git repository>``` | clone a remote repository to a local folder
```git init``` | initialize git in current folder
```git add <file>``` | add file to git (staged area) or add all files in folder: git add .
```git commit -m "<commit message>"``` | commit current point to git history
```git remote add <name> <remote address>``` | add remote repository
```git push [<remote name>]``` | push git to remote repository
```git status``` | show git status of current directory
|
| ".gitignore" file | using this file in your root git directory you can excludes files, filetypes and folders. You can find templates [here](https://github.com/github/gitignore)

## commits
| Commands | Explanation |
| -- | -- |
```git commit --fixup <commit hash>``` | mark as fix for specified commit
```git checkout <commit hash>``` | switch to another commit
```git reset <commit hash> [--hard]``` | delete all commits after specified commit
```git update-ref -d HEAD``` | reset first commit

## branches
| Commands | Explanation |
| -- | -- |
```git branch``` | list all available branches
```git branch -M <new branch name>``` | rename current branch
```git branch <branch name> [<commit hash>]``` | create new branch at commit point (default is last commit)
```git checkout -b <branch name> [<commit hash>]``` | create and switch to new branch at commit point
```git checkout <branch name>``` | switch to another branch
```git branch -d <branch name>``` | delete a branch
```git merge <branch name>``` | merge named branch in current branch

## logs
| Commands | Explanation |
| -- | -- |
```git log``` | show history of last commits
```git log --follow <file>``` | show history of a file
```git diff <commit hash/branch 1>...<commit hash 2> [<filepath>]``` | show changes between commits or branches
```git blame <file>``` | show author, time and changes made to file

## stash
| Commands | Expanation |
| -- | -- |
```git stash -a``` | stash current state of all files
```git stash list``` | list stashes
```git stash pop``` | Apply last stashed state
```git stash clear``` | delete all stashes

## other resources

| Source | About |
| -- | -- |
[git](https://git-scm.com/docs) | official git man pages
[git](https://git-scm.com/book/en/v2) | official Pro Git book by by Scott Chacon and Ben Straub
[github](https://training.github.com) | git cheat sheets by github
[git-tips](https://github.com/git-tips/tips) | collection of git-tips
[Computerphile](https://youtu.be/92sycL8ij-U) | 16 minute video on how the basics of git work