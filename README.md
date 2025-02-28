# The Gym Advanced Git challenges

## Part 1: Refining Git History (10 challenges)

## 1. Missing File Fix:
```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ touch test{1..4}.md

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add test1.md && git commit -m "chore: Create initial file"
[main (root-commit) 4ddcb4d] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add test2.md && git commit -m "chore: Create another file"
[main 8acc478] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
 
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add test3.md && git commit -m "chore: Create third and fourth files"
[main 1d221fc] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git log
commit 1d221fc5e5513137742f53bbd735e30d4109d32f (HEAD -> main)
Author: Mugara250 <mbonyumugara52@gmail.com>
Date:   Fri Feb 28 19:39:39 2025 +0200

    chore: Create third and fourth files

commit 8acc478433fb9521e190fad4cf89e150ac1309fd
Author: Mugara250 <mbonyumugara52@gmail.com>
Date:   Fri Feb 28 19:38:53 2025 +0200

    chore: Create another file

commit 4ddcb4d65058823c7fd67adc1ec5b78928333bf7
Author: Mugara250 <mbonyumugara52@gmail.com>
Date:   Fri Feb 28 19:38:27 2025 +0200

    chore: Create initial file
    
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add test4.md && git commit --amend -m "chore: Create third and fourth files"
[main 57a3590] chore: Create third and fourth files
 Date: Fri Feb 28 19:39:39 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
```

## 2. Editing Commit History:
```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git rebase -i HEAD~2
Stopped at 8acc478...  chore: Create another file
You can amend the commit now, with

  git commit --amend 

Once you are satisfied with your changes, run

  git rebase --continue
 
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git commit --amend -m "chore: Create second file"
[detached HEAD 84cc19b] chore: Create second file
 Date: Fri Feb 28 19:38:53 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git rebase --continue
Successfully rebased and updated refs/heads/main.
```

## 3. Keeping History Tidy - Squashing Commits:
```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git rebase -i --root
[detached HEAD 574d1ec] chore: Create initial file and second file chore: Create initial file
 Date: Fri Feb 28 19:38:27 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
```

## 4. Splitting a Commit
```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git rebase -i 1d221fc
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

    git commit --allow-empty

Otherwise, please use 'git rebase --skip'
interactive rebase in progress; onto 1d221fc
Last command done (1 command done):
   pick 574d1ec chore: Create initial file and second file chore: Create initial file
Next command to do (1 remaining command):
   edit f9f29fa chore: Create third and fourth files
  (use "git rebase --edit-todo" to view and edit)
You are currently rebasing branch 'main' on '1d221fc'.
  (all conflicts fixed: run "git rebase --continue")

nothing to commit, working tree clean
Could not apply 574d1ec... chore: Create initial file and second file chore: Create initial file

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git reset HEAD~

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git status
interactive rebase in progress; onto 1d221fc
Last command done (1 command done):
   pick 574d1ec chore: Create initial file and second file chore: Create initial file
Next command to do (1 remaining command):
   edit f9f29fa chore: Create third and fourth files
  (use "git rebase --edit-todo" to view and edit)
You are currently editing a commit while rebasing branch 'main' on '1d221fc'.
  (use "git commit --amend" to amend the current commit)
  (use "git rebase --continue" once you are satisfied with your changes)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test3.md

nothing added to commit but untracked files present (use "git add" to track)

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add test3.md && git commit -m "chore: Create third file"
[detached HEAD c531eaa] chore: Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git log --oneline
c531eaa (HEAD) chore: Create third file
8acc478 chore: Create another file
4ddcb4d chore: Create initial file

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ ls
test1.md  test2.md  test3.md

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ touch test4.md

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add test4.md && git commit -m "chore: Create fourth file"
[detached HEAD 6fc9ee2] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
```

## 5. Advanced Squashing:

```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git rebase -i HEAD~3
[detached HEAD 3c7cf26] chore: Create third and fourth files
 Date: Fri Feb 28 20:03:35 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
```

## 6. Dropping a commit

