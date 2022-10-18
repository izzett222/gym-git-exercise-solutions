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
