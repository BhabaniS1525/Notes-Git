# Renaming or Moving Files

## Using Linux commands

We can use the `mv` command to rename or move files in Linux. The syntax is as follows:

**Rename File**

```bash
mv <current file> <new name>
```

Upon running `git status` we will see the following output:

```bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    6.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        new6.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Upon running `git add .` we will see the following output:

```bash
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    6.txt -> new6.txt
```

**Move File**

Command:

```bash
mv <current file> <another existing file>
```

Upon running `git status` we will see the following output:

```bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    2.txt
        modified:   6.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Upon staging both files and running `git status` one more time, we will see the following output:

```bash
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    2.txt
        modified:   6.txt
```

## Git mv Command

When we use the `git mv` command the changes are applied to both the **Working Directory** and the **Staging Area**.
