# testing
on github
on github for conflict
on local

C:\Users\Sham>e:

E:\>cd git

E:\git>mkdir exp7

E:\git>cd exp7

E:\git\exp7>git init
Initialized empty Git repository in E:/git/exp7/.git/

E:\git\exp7>git add f1.txt

E:\git\exp7>git commit -m "master"
[master (root-commit) 161e186] master
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 f1.txt

E:\git\exp7>git checkout -b fb
Switched to a new branch 'fb'

E:\git\exp7>f1.txt

E:\git\exp7>git add f1.txt

E:\git\exp7>git commit -m "fb1"
[fb 1edf91a] fb1
 1 file changed, 1 insertion(+)

E:\git\exp7>f1.txt

E:\git\exp7>git add f1.txt

E:\git\exp7>git commit -m "fb1 2"
[fb f2fae16] fb1 2
 1 file changed, 2 insertions(+), 1 deletion(-)

E:\git\exp7>f1.txt

E:\git\exp7>git add f1.txt

E:\git\exp7>git commit -m "fb1 3"
[fb 43323c5] fb1 3
 1 file changed, 2 insertions(+), 1 deletion(-)

E:\git\exp7>git log
commit 43323c59dbce213c2d23bfe97d2e8f39d1116840 (HEAD -> fb)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

commit f2fae16ba1cc532ffe876a6cb4b11a9d2658078d
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:04 2024 +0530

    fb1 2

commit 1edf91a933ca0ead403e5d82ee125cab50a644d9
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:43:46 2024 +0530

    fb1

commit 161e186e8bebb7936e1696b64f9797e4646c0616 (master)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:42:02 2024 +0530

    master

E:\git\exp7>git tag fb1

E:\git\exp7>git tag -d fb1
Deleted tag 'fb1' (was 43323c5)

E:\git\exp7>git tag fb1

E:\git\exp7>git tag -d fb1
error: tag 'fb1' not found.

E:\git\exp7>git tag fb1 1edf91a933ca0ead403e5d82ee125cab50a644d9

E:\git\exp7>git tag last

E:\git\exp7>git log
commit 43323c59dbce213c2d23bfe97d2e8f39d1116840 (HEAD -> fb, tag: last)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

commit f2fae16ba1cc532ffe876a6cb4b11a9d2658078d
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:04 2024 +0530

    fb1 2

commit 1edf91a933ca0ead403e5d82ee125cab50a644d9 (tag: fb1)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:43:46 2024 +0530

    fb1

commit 161e186e8bebb7936e1696b64f9797e4646c0616 (master)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:42:02 2024 +0530

    master

E:\git\exp7>git tag -d last
Deleted tag 'last' (was 43323c5)

E:\git\exp7>git checkout master
Switched to branch 'master'

E:\git\exp7>git checkout -b tb
Switched to a new branch 'tb'

E:\git\exp7>git --cherry-pick 1edf91a933ca0ead403e5d82ee125cab50a644d9^..43323c59dbce213c2d23bfe97d2e8f39d1116840
unknown option: --cherry-pick
usage: git [-v | --version] [-h | --help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--config-env=<name>=<envvar>] <command> [<args>]

E:\git\exp7>git cherry-pick 1edf91a933ca0ead403e5d82ee125cab50a644d9^..43323c59dbce213c2d23bfe97d2e8f39d1116840
Auto-merging f1.txt
CONFLICT (content): Merge conflict in f1.txt
error: could not apply f2fae16... fb1 2
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
hint: run "git cherry-pick --abort".

E:\git\exp7>f1.txt

E:\git\exp7>git add .

E:\git\exp7>git cherry-pick --continue
[tb 75d6e83] fb1 2
 Date: Thu Mar 21 23:44:04 2024 +0530
 1 file changed, 3 insertions(+)
Auto-merging f1.txt
CONFLICT (content): Merge conflict in f1.txt
error: could not apply 43323c5... fb1 3
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
hint: run "git cherry-pick --abort".

E:\git\exp7>f1.txt

E:\git\exp7>git add .

E:\git\exp7>git cherry-pick --continue
[tb 9cae370] fb1 3
 Date: Thu Mar 21 23:44:19 2024 +0530
 1 file changed, 1 insertion(+), 1 deletion(-)

E:\git\exp7>git log
commit 9cae370750c64b890d5164a12096001febd56c17 (HEAD -> tb)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

commit 75d6e839a096e66f56fa0a931f2910a371568651
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:04 2024 +0530

    fb1 2

commit 161e186e8bebb7936e1696b64f9797e4646c0616 (master)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:42:02 2024 +0530

    master

E:\git\exp7>git show 43323c59dbce213c2d23bfe97d2e8f39d1116840
commit 43323c59dbce213c2d23bfe97d2e8f39d1116840 (fb)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

diff --git a/f1.txt b/f1.txt
index 70e8a1f..5c891d8 100644
--- a/f1.txt
+++ b/f1.txt
@@ -1,2 +1,3 @@
 hi
-hello
\ No newline at end of file
+hello
+hola
\ No newline at end of file

E:\git\exp7>git log -n 2 43323c59dbce213c2d23bfe97d2e8f39d1116840
commit 43323c59dbce213c2d23bfe97d2e8f39d1116840 (fb)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

commit f2fae16ba1cc532ffe876a6cb4b11a9d2658078d
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:04 2024 +0530

    fb1 2

E:\git\exp7>git log -n 2
commit 9cae370750c64b890d5164a12096001febd56c17 (HEAD -> tb)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

commit 75d6e839a096e66f56fa0a931f2910a371568651
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:04 2024 +0530

    fb1 2

E:\git\exp7>git config --global -l
core.editor="C:\Users\Sham\AppData\Local\Programs\Microsoft VS Code\bin\code" --wait
user.name=sham
user.email=sham@gmail.com

E:\git\exp7>git log --author="sham" --since="2024-01-01" --until="2024-03-21"
commit 9cae370750c64b890d5164a12096001febd56c17 (HEAD -> tb)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

commit 75d6e839a096e66f56fa0a931f2910a371568651
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:04 2024 +0530

    fb1 2

commit 161e186e8bebb7936e1696b64f9797e4646c0616 (master)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:42:02 2024 +0530

    master

E:\git\exp7>git log
commit 9cae370750c64b890d5164a12096001febd56c17 (HEAD -> tb)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

commit 75d6e839a096e66f56fa0a931f2910a371568651
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:04 2024 +0530

    fb1 2

commit 161e186e8bebb7936e1696b64f9797e4646c0616 (master)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:42:02 2024 +0530

    master

E:\git\exp7>f1.txt

E:\git\exp7>git revert 9cae370750c64b890d5164a12096001febd56c17
[tb 838a9dd] Revert "fb1 3"
 1 file changed, 1 insertion(+), 1 deletion(-)

E:\git\exp7>git log
commit 838a9dd99b8169fa75bd0062bc0aaeaf0e6bb11d (HEAD -> tb)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:56:51 2024 +0530

    Revert "fb1 3"

    This reverts commit 9cae370750c64b890d5164a12096001febd56c17.

commit 9cae370750c64b890d5164a12096001febd56c17
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:19 2024 +0530

    fb1 3

commit 75d6e839a096e66f56fa0a931f2910a371568651
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:44:04 2024 +0530

    fb1 2

commit 161e186e8bebb7936e1696b64f9797e4646c0616 (master)
Author: sham <sham@gmail.com>
Date:   Thu Mar 21 23:42:02 2024 +0530

    master

E:\git\exp7>f1.txt

E:\git\exp7>
