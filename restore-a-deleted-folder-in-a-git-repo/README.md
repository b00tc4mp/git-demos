# [Restore a deleted folder in a Git repo](https://stackoverflow.com/questions/30875205/restore-a-deleted-folder-in-a-git-repo)

Everything you can do with a file, you can do with a folder too.

Also note [find and restore a deleted file in a Git repository](https://stackoverflow.com/questions/953481/find-and-restore-a-deleted-file-in-a-git-repository)

## Files are deleted from working tree but not committed yet

If you have not yet indexed (git add) your changes you can revert content of a directory:

```sh
git checkout -- path/to/folder
```

If the deletion is already indexed, you should reset that first:

```
git reset -- path/to/folder
git checkout -- path/to/folder
```

### Restore the full working tree (not a single folder), but lose all uncommitted changes

```
git reset --hard HEAD
```

## When files are deleted in some commit in the past

Find the last commit that affected the given path. As the file isn't in the HEAD commit, this commit must have deleted it.

```
git rev-list -n 1 HEAD -- <file_path>
```

Then checkout the version at the commit before, using the caret (^) symbol:

```
git checkout <deleting_commit>^ -- <file_path>
```

Restore the full working tree from a distant commit

```
git reset --hard <revision> 
```