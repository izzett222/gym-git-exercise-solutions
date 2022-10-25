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
## bundle 3
### exercise 1
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/service-redesign
Your branch is up to date with 'origin/ft/service-redesign'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout -b ft/team-page
Switched to a new branch 'ft/team-page'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ code .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/team-page
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "add the team page"
[ft/team-page 02310a2] add the team page
 1 file changed, 12 insertions(+)
 create mode 100644 team.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
fatal: The current branch ft/team-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/team-page

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push --set-upstream origin ft/team-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 471 bytes | 235.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/ft/team-page
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      ft/team-page -> ft/team-page
Branch 'ft/team-page' set up to track remote branch 'ft/team-page' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git branch ft/contact-page
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git branch
  dev
  ft/bundle-2
  ft/contact-page
  ft/service-redesign
  ft/team-page
* main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout ft/team-page
Switched to branch 'ft/team-page'
Your branch is up to date with 'origin/ft/team-page'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit 02310a23600506b37d5059b79abf9a0a4379948e (HEAD -> ft/team-page, origin/ft/team-page)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 09:39:49 2022 +0200

    add the team page

commit c6f7632923fad35faee5ae1a1395c91a376d1550 (origin/main, main, ft/contact-page)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200

    modify the service list

commit 8ea7ed6973251a2854fd972a1e2c34659d52fd97
Merge: dc53f3a 71c1b48
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:47 2022 -0700

    Merge pull request #3 from izzett222/revert-2-ft/service-redesign

    Revert "Ft/service redesign"

commit 71c1b48d14640fc5922537cd556b454976c52a77 (origin/revert-2-ft/service-redesign)
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:33 2022 -0700

    Revert "Ft/service redesign"

