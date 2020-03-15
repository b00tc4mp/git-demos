# [How can I list all the deleted files in a git repository?](https://stackoverflow.com/questions/6017987/how-can-i-list-all-the-deleted-files-in-a-git-repository)

```
git log --diff-filter=D --summary
```

If you don't want all the information about which commit they were removed in, you can just add a grep delete in there.

```
git log --diff-filter=D --summary | grep delete
```

