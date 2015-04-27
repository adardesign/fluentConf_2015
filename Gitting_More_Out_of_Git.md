# Gitting More Out of Git
#### Monday April 20th 1:45pm Gitting More Out of Git
######  Jordan Kasper (StrongLoop)
[Slides](http://cdn.oreillystatic.com/en/assets/1/event/125/Gitting%20More%20Out%20of%20Git%20Presentation.pdf)




## Methods
- Diff'ing branches:  `git diff master branch`  
- Seeing only diffs from diverging branch `git diff master..stuff` 
- Explains How git works internally (via delta snapshots) 
- `git --amend`
- git **almost** never deletes (see `git reflog`)
- use `git rebase ‐‐interactive` to rewrite history  can be used on `HEAD` and each `^` is one up in the log `git rebase ‐‐interactive  HEAD^^^` will bring the screen to interactively allow to edit 3 entries in the git log
- `git reflog` always stays local
- `git stash` 
- git stash the difference between `apply` and `pop` 
- `git stash` can be named
## Undoing changes:
- `git reset ‐‐soft HEAD^` leaves the changes in the index but removes from the staged  
- `git reset ‐‐mixed HEAD^` Resets the index but not the working tree (i.e., the changed files are preserved but not marked for commit) and reports what has not been updated. This is the default action.
- `git reset ‐‐hard HEAD^` Resets the index and working tree. Any changes to tracked files in the working tree since <commit> are discarded.
- `git blame` (should be used to give compliments too :))
- rebase only when safe to do so


## HEAD notations
- `HEAD^` (back one place from current HEAD)
- `HEAD^^` (back two places from current HEAD)
- `HEAD~n` (back 'n' places from current HEAD)
- `HEAD@{i}` (back to reflog index 'i')
