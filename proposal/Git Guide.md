# Basic Git Workflow for Team Noname


## Before making any changes
1. `ls -a` To make sure you're sure in the correct directory. (ls -a from terminal should show .git)
2. `git branch` to make sure you're in the dev branch 
3. `git pull` _before_ making any changes to reduce merge conflicts.
4. Create a new branch off of dev using the category for the type of changes you're making followed by a "/" then a descriptive name.
- examples: 
  - `git checkout -b feature/login-form`
  - `git checkout -b bug-fix/typing-bug`

## While coding
1. Commit frequently with descriptive, concise messages. If you get into a messy situation and want to rollback to a previous commit:
   1. Rollback and nuke the bad code in the process:
      1. `git log` then copy the SHA-hash (a long string of numbers) of the last working commit, then run `git reset --HARD <SHA-hash>`
   2. Create a new branch off of the last working commit (you may want to look at the bad stuff later to figure something out):
      1. `git checkout -b <new-branch-name> <SHA-hash>` 
## After changes
1. After you're finished and sure everything is working, merge back into dev by first checking out to dev with `checkout dev` then running `merge --no-ff <name of working branch>` 
2. Push to origin with `git push`
3. If the change is ready for the world to see on the main branch, make a pull request on Github for teammates to review the change. 

Note: this is a modified version of "Gitflow" with an additional protective layer in the form of a dev branch. 