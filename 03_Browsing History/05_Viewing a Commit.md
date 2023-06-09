# Viewing a Commit

As we seen before we can use `git show` to get the info about a specific commit.

## Final version of a file

We can see the final version of a file in a particular commit with the `git show HEAD~n:<path to the file>`. For example `git show HEAD~2:"02 Creating Snapshots/12- Viewing Staged and Unstaged Changes.md`. In here are 2 commits before `HEAD` which is the last commit.

## Files changed in a commit `--name-only`

To view the files that were changed in a given commit we use `git show HEAD~4 --name-only`, The output is something like:

```bash
commit bf77b4e007ecaa30da382ff80e7afdc1fb1f6fc9
Author: user user <user @user.com>
Date:   Thu Mar 4 23:35:58 2021 -0300

    lesson completed

02 Creating Snapshots/19- Creating Snapshots with VSCode.md
02 Creating Snapshots/20- Creating Snapshots with GitKraken.md
02 Creating Snapshots/images/19-01.png
```

## Files changed in a commit `--name-status`

Using the option `--name-status`, we have a similar output than above but wit information about the file, if it was added, modified, deleted or renamed.

```bash
commit bf77b4e007ecaa30da382ff80e7afdc1fb1f6fc9
Author: user user <user @user.com>
Date:   Thu Mar 4 23:35:58 2021 -0300

    lesson completed

A       02 Creating Snapshots/19- Creating Snapshots with VSCode.md
A       02 Creating Snapshots/20- Creating Snapshots with GitKraken.md
A       02 Creating Snapshots/images/19-01.png
```
