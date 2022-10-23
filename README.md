# gym-git-exercise-solutions
## Bundle 1
### exercise 1
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym$ mkdir git-exercises
thegym@DESKTOP-JIQ9UQP:~/thegym$ cd git-exercises/
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint:   git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint:   git branch -m <name>
Initialized empty Git repository in /home/thegym/thegym/git-exercises/.git/
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi README.md
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git config --list
user.name=izzett222
user.email=iizzeddin62@gmail.com
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "added readme"
[master (root-commit) d816ad1] added readme
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git branch -M main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch main
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "added test file"
[main e34b821] added test file
 1 file changed, 1 insertion(+)
 create mode 100644 test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git remote add origin  git@github.com:izzett222/git-exercises.git
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push -u origin main
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (6/6), 480 bytes | 480.00 KiB/s, done.
Total 6 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:izzett222/git-exercises.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git branch dev
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout dev
Switched to branch 'dev'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git branch test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout test
Switched to branch 'test'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch test
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout dev
Switched to branch 'dev'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch dev
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git branch -d test
Deleted branch test (was e34b821).
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git branch
* dev
  main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
### exercise 2
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash
Saved working directory and index state WIP on dev: e34b821 added test file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch dev
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ touch about.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash
Saved working directory and index state WIP on dev: e34b821 added test file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch dev
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ touch team.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash
Saved working directory and index state WIP on dev: e34b821 added test file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash list
stash@{0}: WIP on dev: e34b821 added test file
stash@{1}: WIP on dev: e34b821 added test file
stash@{2}: WIP on dev: e34b821 added test file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash show -p
diff --git a/team.html b/team.html
new file mode 100644
index 0000000..56efbdb
--- /dev/null
+++ b/team.html
@@ -0,0 +1,12 @@
+<!DOCTYPE html>
+<html lang="en">
+<head>
+    <meta charset="UTF-8">
+    <meta http-equiv="X-UA-Compatible" content="IE=edge">
+    <meta name="viewport" content="width=device-width, initial-scale=1.0">
+    <title>Document</title>
+</head>
+<body>
+
+</body>
+</html>
\ No newline at end of file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash@{1} show -p
git: 'stash@{1}' is not a git command. See 'git --help'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git show stash@{1} -p
commit 9292c4534210f60a659f7114f6c069a91a1cd644
Merge: e34b821 150537d
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Tue Oct 18 19:18:54 2022 +0200

    WIP on dev: e34b821 added test file

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git show stash@{1}
commit 9292c4534210f60a659f7114f6c069a91a1cd644
Merge: e34b821 150537d
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Tue Oct 18 19:18:54 2022 +0200

    WIP on dev: e34b821 added test file

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git show stash@{2}
commit d44b52946464ef783bfa22ad9aeeeb6d0d004c30
Merge: e34b821 88db66c
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Tue Oct 18 19:18:16 2022 +0200

    WIP on dev: e34b821 added test file

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git show stash show -p
fatal: ambiguous argument 'show': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:
'git <command> [<revision>...] -- [<file>...]'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash show -p
diff --git a/team.html b/team.html
new file mode 100644
index 0000000..56efbdb
--- /dev/null
+++ b/team.html
@@ -0,0 +1,12 @@
+<!DOCTYPE html>
+<html lang="en">
+<head>
+    <meta charset="UTF-8">
+    <meta http-equiv="X-UA-Compatible" content="IE=edge">
+    <meta name="viewport" content="width=device-width, initial-scale=1.0">
+    <title>Document</title>
+</head>
+<body>
+
+</body>
+</html>
\ No newline at end of file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash show -p stash@{1}
diff --git a/about.html b/about.html
new file mode 100644
index 0000000..56efbdb
--- /dev/null
+++ b/about.html
@@ -0,0 +1,12 @@
+<!DOCTYPE html>
+<html lang="en">
+<head>
+    <meta charset="UTF-8">
+    <meta http-equiv="X-UA-Compatible" content="IE=edge">
+    <meta name="viewport" content="width=device-width, initial-scale=1.0">
+    <title>Document</title>
+</head>
+<body>
+
+</body>
+</html>
\ No newline at end of file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Dropped stash@{1} (9292c4534210f60a659f7114f6c069a91a1cd644)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash list
stash@{0}: WIP on dev: e34b821 added test file
stash@{1}: WIP on dev: e34b821 added test file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash show -p stash{2}
error: stash{2} is not a valid reference
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash show -p stash{1}
error: stash{1} is not a valid reference
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash show -p stash@{1}
diff --git a/home.html b/home.html
new file mode 100644
index 0000000..62510eb
--- /dev/null
+++ b/home.html
@@ -0,0 +1,12 @@
+<!DOCTYPE html>
+<html lang="en">
+<head>
+    <meta charset="UTF-8">
+    <meta http-equiv="X-UA-Compatible" content="IE=edge">
+    <meta name="viewport" content="width=device-width, initial-scale=1.0">
+    <title>home</title>
+</head>
+<body>
+
+</body>
+</html>
\ No newline at end of file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html

