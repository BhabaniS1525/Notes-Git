# 15- Tagging

Tags are use to mark a certain point in the project. Most of the times they are used to mark release version, like v1.0.

There are two type of tags **lightweight**, and **annotated** tag. The lightweight as only the tag name, and a annotated tag has more properties, like tagger name, email and message. Because a annotated tag can have more info they are preferes to lightweight.

## Tagging in the last commit

If we want to tag the last commit run `git tag <name of the tag>`

```bash
git tag v1.0
```

## Tagging an earlier commit

To tag an earlier commit we have to pass the commit after the tag like `git tag <name of the tag> <referent to commit>`.

```bash
git tag v1.0 b4ef25f
```

With `git log --oneline` we can see the tag.

```bash
b89cef8 (HEAD -> main) lesson complete
b4ef25f (tag: v1.0) restore file
dacc1ec delete file
33bceb5 start new lesson
1ce178a lesson complete
b5f716e lesson complete
```

## Referente a commit using a tag

It is also possible to reference a commit by it tag.

```bash
git checkout v1.0
```

## See all the tags

To see all the tag in the project run:

```bash
git tag
```

## Annotated tag `-a`

To create a annotated tag we use the option `-a`, followed by the tag name and then `-m` and a message.

```bash
git tag -a v1.2 -m 'Release version 1.1'
```

## Tags messages `-n`

To view the tags and messages use the `-n`option.

```bash
git tag -n
```

This will ouput something like the following example.

```bash
v1.0            restore file
v1.2            Release version 1.2
```

The lightweight tag is associated with the commit message that it point to. And the annotated tag has a custom message.

## Show Tag

Run `git show <tag name>` to view all the infos of that tag. Similar to `git show <commit>`. If the command is ran on an annotated tag besides the commit info we also have the tag info.

```bash
tag v1.2
Tagger: user user <user@user.com>
Date:   Tue Mar 9 00:00:03 2021 -0300

Release version 1.1

commit b89cef852dde2c83d81609d981c35ce6f8b7fba0 (HEAD -> main, tag: v1.2)
Author: user user <user@user.com>
Date:   Mon Mar 8 23:30:10 2021 -0300

    lesson complete
```

## Delete a tag `-d`

To delete a tag use the `-d` option.

```bash
git tag -d v1.0
```

This returns the deleted tag like so:

```bash
Deleted tag 'v1.0' (was b4ef25f)
```
