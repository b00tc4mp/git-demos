# recursive pull

in a folder with various repos (sub-folders)

```sh
$ find . -type d -depth 1 -exec git --git-dir={}/.git --work-tree=$PWD/{} pull \;
```

another way, using `parallel`

```sh
$ find . -type d -depth 1 | parallel 'cd {}; git pull'
```