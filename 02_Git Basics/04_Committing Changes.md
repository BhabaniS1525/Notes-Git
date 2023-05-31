# Committing Changes

Once files are in the **Staging Area**, we can commit them to the repository, with the command `git commit -m "My commit message"`

```bash
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   02 Creating Snapshots/05- Committing Changes.md
```

With the command `git commit -m "New lesson started"` a snapshot will be saved to the repository.

```bash
❯ git commit -m 'New lesson started'
[main cb4a472] New lesson started
 1 file changed, 4 insertions(+)
 create mode 100644 02 Creating Snapshots/05- Committing Changes.md
```

If we commit to more than one file, we will se the following message:

```bash
❯ git commit -m 'Lesson completed'
[main bc32e03] Lesson completed
 2 files changed, 25 insertions(+)
 create mode 100644 02 Creating Snapshots/06- Committing Best Practices.md
 create mode 100644 02 Creating Snapshots/07- Skipping the Staging Area.md
```

When a short, one line, message is not sufficient, because we need to explain the details of the changes we can use the command `git commit`, without the `-m "My message"` part. These will open the default editor with a file named `COMMIT_EDITMSG`.

In the first line we add a short description (ideal less than 80 characters), then we add a line break and then description message. After we save and close the file the changes are committed. And we will have in the terminal and output like the following:

```bash
❯ git commit
[main e0a1a79] Continuing lesson 5 Committing Changes
 1 file changed, 18 insertions(+)
```

## Committing Best Practices

Commits should not be to small neither too big. We want to wait until we implement a feature end to end before committing. The all point of committing is to record checkpoint as we go.

**Commit often** when we believe the project or file is at a state we want to record.

For example if we are fixing a **Bug** than we find a **Typo** we should make separate commits. One for the **Bug** and another for the **Typo**.

### Wording

Most people like to use the present tense for commit messages. But other conventions can be used.

- PRESENT: Fix the bug
- PAST: Fixed the bug

### Conventional Commits

More in depth detail about commit messages in [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).