commit dc53f3abeca1b6976b563e6cd0eafdb2b821a8e4
Merge: c7e482c 2d1abd5
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/team-page
Your branch is up to date with 'origin/ft/team-page'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout ft/contact-page
Switched to branch 'ft/contact-page'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit c6f7632923fad35faee5ae1a1395c91a376d1550 (HEAD -> ft/contact-page, origin/main, main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200

    modify the service list

commit 8ea7ed6973251a2854fd972a1e2c34659d52fd97
Merge: dc53f3a 71c1b48
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:47 2022 -0700

    Merge pull request #3 from izzett222/revert-2-ft/service-redesign

    Revert "Ft/service redesign"

commit 71c1b48d14640fc5922537cd556b454976c52a77 (origin/revert-2-ft/service-redesign)
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:33 2022 -0700

    Revert "Ft/service redesign"

commit dc53f3abeca1b6976b563e6cd0eafdb2b821a8e4
Merge: c7e482c 2d1abd5
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Thu Oct 20 12:02:21 2022 +0200

    Merge branch 'ft/service-redesign'

commit c7e482cb492980a4471af00043d767762f58c25f
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git cherry-pick 02310a23600506b37d5059b79abf9a0a4379948e
[ft/contact-page 8c085de] add the team page
 Date: Mon Oct 24 09:39:49 2022 +0200
 1 file changed, 12 insertions(+)
 create mode 100644 team.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit 8c085de5e7568344f2bc7f3702399e369363bcab (HEAD -> ft/contact-page)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 09:39:49 2022 +0200

    add the team page

commit c6f7632923fad35faee5ae1a1395c91a376d1550 (origin/main, main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200

    modify the service list

commit 8ea7ed6973251a2854fd972a1e2c34659d52fd97
Merge: dc53f3a 71c1b48
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:47 2022 -0700

    Merge pull request #3 from izzett222/revert-2-ft/service-redesign

    Revert "Ft/service redesign"

commit 71c1b48d14640fc5922537cd556b454976c52a77 (origin/revert-2-ft/service-redesign)
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:33 2022 -0700

    Revert "Ft/service redesign"

commit dc53f3abeca1b6976b563e6cd0eafdb2b821a8e4
Merge: c7e482c 2d1abd5
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/contact-page
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ ls
about.html  home.html  README.md  services.html  team.html  test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/contact-page
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        contact.html

nothing added to commit but untracked files present (use "git add" to track)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "add contact page"
[ft/contact-page fd56bcc] add contact page
 1 file changed, 12 insertions(+)
 create mode 100644 contact.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
fatal: The current branch ft/contact-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/contact-page

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push --set-upstream origin ft/contact-page
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 742 bytes | 247.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/ft/contact-page
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      ft/contact-page -> ft/contact-page
Branch 'ft/contact-page' set up to track remote branch 'ft/contact-page' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout -b ft/faq-page
Switched to a new branch 'ft/faq-page'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/faq-page
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/faq-page
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        faq.html

nothing added to commit but untracked files present (use "git add" to track)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add faq.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "add faq page"
[ft/faq-page 6752eaa] add faq page
 1 file changed, 12 insertions(+)
 create mode 100644 faq.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
fatal: The current branch ft/faq-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/faq-page

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push --set-upstream origin ft/faq-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 465 bytes | 465.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/ft/faq-page
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      ft/faq-page -> ft/faq-page
Branch 'ft/faq-page' set up to track remote branch 'ft/faq-page' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit 6752eaa838a924a29d38dd4093d7cb8e1e665004 (HEAD -> ft/faq-page, origin/ft/faq-page)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:31:33 2022 +0200

    add faq page

commit fd56bcce818b0a044a566fcddbd5c746878f0724 (origin/ft/contact-page, ft/contact-page)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:27:41 2022 +0200

    add contact page

commit 8c085de5e7568344f2bc7f3702399e369363bcab
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 09:39:49 2022 +0200

    add the team page

commit c6f7632923fad35faee5ae1a1395c91a376d1550 (origin/main, main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200

    modify the service list

commit 8ea7ed6973251a2854fd972a1e2c34659d52fd97
Merge: dc53f3a 71c1b48
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:47 2022 -0700

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/faq-page
Your branch is up to date with 'origin/ft/faq-page'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git revert 02310a23600506b37d5059b79abf9a0a4379948e
[ft/faq-page bad315c] Revert "add the team page"
 1 file changed, 12 deletions(-)
 delete mode 100644 team.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit bad315c0a222ab402a22af915ba8f57da42f2c89 (HEAD -> ft/faq-page)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:47:42 2022 +0200

    Revert "add the team page"

    This reverts commit 02310a23600506b37d5059b79abf9a0a4379948e.

commit 6752eaa838a924a29d38dd4093d7cb8e1e665004 (origin/ft/faq-page)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:31:33 2022 +0200

    add faq page

commit fd56bcce818b0a044a566fcddbd5c746878f0724 (origin/ft/contact-page, ft/contact-page)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:27:41 2022 +0200

    add contact page

commit 8c085de5e7568344f2bc7f3702399e369363bcab
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 09:39:49 2022 +0200

    add the team page

commit c6f7632923fad35faee5ae1a1395c91a376d1550 (origin/main, main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ ls
about.html  contact.html  faq.html  home.html  README.md  services.html  test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 275 bytes | 275.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:izzett222/git-exercises.git
   6752eaa..bad315c  ft/faq-page -> ft/faq-page
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
### exercise 2
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/faq-page
Your branch is up to date with 'origin/ft/faq-page'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout -b ft/home-page-redesign
Switched to a new branch 'ft/home-page-redesign'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ ls
about.html  home.html  README.md  services.html  test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi home.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   home.html

no changes added to commit (use "git add" and/or "git commit -a")
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit c6f7632923fad35faee5ae1a1395c91a376d1550 (HEAD -> main, origin/main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200

    modify the service list

commit 8ea7ed6973251a2854fd972a1e2c34659d52fd97
Merge: dc53f3a 71c1b48
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:47 2022 -0700

    Merge pull request #3 from izzett222/revert-2-ft/service-redesign

    Revert "Ft/service redesign"

commit 71c1b48d14640fc5922537cd556b454976c52a77 (origin/revert-2-ft/service-redesign)
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:33 2022 -0700

    Revert "Ft/service redesign"

commit dc53f3abeca1b6976b563e6cd0eafdb2b821a8e4
Merge: c7e482c 2d1abd5
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Thu Oct 20 12:02:21 2022 +0200

    Merge branch 'ft/service-redesign'

commit c7e482cb492980a4471af00043d767762f58c25f
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "add welcome message on the homepage"
[main 40b138e] add welcome message on the homepage
 1 file changed, 3 insertions(+), 2 deletions(-)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 352 bytes | 352.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:izzett222/git-exercises.git
   c6f7632..40b138e  main -> main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit 40b138ea76110837914c8515c31e526a5b9ce969 (HEAD -> main, origin/main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:56:59 2022 +0200

    add welcome message on the homepage

commit c6f7632923fad35faee5ae1a1395c91a376d1550
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200

    modify the service list

commit 8ea7ed6973251a2854fd972a1e2c34659d52fd97
Merge: dc53f3a 71c1b48
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:47 2022 -0700

    Merge pull request #3 from izzett222/revert-2-ft/service-redesign

    Revert "Ft/service redesign"

commit 71c1b48d14640fc5922537cd556b454976c52a77 (origin/revert-2-ft/service-redesign)
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:33 2022 -0700

    Revert "Ft/service redesign"

commit dc53f3abeca1b6976b563e6cd0eafdb2b821a8e4
Merge: c7e482c 2d1abd5
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout ft/home-page-redesign
Switched to branch 'ft/home-page-redesign'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git rebase main
Successfully rebased and updated refs/heads/ft/home-page-redesign.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit fa1aaac7b445fb491e1d38eb4b17f5e6fdb2a901 (HEAD -> ft/home-page-redesign)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:47:42 2022 +0200

    Revert "add the team page"

    This reverts commit 02310a23600506b37d5059b79abf9a0a4379948e.

commit 6b51be3c478b90b92bb1977e1f70da1915700a38
Author: izzett222 <iizzeddin62@gmail.com>

    Revert "add the team page"

    This reverts commit 02310a23600506b37d5059b79abf9a0a4379948e.

commit fa1aaac7b445fb491e1d38eb4b17f5e6fdb2a901 (HEAD -> ft/home-page-redesign)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:47:42 2022 +0200

    Revert "add the team page"

    This reverts commit 02310a23600506b37d5059b79abf9a0a4379948e.

commit 6b51be3c478b90b92bb1977e1f70da1915700a38
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:31:33 2022 +0200

    add faq page

commit ebcc5121e24cb5068f09de3841849c59b3e7fbf4
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:27:41 2022 +0200

    add contact page

commit d8be263403a90c6b89062d4e22f0c424ec00ae9f
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 09:39:49 2022 +0200

    add the team page

commit 40b138ea76110837914c8515c31e526a5b9ce969 (origin/main, main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:56:59 2022 +0200
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi home.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/home-page-redesign
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   home.html

no changes added to commit (use "git add" and/or "git commit -a")
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add ,
fatal: pathspec ',' did not match any files
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add home.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/home-page-redesign
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   home.html

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "change welcome message on the homepage"
[ft/home-page-redesign a657342] change welcome message on the homepage
 1 file changed, 2 insertions(+), 2 deletions(-)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
fatal: The current branch ft/home-page-redesign has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/home-page-redesign

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push --set-upstream origin ft/home-page-redesign
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.
Delta compression using up to 4 threads
Compressing objects: 100% (14/14), done.
Writing objects: 100% (14/14), 1.62 KiB | 553.00 KiB/s, done.
Total 14 (delta 7), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (7/7), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/ft/home-page-redesign
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign
Branch 'ft/home-page-redesign' set up to track remote branch 'ft/home-page-redesign' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
## bundle 4
### exercise 1
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/home-page-redesign
Your branch is up to date with 'origin/ft/home-page-redesign'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git remote add git-copy git@github.com:izzett222/git-exercises-copy.git
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git remote -v
git-copy        git@github.com:izzett222/git-exercises-copy.git (fetch)
git-copy        git@github.com:izzett222/git-exercises-copy.git (push)
origin  git@github.com:izzett222/git-exercises.git (fetch)
origin  git@github.com:izzett222/git-exercises.git (push)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi home.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "add homepage header section"
[main b6c1bd1] add homepage header section
 1 file changed, 1 insertion(+)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 321 bytes | 321.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:izzett222/git-exercises.git
   40b138e..b6c1bd1  main -> main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push git-copy main
Enumerating objects: 35, done.
Counting objects: 100% (35/35), done.
Delta compression using up to 4 threads
Compressing objects: 100% (32/32), done.
Writing objects: 100% (35/35), 5.01 KiB | 732.00 KiB/s, done.
Total 35 (delta 15), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (15/15), done.
To github.com:izzett222/git-exercises-copy.git
 * [new branch]      main -> main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
### exercise 2
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout -b ft/footer
Switched to a new branch 'ft/footer'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ ls
about.html  home.html  README.md  services.html  test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi home.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "add footer to the home page"
[ft/footer feb93d8] add footer to the home page
 1 file changed, 3 insertions(+)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ vi home.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/footer
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   home.html

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "add a list of links to the footer on the homepage"
[ft/footer 5a26d2e] add a list of links to the footer on the homepage
 1 file changed, 3 insertions(+)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push origin main
Everything up-to-date
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
fatal: The current branch ft/footer has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/footer

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push --set-upstream origin ft/footer
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 640 bytes | 320.00 KiB/s, done.
Total 6 (delta 4), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (4/4), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/footer' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/ft/footer
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      ft/footer -> ft/footer
Branch 'ft/footer' set up to track remote branch 'ft/footer' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout -b ft/squashing
Switched to a new branch 'ft/squashing'
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/squashing
nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git merge --squash ft/footer
Updating b6c1bd1..5a26d2e
Fast-forward
Squash commit -- not updating HEAD
 home.html | 6 ++++++
 1 file changed, 6 insertions(+)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/squashing
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   home.html

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "footer changes squashing"
[ft/squashing b8eadf7] footer changes squashing
 1 file changed, 6 insertions(+)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git log
commit b8eadf7191ec5e59d10efd06a4256f50a7cfdddb (HEAD -> ft/squashing)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 11:38:04 2022 +0200

    footer changes squashing

commit b6c1bd13622633bf1950e5eb5a0f0bb0ce462ca2 (origin/main, git-copy/main, main)
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 11:14:08 2022 +0200

    add homepage header section

commit 40b138ea76110837914c8515c31e526a5b9ce969
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Mon Oct 24 10:56:59 2022 +0200

    add welcome message on the homepage

commit c6f7632923fad35faee5ae1a1395c91a376d1550
Author: izzett222 <iizzeddin62@gmail.com>
Date:   Sun Oct 23 22:06:26 2022 +0200

    modify the service list

commit 8ea7ed6973251a2854fd972a1e2c34659d52fd97
Merge: dc53f3a 71c1b48
Author: izzett222 <51261911+izzett222@users.noreply.github.com>
Date:   Thu Oct 20 03:06:47 2022 -0700

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
fatal: The current branch ft/squashing has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/squashing

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push --set-upstream origin ft/squashing
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 382 bytes | 127.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/squashing' on GitHub by visiting:
remote:      https://github.com/izzett222/git-exercises/pull/new/ft/squashing
remote:
To github.com:izzett222/git-exercises.git
 * [new branch]      ft/squashing -> ft/squashing
Branch 'ft/squashing' set up to track remote branch 'ft/squashing' from 'origin'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
## bundle 5
### exercise 1
```bash
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch ft/squashing
Your branch is up to date with 'origin/ft/squashing'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ ls
about.html  home.html  README.md  services.html  test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ mv home.html index.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ ls
about.html  index.html  README.md  services.html  test
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ code .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    home.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html

no changes added to commit (use "git add" and/or "git commit -a")
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    home.html -> index.html

thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git commit -m "rename home.html to index.html"
[main 3b897ce] rename home.html to index.html
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename home.html => index.html (100%)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 240 bytes | 240.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:izzett222/git-exercises.git
   b6c1bd1..3b897ce  main -> main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-exercises$
```
### exercise 2
```bash
thegym@DESKTOP-JIQ9UQP:~$ cd thegym/
thegym@DESKTOP-JIQ9UQP:~/thegym$ git clone git@github.com:izzett222/git-cafe-exercise.git
Cloning into 'git-cafe-exercise'...
remote: Enumerating objects: 107, done.
remote: Counting objects: 100% (107/107), done.
remote: Compressing objects: 100% (101/101), done.
remote: Total 107 (delta 5), reused 104 (delta 4), pack-reused 0
Receiving objects: 100% (107/107), 1.95 MiB | 1.73 MiB/s, done.
Resolving deltas: 100% (5/5), done.
thegym@DESKTOP-JIQ9UQP:~/thegym$ cd git-cafe-exercise/
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$ ls
bat  css  images  index-1.html  index-2.html  index-3.html  index-4.html  index.html  js  README.md
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$ vi index.html
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$ code .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$ git add .
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$ git commit -m "change the homepage main title"
[main 36fb092] change the homepage main title
 1 file changed, 1 insertion(+), 1 deletion(-)
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 326 bytes | 326.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:izzett222/git-cafe-exercise.git
   d1d3f9c..36fb092  main -> main
thegym@DESKTOP-JIQ9UQP:~/thegym/git-cafe-exercise$
```
