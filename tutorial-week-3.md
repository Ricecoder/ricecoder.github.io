##How to Avoid Merge Conflicts When Starting An Assignment:
Getting merge conflicts as you are starting an assignment is a bummer! Here are some steps to take before you begin to help prevent them.

1. Create your Issue.
2. Go to your TERMINAL and do a quick `git status` to make sure you have nothing you need to **push** to Github. 
3. Go back to Github and click on Pull Requests in the upper nav bar and **MERGE** all open PRs from the last assignment. 
4. Create your new branch in TIY-Assignments.
4. Now go back to your TERMINAL and do `git pull` to bring the new branch down to your LOCAL repository. 
5. Do `git checkout <new branch name here>` to change to that branch. 
6. You should now be good to go! 

###What to do if you didn't push first:
You made your issue and merged all your open PRs, but when you went to your terminal to pull down your new branch you realize you still have changes to a file that you never pushed to the branch you just merged. OH NO! What should you do.....?

1. In the terminal check that you are on the branch you were supposed to merge to. 
2. `git add` the untracked file.
3. `git commit`
4. `git push` At this point you will probably see:
```
❯❯❯ git push
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 577 bytes | 0 bytes/s, done.
Total 5 (delta 3), reused 0 (delta 0)
To https://github.com/<your account/branch>
   1f57eeb..78d4558 <branch> -> <branch>
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/<your account/branch>
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
5. DON"T WORRY! The file did go through but you still have more work.
6. `git pull`
7. You should now get a message that looks like this:
```
❯❯❯ git pull                                                                ⏎
remote: Counting objects: 1, done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), done.
From https://github.com/<your account/branch>
   5680353..e57a8fe  master     -> origin/master
Already up-to-date.
```
9. You're **not** done yet!
10. Go to your master branch (that's probably where you were trying to go before you realized you had an untracked file)
11. You will see something that looks like this:
```
❯❯❯ git checkout master                                                     ⏎
Switched to branch 'master'
Your branch is behind 'origin/master' by (#) commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
```  
11. Now let's do what it suggests `git pull`
12. You'll probably see a whole bunch of files at this point because, remember, you just merged your branch with master. 
13. Now you can `git checkout` your new branch and move on to the next thing.


Remember: 
* `git status` is your friend. 
* `git branch -l` lists the branches in your current repo and stars the branch you are on. 
* If you do get a merge conflict start by trying to mentally figure out what could be causing it. It is much easier to fix a merge conflict if you know what went wrong.
