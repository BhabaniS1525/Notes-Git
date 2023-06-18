# Why Rewrite History

## Why do we need the history?

With Git history we can see:

- What was changed
- Why it was changed
- When it was changed

## Bad commits

Bad commits make it difficult to read the project history.

- Poor commits messages, with no meaning
- To large commits, with unrelated changes
- To small commits, scattered all over the history

We need a clean history to be able to see how our project evolved from day one.

## Tools

To make our history cleaner we can use several Git operations.

- Squash small, related commits
- Split large commits with unrelated changes
- Reword commits messages
- Drop unwanted commits
- Modify the content of a commit

## The Golden Rule of Rewriting History

**_Don't rewrite public history_:** This rule means that commits that have been pushed to a public repository, and shared with other developers should not be modified.
