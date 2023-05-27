# Squash Merging

In squash merging we first combine the small commits in the branch itself because they are not good quality commits, and then we merge.

For example commits are

- Too fine grain
- Maybe we have mixed different things in each commit

![Squash Merging](./images/15-01.png "Squash Merging")

This new commit is not a merge commit, because it does not have two parents. It is lacking the reference to **B2**, the last commit from the **bugfix** branch. It is just a regular commit added on top of **_`main`_** that combines the commits from the other branch.

When we delete the **bugfix** branch, we are left with a clean linear history. This is the benefit fo Squash merging. But usually we should only apply it to short lived branches with bad history.

![Squash merging linear history](./images/15-01.png "Squash merging linear history")

To perform a squash merge use the following command `git merge --squash <name-of-branch>`. Git will create a new commit, called a **_`Squash commit`_**, that combines the changes made in the merged branch, and it will and the changes to the **_Staging Area_**. Then we just need to commit then normall.

```bash
git merge --squash bugfix
```

## List merged and unmerged branches

If we run `git branch --merged`, to list all the merged branches we will not see the **bugfix** branch. Because this branch was not actually merged. So it best to delete it after the squash merge, but in this situation we have to use `-D` instead of `-d`, or Git will throw an error. So `git branch -D bugfix`.

## Conflict in Squash merge

In case we run into conflicts when running a Squash merge, we can resolve this conflicts as in a normal merge.
