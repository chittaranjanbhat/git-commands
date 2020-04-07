# git-commands

## Undoing/Reverting/Resetting code changes

### Undoing uncommited changes
git clone https://github.com/chittaranjanbhat/test.git
vi test.txt
added line -- adding line for test

git status :
(use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   test.txt

cat test.txt 
testing the git revert
adding line for test

git restore test.txt / git restore .

cat test.txt        
testing the git revert

### Undoing committed changes
vi test.txt
git add test.txt
git commit -m 'burger changes'
git log
commit a571de0dbb4e068aefdb74ff8459fa0ff27809e2 (HEAD -> master)
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:25:57 2020 -0500

    burger changes

commit 8d3d31db30d8dc40bf6eb97fe56ed5a88497c118
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:23:23 2020 -0500

    pizza changes

commit da9e208109570afe28ccf95a0f9438b779f038f8 (origin/master, origin/HEAD)
Author: Bhat, Chittaranjan U. (CONT) <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:04:06 2020 -0500

    Create test.txt

commit ab43c7f80076e59bb9ca744afb55e8c005b6588e
Author: Bhat, Chittaranjan U. (CONT) <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:03:41 2020 -0500

    Initial commit
    
#### Undoing with commit changes
git revert a571de0dbb4e068aefdb74ff8459fa0ff27809e2
git log                                            
commit fed7be0033bc3deedf34b2b8c5362288115be89b (HEAD -> master)
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:27:22 2020 -0500

    Revert "burger changes"
    
    This reverts commit a571de0dbb4e068aefdb74ff8459fa0ff27809e2.

commit a571de0dbb4e068aefdb74ff8459fa0ff27809e2
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:25:57 2020 -0500

    burger changes

commit 8d3d31db30d8dc40bf6eb97fe56ed5a88497c118
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:23:23 2020 -0500

    pizza changes

commit da9e208109570afe28ccf95a0f9438b779f038f8 (origin/master, origin/HEAD)
Author: Bhat, Chittaranjan U. (CONT) <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:04:06 2020 -0500

    Create test.txt

commit ab43c7f80076e59bb9ca744afb55e8c005b6588e
Author: Bhat, Chittaranjan U. (CONT) <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:03:41 2020 -0500

    Initial commit

#### Undoing with commit changes without commiting
git revert -n 8d3d31db30d8dc40bf6eb97fe56ed5a88497c118
git status
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

You are currently reverting commit 8d3d31d.
  (all conflicts fixed: run "git revert --continue")
  (use "git revert --skip" to skip this patch)
  (use "git revert --abort" to cancel the revert operation)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
  
  --Review your change and commit explicitly
  
  ### Resetting the changes
git log               
commit 120f776475c79821e6ecca1e815c5f10564807b1 (HEAD -> master, origin/master, origin/HEAD)
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 16:46:32 2020 -0500

    changes update

commit fed7be0033bc3deedf34b2b8c5362288115be89b
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:27:22 2020 -0500

    Revert "burger changes"
    
    This reverts commit a571de0dbb4e068aefdb74ff8459fa0ff27809e2.

commit a571de0dbb4e068aefdb74ff8459fa0ff27809e2
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:25:57 2020 -0500

    burger changes

commit 8d3d31db30d8dc40bf6eb97fe56ed5a88497c118
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:23:23 2020 -0500

    pizza changes

commit da9e208109570afe28ccf95a0f9438b779f038f8
Author: Bhat, Chittaranjan U. (CONT) <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:04:06 2020 -0500

    Create test.txt

commit ab43c7f80076e59bb9ca744afb55e8c005b6588e
Author: Bhat, Chittaranjan U. (CONT) <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:03:41 2020 -0500

    Initial commit
    
 ## git reset --hard a571de0dbb4e068aefdb74ff8459fa0ff27809e2
git log     
commit a571de0dbb4e068aefdb74ff8459fa0ff27809e2 (HEAD -> master)
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:25:57 2020 -0500

    burger changes

commit 8d3d31db30d8dc40bf6eb97fe56ed5a88497c118
Author: Chittaranjan Bhat <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:23:23 2020 -0500

    pizza changes

commit da9e208109570afe28ccf95a0f9438b779f038f8
Author: Bhat, Chittaranjan U. (CONT) <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:04:06 2020 -0500

    Create test.txt

commit ab43c7f80076e59bb9ca744afb55e8c005b6588e
Author: Bhat, Chittaranjan U. (CONT) <chittaranjan.bhat@hotmail.com>
Date:   Tue Apr 7 12:03:41 2020 -0500

    Initial commit

## git push -f origin master

 
