# [How to list all the files in a commit?](https://stackoverflow.com/questions/424071/how-to-list-all-the-files-in-a-commit)

**Preferred Way** (because it's a plumbing command; meant to be programmatic):

```
git diff-tree --no-commit-id --name-only -r bd61ad98
```

**Another Way** (less preferred for scripts, because it's a porcelain command; meant to be user-facing)

```
git show --pretty="" --name-only bd61ad98
```

The `--no-commit-id` suppresses the commit ID output.

The `--pretty` argument specifies an empty format string to avoid the cruft at the beginning.

The `--name-only` argument shows only the file names that were affected (Thanks Hank).

The `-r` argument is to recurse into sub-trees

```