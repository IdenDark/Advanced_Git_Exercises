# Advanced_Git_Exercises

####Excercise 5: Advanced Squashing.

```bash
$ git log --oneline --decorate
pick e27f8d1 Chore: Creaete third file
# This is a combination of 2 commits.
```

```bash
[detached HEAD 1a28287] Chore: Creaete third and fourth file
Date: Mon Mar 10 11:45:42 2025 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test3.md
create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (main)
$ git log --oneline --graph --decorate --all

- 1a28287 (HEAD -> main) Chore: Creaete third and fourth file
  | _ b7c4736 (origin/main, origin/HEAD) Chore: Create fourth file
  | _ e27f8d1 Chore: Creaete third file
  |/
- 3cb1f55 Chore: Create initial and second files
- ea4e704 Initial commit
```

#####Excersise 6:Dropping a commit

```bash
$ touch unwanted.txt

SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (main)
$ echo "Just temporary" > unwanted.txt
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (main)
$ git add unwanted.txt
warning: in the working copy of 'unwanted.txt', LF will be replaced by CRLF the
next time Git touches it
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (main)
$ git commit -m "Unwanted Commit"
[main a4575d1] Unwanted Commit
1 file changed, 1 insertion(+)
create mode 100644 unwanted.txt
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (main)
$ git log --oneline --graph --decorate --all

- a4575d1 (HEAD -> main) Unwanted Commit
- 1a28287 (origin/main, origin/HEAD) Chore: Creaete third and fourth file
- 3cb1f55 Chore: Create initial and second files
- ea4e704 Initial commit
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (main)
$ git reset --hard HEAD~1
HEAD is now at 1a28287 Chore: Creaete third and fourth file
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (main)
$ git log --oneline --graph --decorate --all

- 1a28287 (HEAD -> main, origin/main, origin/HEAD) Chore: Creaete third and four
  th file
- 3cb1f55 Chore: Create initial and second files
- ea4e704 Initial commit
```

######Exercise 7: Reordering commit messages.

```bash
git rebase -i HEAD~2

pick 3cb1f55 Chore: Create initial and second files
pick 1a28287 Chore: Create third and fourth file
pick ea4e704 Initial commit
```

#######Exercise 8: Cherry Pick

```bash
$ echo "Test 5 this is!!" > test5.md
echo "Test 5 this isgit checkout -b ft/branch" > test5.md
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (ft/branch)
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next
 time Git touches it
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (ft/branch)
$ git commit -m "Implemented test 5"
[ft/branch aa7def9] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
```

```bash
$ git cherry-pick aa7def9
[main 3ebb92e] Implemented test 5
 Date: Tue Mar 11 13:25:10 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
```

```bash
SYNDICATE@DESKTOP-LVM290F MINGW64 ~/Documents/GYM/Advanced_Git_Exercises (main)
$ git log --oneline
3ebb92e (HEAD -> main) Implemented test 5
7162fdb (origin/main, origin/HEAD) Chore: Create initial and second files
b6da832 Chore: Creaete third and fourth file
ea4e704 Initial commit
```
