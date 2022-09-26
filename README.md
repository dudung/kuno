# kuno
texts, notes, scripts, codes kuno (have not been used)


## caution
All histories are mixed up and repeated. Can not find a better way. Just copy without history.


## clone source repo to merge
```bash
$ git clone https://github.com/dudung/ele-phys
Cloning into 'ele-phys'...
remote: Enumerating objects: 96, done.
remote: Counting objects: 100% (96/96), done.
remote: Compressing objects: 100% (74/74), done.
remote: Total 96 (delta 22), reused 15 (delta 3), pack-reused 0
Receiving objects: 100% (96/96), 20.26 KiB | 864.00 KiB/s, done.
Resolving deltas: 100% (22/22), done.
```


## move files to new unique folder
```bash
$ cd ele-phys

$ mkdir ele-phys

$ mv -v * ele-phys
renamed '01' -> 'ele-phys/01'
renamed 'LICENSE' -> 'ele-phys/LICENSE'
renamed 'README.md' -> 'ele-phys/README.md'
mv: cannot move 'ele-phys' to a subdirectory of itself, 'ele-phys/ele-phys'
```


## add, commit change, and push
```bash
$ git add .

Sparisoma Viridi@DESKTOP-IQQMB2K MINGW64 /l/home/ele-phys (main)
$ git commit -a -m  "move files and folder to subfolder"
[main 9b2bd3d] move files and folder to subfolder
 3 files changed, 0 insertions(+), 0 deletions(-)
 rename {01 => ele-phys/01}/unit-conversion.md (100%)
 rename LICENSE => ele-phys/LICENSE (100%)
 rename README.md => ele-phys/README.md (100%)

$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (1/1), done.
Writing objects: 100% (2/2), 236 bytes | 118.00 KiB/s, done.
Total 2 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/dudung/ele-phys
   800b599..9b2bd3d  main -> main
```

## navigate to destination folder, remote add, fetch, and rebase
```bash
$ cd ../kuno

$ git remote add ele-phys ../ele-phys

$ git fetch ele-phys
remote: Enumerating objects: 98, done.
remote: Counting objects: 100% (98/98), done.
remote: Compressing objects: 100% (56/56), done.
remote: Total 98 (delta 22), reused 96 (delta 22), pack-reused 0
Unpacking objects: 100% (98/98), 20.44 KiB | 5.00 KiB/s, done.
From ../ele-phys
 * [new branch]      main       -> ele-phys/main

$ git rebase ele-phys/main HEAD
Successfully rebased and updated detached HEAD.
```


## merge
```bash
$ git switch main
Warning: you are leaving 1 commit behind, not connected to
any of your branches:

  16ba897 Initial commit

If you want to keep it by creating a new branch, this may be a good time
to do so with:

 git branch <new-branch-name> 16ba897

Switched to branch 'main'
Your branch is up to date with 'origin/main'.

$ git merge --allow-unrelated-histories 16ba897
Merge made by the 'ort' strategy.
 ele-phys/01/unit-conversion.md | 57 ++++++++++++++++++++++++++++++++++++++++++
 ele-phys/LICENSE               | 21 ++++++++++++++++
 ele-phys/README.md             | 35 ++++++++++++++++++++++++++
 3 files changed, 113 insertions(+)
 create mode 100644 ele-phys/01/unit-conversion.md
 create mode 100644 ele-phys/LICENSE
 create mode 100644 ele-phys/README.m
```


## push
```bash
$ git push
Enumerating objects: 102, done.
Counting objects: 100% (102/102), done.
Delta compression using up to 4 threads
Compressing objects: 100% (80/80), done.
Writing objects: 100% (100/100), 20.28 KiB | 432.00 KiB/s, done.
Total 100 (delta 22), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (22/22), done.
To https://github.com/dudung/kuno
   d3a5e02..40a580f  main -> main
```
