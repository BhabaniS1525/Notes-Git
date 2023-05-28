# Viewing Staged and Unstaged Changes

Before committing code it is a best practice to review your code. To do that we can use the `git diff` command.

## Comparing the **Staging Area**

```bash
git diff --staged
```

To view changes in files that we have added to the **Staging Area** we run `git diff --staged`. This command will give us the following output:

```bash
❯ git diff --staged
diff --git a/02 Creating Snapshots/12- Viewing Staged and Unstaged Changes.md b/02 Creating Snapshots/12- Viewing Staged and Unstaged Changes.md
index 561ffc0..3661360 100644
--- a/02 Creating Snapshots/12- Viewing Staged and Unstaged Changes.md
+++ b/02 Creating Snapshots/12- Viewing Staged and Unstaged Changes.md
@@ -1,3 +1,9 @@
 # 12- Viewing Staged and Unstaged Changes

+## git diff command

+Before committing code it is a best practice to review your code. To do that we can use the `git diff` command.
+
+
+git diff --staged
+
\ No newline at end of file
```

In the first line we can see that the `diff` utility is called and with which arguments, what files we are comparing.

- **`a/...`** is what we have in the last commit
- **`b/...`** is what we currently have in the **Staging Area**.
- **`-`** changes in the old copy are marked with a red
- **`+`** changes to the new copy are marked with green

The legend is followed by a header, that tells us what parts of our file have been changed. The changes are split in chunks and there is a header for each chunk.

The **`-1,3`** referes to the old copy. It means starting from line one **`1`** three **`3`** lines have been extracted and shown here.

The **`+1,9`** referes to the new copy. It means starting from line one **`1`** nine **`9`** lines have been extracted and shown here.

## Comparing the **Working Directory**

To compare what we have in the working directory with what we have in the **Staging Area** we run `git diff`.

The output follows the same concept as `git diff --staged`.