Dropped stash@{1} (d44b52946464ef783bfa22ad9aeeeb6d0d004c30)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "added home and about page"
[dev d3997a3] added home and about page
 2 files changed, 24 insertions(+)
 create mode 100644 about.html
 create mode 100644 home.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
fatal: The current branch dev has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin dev

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push -u origin dev
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 544 bytes | 181.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
remote:
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/dev
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      dev -> dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash list
stash@{0}: WIP on dev: e34b821 added test file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash show -p
diff --git a/team.html b/team.html
new file mode 100644
index 0000000..56efbdb
--- /dev/null
+++ b/team.html
@@ -0,0 +1,12 @@
+<!DOCTYPE html>
+<html lang="en">
+<head>
+    <meta charset="UTF-8">
+    <meta http-equiv="X-UA-Compatible" content="IE=edge">
+    <meta name="viewport" content="width=device-width, initial-scale=1.0">
+    <title>Document</title>
+</head>
+<body>
+
+</body>
+</html>
\ No newline at end of file
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git stash pop
On branch dev
Your branch is up to date with 'origin/dev'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped refs/stash@{0} (4caf1a12c0d4a9ebcb51d9fb313ee8542f6b8ed0)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git reset --hard HEAD
HEAD is now at d3997a3 added home and about page
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch dev
Your branch is up to date with 'origin/dev'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
## bundle 2
### exercise 1
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ ls
about.html  home.html  README.md  test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch dev
Your branch is up to date with 'origin/dev'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ touch services.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ code .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "add services page"
[ft/bundle-2 01b9e58] add services page
 1 file changed, 12 insertions(+)
 create mode 100644 services.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push -u
fatal: The current branch ft/bundle-2 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/bundle-2

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push --set-upstream origin ft/bundle-2
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 472 bytes | 236.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/ft/bundle-2
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2
Branch 'ft/bundle-2' set up to track remote branch 'ft/bundle-2' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
### exercise 2
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git pull
Already up to date.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout -b ft/service-redesign
Switched to a new branch 'ft/service-redesign'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/service-redesign
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi services.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "change the service list"
[ft/service-redesign 4bf0aff] change the service list
 1 file changed, 6 insertions(+), 5 deletions(-)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
fatal: The current branch ft/service-redesign has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/service-redesign

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push --set-upstream origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 396 bytes | 132.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/ft/service-redesign
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      ft/service-redesign -> ft/service-redesign
Branch 'ft/service-redesign' set up to track remote branch 'ft/service-redesign' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi services.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "modify the service list"
[main c6f7632] modify the service list
 1 file changed, 5 insertions(+), 3 deletions(-)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 418 bytes | 418.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:izzett222/git-exercises.git
   8ea7ed6..c6f7632  main -> main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'
Your branch is up to date with 'origin/ft/service-redesign'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/service-redesign
Your branch is up to date with 'origin/ft/service-redesign'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git diff main
diff --git a/services.html b/services.html
index c23beaa..6ac3fbd 100644
--- a/services.html
+++ b/services.html
@@ -7,12 +7,11 @@
     <title>services</title>
 </head>
 <body>
-       <h3>these are our services, you can learn more <a href="#">here</a></h3>
-    <ol>
-       <li>ads</li>
-       <li>graphic design</li>
-       <li>backend develop</li>
-       <li>ui design</li>
-    </ol>
+    <h2>these are our services right now</h2>
+    <ul>
+       <li>web design</li>
+       <li>cooking</li>
+       <li>fashion design</li>
+    </ul>
 </body>
 </html>
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git merge main
Auto-merging services.html
CONFLICT (content): Merge conflict in services.html
Automatic merge failed; fix conflicts and then commit the result.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi services.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit
[ft/service-redesign 86ed0a7] Merge branch 'main' into ft/service-redesign
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit 86ed0a7f33459af8c8bbe710e201ea0c0c48bed5 (HEAD -> ft/service-redesign)
Merge: 4bf0aff c6f7632
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:21:38 2022 +0200

    Merge branch 'main' into ft/service-redesign

commit c6f7632923fad35faee5ae1a1395c91a376d1550 (origin/main, main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200

    modify the service list

commit 4bf0aff5c1d3197022c9bc18db38d838f6792293 (origin/ft/service-redesign)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:00:24 2022 +0200

    change the service list

commit 8ea7ed6973251a2854fd972a1e2c34659d52fd97
Merge: dc53f3a 71c1b48
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:47 2022 -0700

    Merge pull request #3 from izzett222/revert-2-ft/service-redesign

    Revert "Ft/service redesign"

commit 71c1b48d14640fc5922537cd556b454976c52a77 (origin/revert-2-ft/service-redesign)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 435 bytes | 108.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:izzett222/git-exercises.git
   4bf0aff..86ed0a7  ft/service-redesign -> ft/service-redesign
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
