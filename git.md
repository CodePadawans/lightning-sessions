# git

## Create a new repository

```bash
git init
Initialized empty Git repository in /Users/schneidersjosef/temp/.git/
```

This command creates a new hidden folder, `.git`. This folder is the repository, which means that all version control 
happens here. Note that no server is involved here. All happens on your local machine.

## Commit a new file

Place a new file in your directory. Then type in `git status`.

```bash
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	hello.txt

nothing added to commit but untracked files present (use "git add" to track)
```

It says, there is a new file git doesn't know about. To 'introduce' the file to git, type this:

```bash
git add hello.txt
```
This adds `hello.txt` to the *staging area*. This means, when you do a commit, this file will be considered for the commit. Only files which are staged will be part of the new commit.

To do the commit, type in `git commit`. The default editor opens and you can type in your commit message. Your commit message should be ~ 50-70 chars long.

## View the history

git stores the history of changes you did to all files. To view it, type in `git log`. Now you see all commits which have been made on the current branch.

To close this view, type in `q`.

## Undo changes 

Given the case you did changes to a file you want to undo. You can tell git to restore the last version of the file.
At first, type in `git status`. Then you will see this:

```bash
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   hello.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

git says, `hello.txt` changed. To see what has changed, type in `git diff`:

```bash
diff --git a/hello.txt b/hello.txt
index 1244ed0..5d799c6 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1 +1 @@
-Alice wrote this line
+Alice changed this line
```
You see, one line changed. To undo this change, you _check out_ this file. This means, git overwrites the current version whith its latest version. All changes will be lost. 

```bash
git checkout hello.txt
```

