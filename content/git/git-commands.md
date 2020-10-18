---
title: "Git Commands"
date: 2017-12-03 16:32
---

[TOC]

### 0. init
> Create an empty Git repository or reinitialize an existing one.

```
git init
```

### 1. clone
```
git clone [-b <branch>] [--depth <depth>] <repository> [<dir>]
```

### 2. fetch
```
git fetch <repository> [<branch>]

e.g.
git fetch origin develop
```

### 3. merge
```
git merge [<options>] <branch>

e.g.
git merge --no-ff origin/develop
```
#### options
|options|description|
|:------|:-----------|
|`--ff`|default behavior|
|`--no-ff`|no fast forward|
|`--squash`||

### 4. pull
> Fetch from and integrate with another repository or a local

```
# git pull = fetch + merge
git pull [<options>] <repository> [<branch>]
```
#### options
|options|description|
|:------|:-----------|
|`--ff`|default behavior|
|`--no-ff`|no fast forward|
|`--squash`||
|`--ff-only`|abort if fast-forward is not possible|
|`-f, --force`|force overwrite of local branch|
|`--rebase`|rebase the current branch on top of the upstream branch after fetching|

### 5. push
> Update remote refs along with associated objects.
> Push local commits to remote repository.

```
git push [<options>] <repository> [<branch>]

e.g.
git push origin develop
git push --delete <repository> [<branch>]
```
#### options
|options|description|
|:------|:-----------|
|`--delete`|delete remote branch|
|`--tag`|push tags (can't be used with --all or --mirror)|

### 6. add
> Add file contents to the index.

```
git add [<options>] [--] <pathspec>...

e.g.
git add readme.md
git add .
```

### 7. commit
```
git commit [<options>] [--] <pathspec>...
```
#### Commit message options
|options|description|
|:------|:-----------|
|`-m, --message <message>`|commit message|
|`--fixup <commit>`|use autosquash formatted message to fixup specified commit|
|`--squash <commit>`|use autosquash formatted message to squash specified commit|

#### Commit contents options
|options|description|
|:------|:-----------|
|`--amend`|amend previous commit & append add to last commit|

### 8. remote
```
git remote show
git remote show origin
git remote add <ref-name> <repository>
```

### 9. branch
> List, create, or delete branches.

```
git branch [<options>] [-r | -a] [--merged | --no-merged]
git branch [<options>] [-l] [-f] <branch-name> [<start-point>]
git branch [<options>] [-r] (-d | -D) <branch-name>...
git branch [<options>] (-m | -M) [<old-branch>] <new-branch>
```
#### options
|options|description|
|:------|:-----------|
|`-a, --all`|list both remote-tracking and local branches|
|`-d, --delete`|delete fully merged branch|
|`-m, --move`|move/rename a branch and its reflog|
|`-f, --force`|force creation, move/rename, deletion|
|`--no-merged <commit>`|print only not merged branches|
|`--merged <commit>`|print only merged branches|

### 10. checkout
> Switch branches or restore working tree files.

```
git checkout [<options>] <branch>
git checkout [<options>] [<branch>] -- <file>...
```
#### options
|options|description|
|:------|:-----------|
|`-q, --quiet`|suppress progress reporting|
|`-b <branch>`|create and checkout a new branch|

### 11. rebase

### 12. log
```
git log
```

### 13. reflog
```
git reflog
```

### 14. tag

### 15. rm
> Remove files from the working tree and from the index.

```
git rm [<options>] [--] <file>...

e.g.
git rm --cached <file>...
```
#### options
|options|description|
|:------|:-----------|
|`--`|This option can be used to separate command-line options from the list of files, (useful when filenames might be mistaken for command-line options).|
|`--cached`|only remove from the index|

### 16. clean
> Cleans the working tree by recursively removing files that are __not under version control__, starting from the current directory.

> Normally, only files unknown to Git are removed, but if the `-x` option is specified, ignored files are also removed. This can, for example, be useful to remove all build products.

> If any optional `<path>...` arguments are given, only those paths are affected.

```
git clean [-d] [-f] [-i] [-n] [-q] [-e <pattern>] [-x | -X] [--] <paths>...
```

### 17. status
```
git status
```

### 18. reset

### 19. diff

### 20. cherry-pick

> Apply the changes introduced by some existing commits

```shell
# 在当前分支，以一个新commit合入master分支的最新commit
git cherry-pick master
# 在当前分支，以一个新commit合入master分支的倒数第2个最新commit
git cherry-pick master~1
# 在当前分支，以2个新commits合入master分支的倒数第5个、第3个最新commit
git cherry-pick master~4 master~2
```

