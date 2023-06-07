# Restoring a File to an Earlier Version

Once git tracks a file it stores every version of that file in the database. With Git there are two way to restore a earlier version of file:

1. Restore a file to previous version
2. Undoing a commit

If we delete a file by accident using the `git rm` command which is marked as `deleted` in the **Staging Area**.

```bash
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    02 Creating Snapshots/17- Discarding Local Changes.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        02 Creating Snapshots/18- Restoring a File to an Earlier Version.md
```

After committing `git commit -m 'delete file'`, and if we do a `git log --oneline`

```bash
b02e494 (HEAD -> main) delete file
cb02fd6 Lesson complete
9b67da8 Lesson start
001ce95 Lesson complete
0746554 Start lesson
[...]
```

In this case with `git restore --source=HEAD~1 02 Creating Snapshots/17- Discarding Local Changes.md`, we override the default behavior and restore the last commit that is when we deleted the file. With `git status` we will see the recovered file marked as untracked.

```bash
❯ git status
On branch main

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        02 Creating Snapshots/17- Discarding Local Changes.md
        02 Creating Snapshots/18- Restoring a File to an Earlier Version.md

nothing added to commit but untracked files present (use "git add" to track)
```