```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ echo "Unwanted changes in an unwanted file" >> unwanted.txt

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add unwanted.txt && git commit -m "Unwanted commit"
[main bd2d52f] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git log --oneline
bd2d52f (HEAD -> main) Unwanted commit
3c7cf26 chore: Create third and fourth files
8acc478 chore: Create another file
4ddcb4d chore: Create initial file

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git reset --hard HEAD~1
HEAD is now at 3c7cf26 chore: Create third and fourth files
```

## OR
```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ echo "Unwanted changes in an unwanted file" >> unwanted.txt

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add unwanted.txt && git commit -m "Unwanted commit"
[main 1414f83] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/main.

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git log --oneline
3c7cf26 (HEAD -> main) chore: Create third and fourth files
8acc478 chore: Create another file
4ddcb4d chore: Create initial file
```

## 7. Reordering Commits:

```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git log --oneline
3c7cf26 (HEAD -> main) chore: Create third and fourth files
8acc478 chore: Create another file
4ddcb4d chore: Create initial file

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git rebase -i --root
Successfully rebased and updated refs/heads/main.
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git log --oneline
97450dd (HEAD -> main) chore: Create initial file
ebc9d75 chore: Create another file
569c2ae chore: Create third and fourth files
```

## 8. Cherry-picking Commits:

```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ echo "New file called test5.md" >> test5.md

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git add test5.md && git commit -m "Implemented test5"
[ft/branch e8360aa] Implemented test5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
 
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)
  
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git cherry-pick --no-commit e8360aa

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git commit -m "Cherry picked e8360aa commit from ft/branch"
[main f7aa2d3] Cherry picked e8360aa commit from ft/branch
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git log --oneline
f7aa2d3 (HEAD -> main) Cherry picked e8360aa commit from ft/branch
97450dd chore: Create initial file
ebc9d75 chore: Create another file
569c2ae chore: Create third and fourth files
```

## 9. Visualizing Commit History (Bonus):

```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git log --graph
* commit f7aa2d3a39d37fecbb9e3b637dc00f23b53ae78e (HEAD -> main)
| Author: Mugara250 <mbonyumugara52@gmail.com>
| Date:   Fri Feb 28 21:35:24 2025 +0200
| 
|     Cherry picked e8360aa commit from ft/branch
| 
* commit 97450dd1e9d3fb6033d253bb4f8355d8b1b0dcf3
| Author: Mugara250 <mbonyumugara52@gmail.com>
| Date:   Fri Feb 28 19:38:27 2025 +0200
| 
|     chore: Create initial file
| 
* commit ebc9d75660968d13d1490838b3ab866a320c57ca
| Author: Mugara250 <mbonyumugara52@gmail.com>
| Date:   Fri Feb 28 19:38:53 2025 +0200
| 
|     chore: Create another file
```

## 10. Understanding Reflogs (Bonus):

```
mugara@mugara-Lenovo-Yoga-C940-14IIL:~/Gym_Git_Exercises/The_Gym_Git_Advanced$ git reflog
f7aa2d3 (HEAD -> main) HEAD@{0}: commit: Cherry picked e8360aa commit from ft/branch
97450dd HEAD@{1}: checkout: moving from ft/branch to main
e8360aa (ft/branch) HEAD@{2}: checkout: moving from main to ft/branch
97450dd HEAD@{3}: checkout: moving from ft/branch to main
e8360aa (ft/branch) HEAD@{4}: commit: Implemented test5
97450dd HEAD@{5}: checkout: moving from main to ft/branch
97450dd HEAD@{6}: rebase (finish): returning to refs/heads/main
97450dd HEAD@{7}: rebase (pick): chore: Create initial file
ebc9d75 HEAD@{8}: rebase (pick): chore: Create another file
569c2ae HEAD@{9}: rebase (pick): chore: Create third and fourth files
eb40e59 HEAD@{10}: rebase (start): checkout eb40e59a484e0e59f98f9488d83220cc60d509ea
3c7cf26 HEAD@{11}: rebase (finish): returning to refs/heads/main
3c7cf26 HEAD@{12}: rebase: fast-forward
8acc478 HEAD@{13}: rebase: fast-forward
4ddcb4d HEAD@{14}: rebase: fast-forward
e6f9abb HEAD@{15}: rebase (start): checkout e6f9abb1ba4bf9741e09d07636902edbdd0f2fab
3c7cf26 HEAD@{16}: rebase (finish): returning to refs/heads/main
```