##How to `git stash` in Terminal

Have you ever found yourself unable to change branchs in terminal because you have modified files that you don't want to commit? Then `git stash` is the command for you! `git stash` allows you to save your untracked files from your working directory so that you can reapply them later on. 

###How does this work?

1.) In your terminal do `git status`:
```
$ git status
On branch one
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)
  
    modified:   main.js
    
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  
    modified:   tutorial.md
```    
2.) To save these files do `git stash`:
```
$ git stash
Saved working directory and index state \
  "WIP on master: 0ccec3d added the main file"
HEAD is now at 0ccec3d added the main file
(To restore them type "git stash apply")
```
What just happened? Git has saved your working directory i.e. main.js and tutorial.md and saved it to `0ccec3d`. If you were to `git status` your working directory would be clean. You may now switch your branches.

3.) When you're ready to reapply your files (on the original branch _or_ a different branch), simply type `git stash apply`. 

```
$git stash apply
On branch two 
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  
    modified: main.js
    modified: tutorial.md
```
4.) Now you can simply `git add`, `git commit`, and `git push`.
  
###Extras:

* You can `stash` more than one time. Each stash will be added to a `stash list`. You can view this list with `git stash list`
```
$ git stash list
stash@{0}: WIP on branch: 036h37 added files
stash@{1}: WIP on branch: 048gy35 added more files
```
To access the stash you just added simply do `git stash apply` but to access a previous stash `git stash apply stash@{#}` where `#` represents the number of the stash you want. 




https://git-scm.com/book/en/v1/Git-Tools-Stashing
