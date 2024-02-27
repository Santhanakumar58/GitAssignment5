Git Assignment 5

Question 

● Create a gitflow workflow architecture on git 
● Create all the required branches 
● Starting from the feature branch, push the branch to the master, following the 
architecture 
● Push a urgent.txt on master using hotfix 


santh@Santhana MINGW64 /c
$ pwd
/c

santh@Santhana MINGW64 /c
$ mkdir GitAssignment5

santh@Santhana MINGW64 /c
$ cd GitAssignment5

santh@Santhana MINGW64 /c/GitAssignment5
$ git init
Initialized empty Git repository in C:/GitAssignment5/.git/

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ nano master.txt

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git add .
warning: in the working copy of 'master.txt', LF will be replaced by CRLF the next time Git touches it

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git commit -m "Added Initial master.txt for Assignment5"
[main (root-commit) 9ee14dc] Added Initial master.txt for Assignment5
 1 file changed, 1 insertion(+)
 create mode 100644 master.txt

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git status
On branch main
nothing to commit, working tree clean

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git branch
* main

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git branch develop

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git branch release

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git branch feature1

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git branch feature2

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git branch
  develop
  feature1
  feature2
* main
  release

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git checkout feature1
Switched to branch 'feature1'

santh@Santhana MINGW64 /c/GitAssignment5 (feature1)
$ nano feature1.txt

santh@Santhana MINGW64 /c/GitAssignment5 (feature1)
$ git add .
warning: in the working copy of 'feature1.txt', LF will be replaced by CRLF the next time Git touches it

santh@Santhana MINGW64 /c/GitAssignment5 (feature1)
$ git commit -m "Added feature1.txt"
[feature1 d2e4b06] Added feature1.txt
 1 file changed, 1 insertion(+)
 create mode 100644 feature1.txt

santh@Santhana MINGW64 /c/GitAssignment5 (feature1)
$ git checkout feature2
Switched to branch 'feature2'

santh@Santhana MINGW64 /c/GitAssignment5 (feature2)
$ nano feature2.txt

santh@Santhana MINGW64 /c/GitAssignment5 (feature2)
$ git add .
warning: in the working copy of 'feature2.txt', LF will be replaced by CRLF the next time Git touches it

santh@Santhana MINGW64 /c/GitAssignment5 (feature2)
$ git commit -m "Added feature2.txt"
[feature2 ee627ac] Added feature2.txt
 1 file changed, 1 insertion(+)
 create mode 100644 feature2.txt

santh@Santhana MINGW64 /c/GitAssignment5 (feature2)
$ git checkout develop
Switched to branch 'develop'

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ ls
master.txt

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git merge feature1
Updating 9ee14dc..d2e4b06
Fast-forward
 feature1.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature1.txt

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git merge feature2
Merge made by the 'ort' strategy.
 feature2.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature2.txt

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ ls
feature1.txt  feature2.txt  master.txt

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git checkout release
Switched to branch 'release'

santh@Santhana MINGW64 /c/GitAssignment5 (release)
$ ls
master.txt

santh@Santhana MINGW64 /c/GitAssignment5 (release)
$ git merge develop
Updating 9ee14dc..d85f330
Fast-forward
 feature1.txt | 1 +
 feature2.txt | 1 +
 2 files changed, 2 insertions(+)
 create mode 100644 feature1.txt
 create mode 100644 feature2.txt

santh@Santhana MINGW64 /c/GitAssignment5 (release)
$ ls
feature1.txt  feature2.txt  master.txt

santh@Santhana MINGW64 /c/GitAssignment5 (release)
$ git checkout master
error: pathspec 'master' did not match any file(s) known to git

santh@Santhana MINGW64 /c/GitAssignment5 (release)
$ git checkout main
Switched to branch 'main'

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git merge release
Updating 9ee14dc..d85f330
Fast-forward
 feature1.txt | 1 +
 feature2.txt | 1 +
 2 files changed, 2 insertions(+)
 create mode 100644 feature1.txt
 create mode 100644 feature2.txt

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ ls
feature1.txt  feature2.txt  master.txt

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git checkout develop
Switched to branch 'develop'

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git merge release
Already up to date.

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ ls
feature1.txt  feature2.txt  master.txt

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git tag -a v1.0 -m "Version 1.0"

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git checkout main
Switched to branch 'main'

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git tag -a v1.0 -m "Version 1.0"
fatal: tag 'v1.0' already exists

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git branch hotfix

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git checkout hotfix
Switched to branch 'hotfix'

santh@Santhana MINGW64 /c/GitAssignment5 (hotfix)
$ nano urgent.txt

santh@Santhana MINGW64 /c/GitAssignment5 (hotfix)
$ git add .
warning: in the working copy of 'urgent.txt', LF will be replaced by CRLF the next time Git touches it

santh@Santhana MINGW64 /c/GitAssignment5 (hotfix)
$ git commit -m "Fixed Urgent Issues"
[hotfix 13caf41] Fixed Urgent Issues
 1 file changed, 1 insertion(+)
 create mode 100644 urgent.txt

santh@Santhana MINGW64 /c/GitAssignment5 (hotfix)
$ git checkout main
Switched to branch 'main'

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git merge hotfix
Updating d85f330..13caf41
Fast-forward
 urgent.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 urgent.txt

santh@Santhana MINGW64 /c/GitAssignment5 (main)
$ git checkout develop
Switched to branch 'develop'

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git merge hotfix
Updating d85f330..13caf41
Fast-forward
 urgent.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 urgent.txt

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git remote add origin https://github.com/Santhanakumar58/GitAssignment5.git

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git push origin --all
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (14/14), 1.24 KiB | 632.00 KiB/s, done.
Total 14 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/Santhanakumar58/GitAssignment5.git
 * [new branch]      develop -> develop
 * [new branch]      feature1 -> feature1
 * [new branch]      feature2 -> feature2
 * [new branch]      hotfix -> hotfix
 * [new branch]      main -> main
 * [new branch]      release -> release

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$ git push origin --tags
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 162 bytes | 162.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Santhanakumar58/GitAssignment5.git
 * [new tag]         v1.0 -> v1.0

santh@Santhana MINGW64 /c/GitAssignment5 (develop)
$
