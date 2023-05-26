# 08- Fast-forward Merges

## Git log for branches `--graph`

To have a better visualizations of branches with `git log`, it is better to include the `--graph` option. It will produce an output where we are abe to better view the branch path.

```bash
❯ git log --oneline --graph
* 23c694d (HEAD -> fast-forward-merge) add details to lesson
* 6d91b25 (origin/main, main) add details to lesson
* 932b8dd lesson complete
* 1433f35 lesson complete
* 6d7a701 style: add final empty line
* 18c119d lesson start
* 176761d lesson completed
[...]
```

In this log we can see that the branch **_`fast-forward-merge`_** is one commit ahead of **_`main`_**, and that there is a linear path between them. So the could merger by the fast-forward method.

## Merge branch fast-forward

To merge the **_`fast-forward-merge`_** branch into **_`main`_**, we first should have committed all of our work in that branch and them we switch to **_`main`_**. In the **_`main`_** branch we run the merge with the command:

```bash
git merge fast-forward-merge
```

After we can run `git log` to see the result. As we can see in the log now both branches point to the same commit.

```bash
* 3c5127f (HEAD -> main, fast-forward-merge) add details to lesson
* 8c79b5d add details to lesson
* 23c694d add details to lesson
* 6d91b25 add details to lesson
* 932b8dd lesson complete
* 1433f35 lesson complete
```

## Merge without fast-forward `--no-ff`

It is also possible to enforce a non fast-forward merge with the command `git merge --no-ff <branch-name>`.

```bash
git merge --no-ff no-fast-forward-merge
```

With this we tell Git that, although it is possible to have a fast-forward merge, don't do it, and that it should create a new commit to merge **_`main`_** with another branch.

Here as well we can see the **_`no-fast-forward-merge`_**, branch is three commit ahead of **_`main`_** and there is a linear path between them.

```bash
❯ git log --oneline --graph
* 00a98bb (HEAD -> no-fast-forward-merge) add details to lesson
* 9aff663 add details to lesson
* 2694107 add details to lesson
* d8fbb20 add details to lesson
* 3c5127f add details to lesson
* 8c79b5d add details to lesson
* 23c694d add details to lesson
* 6d91b25 add details to lesson
* 932b8dd lesson complete
* 1433f35 lesson complete
[...]
```

When we run the `git merge --no-ff no-fast-forward-merge`, our default editor will open, with the default merge commit message **_Merge branch 'no-fast-forward-merge'_**. We do not need to modify the message, and we can add details if needed.

Now when we run `git log` we can see the new merge commit.

```bash
❯ git log --oneline --graph
*   afba0c3 (HEAD -> main) Merge branch 'no-fast-forward-merge'
|\
| * 00a98bb (no-fast-forward-merge) add details to lesson
| * 9aff663 add details to lesson
| * 2694107 add details to lesson
|/
* d8fbb20 add details to lesson
* 3c5127f add details to lesson
* 8c79b5d add details to lesson
* 23c694d add details to lesson
```

The new branch for this example called **_`no-fast-forward-merge`_**, was created from commit **`d8fbb20`**, then there were three commits on it, and at last was merged into **_`main`_** in the commit **`afba0c3`**, that was triggered by the merge command with the `--no-ff` option.

## Disable fast-forward merges

It is possible to disable fast-forward merges, that way all mergers Git performs will be non fast-forward, even if it is possible to have a fast forward merge.

1. Disable for a single repository: `git config merge.ff false`
2. Disable globally `git config --global merge.ff false`
