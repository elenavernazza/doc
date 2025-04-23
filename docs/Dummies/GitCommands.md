# Git commands I will forget

| Command                                   | Usage                                                                                         |
|-------------------------------------------|-----------------------------------------------------------------------------------------------|
| `git log --graph`                         | Text-based representation og branches                                                         |
| `git log HEAD~2..HEAD`                    | Show only the last two commits                                                                |
| `git log origin..HEAD`                    | Show what is in HEAD, but not yet pushed to origin                                            |
| `git log -S string`                       | Shows all commits where a string was added or removed                                         |
| `git log -L 10,20:file`                   | Shows evolution of lines 10 to 20 of file                                                     |
| `git log -L:myFunction:file`              | Shows evolution of function inside file                                                       |
| `git blame filename`                      | Tell author and date of last changes in file                                                  |
| `git remote show origin`                  | Checks differences with respect to the `origin` (is my folder up to date? )                   |
| `git fetch orgin main`                    | Updates the remote `origin` in branch `main` but does not change the local files (`HEAD`)     |
| `git merge origin/main`                   | Appends the commits in `origin/main` to the last commit in your `HEAD`                        |
| `git pull origin main`                    | Sum of `git fetch` then `git merge`                                                           |
| `git rebase origin/main HEAD`             | Appends the commits in `origin/main` to the last commit in your `HEAD`                        |
| `git pull --rebase origin main`           | Sum of `git fetch` then `git rebase`                                                          |
| `git fetch --dry-run`                     | Does not update the remote                                                                    |
| `git cherry-pick <commit>`                | Applies changes from a specific commit                                                        |

| Command                                   | Usage                                                                                         |
|-------------------------------------------|-----------------------------------------------------------------------------------------------|
| `git stash push`                          | Sends the current changes and commits to a stash repository (frozen)                          |
| `git stash list`                          | Lists all stases                                                                              |
| `git stash apply`                         | Like pop, but doesn't remove the item from the stash                                          |
| `git stash drop`                          | Removes from the stash without applying to working area                                       |
| `git stash pop`                           | Gets the current changes to a stash repository (`apply` and `pop` together)                   |
| `git stash --keep-index`                  | Save changes to stash without removing them from the staging area                             |
| `git stash --include-untracked`           | Add to stash everything in the working area                                                   |
| `git stash branch name`                   | Creates new branch starting from stashed changes                                              |
| `git stash -p`                            | Interactive stashing step by step                                                             |

| Command                                   | Usage                                                                                         |
|-------------------------------------------|-----------------------------------------------------------------------------------------------|
| `git checkout <file_name>`                | Discards changes and restore the file state to index                                          |
| `git checkout <branch_name>`              | Sets HEAD to point to different branch                                                        |
| `git checkout <branch_name> -- <file_name>`       | Discards changes and restores the file state to the one in that branch                |
| `git checkout <commit>`                   | Sets HEAD to point to that commit, if it's not the last commit it enters detatched mode       |
| `git restore <file_name>`                 | Discards changes and restores the file state to index (similar to `checkout`)                 |
| `git restore <file_name> -- source <branch_name>` | Discards changes and restores the file state to the one in that branch                |
| `git switch <branch_name>`                | Changes the branch (similar to `checkout`)                                                    |
| `git switch -c <branch_name>`             | Crates a new branch and chenages to that (similar to `checkout`)                              |

## Testing git fetch from remote
1. I've changed the README.md locally (HEAD) - commit 'Test git rebase 1'
2. I've changed the README.md in the remote (origin/main) - commit 'Test git rebase 2'
3. `git fetch` takes the new commit from the remote
4. `git rebase --interactive origin/main` puts the commit of the origin on top of my HEAD history
5. Resolve conflict in the file `README.md`
6. `git add README.md`
7. `git rebase --continue`
8. I lost the 'Test git rebase 1' commit, probably because there were conflicts?

## Testing git fetch from branch
1. I've changed the README.md in the branch (dev) - commit 'Test git rebase 1'
2. Someone changed the README.md in the main (main) - commit 'Test git rebase 2'
3. `git rebase main` puts the commit of my HEAD history on top of the origin history
4. `git switch main` move to the main branch
5. `git merge dev` merges the corrected history of dev into main. Do rebase before merge!
6. You cannot push to remote in dev: use `push --force`, better to use `push --force-with-lease` (pushes only if the remote hasn't changed)

## Fixing a mistake

| Staged changes                            | Usage                                                                                         |
|-------------------------------------------|-----------------------------------------------------------------------------------------------|
| `git restore -s <commit> <file_name>`     | Discards changes and restores the file state to commit                                        |

| Committed changes                         | Usage                                                                                         |
|-------------------------------------------|-----------------------------------------------------------------------------------------------|
| `git revert <commit>`                     | Safe undo of the commit, the commit remains in the history and is not dangling                |
| `git commit --amend`                      | If you missed something in the commit and you are adding small changes                        |
| `git commit --amend --no-edit`            | It doesn't change the commit description                                                      |
| `git reset --soft HEAD~`                  | Undo the commit, update the repository to HEAD~ (first parent of HEAD). Same working area, same staging area.    |
| `git reset --mixed HEAD~`                 | Undo the commit, update the repository to HEAD~ (first parent of HEAD), and the staging area. Same working area. |
| `git reset --hard HEAD~`                  | Undo the commit, update the repository to HEAD~ (first parent of HEAD), the staging area, and the working area.  |
| `git filter-repo --invert-path --path <filename>` | Remove large pdfs form the repository forever (CAREFUL!)                              |

The old commit is dangling, but we can go back

| Committed changes                         | Usage                                                                                         |
|-------------------------------------------|-----------------------------------------------------------------------------------------------|
| `git reflog`                              | Shows the history                                                                             |

Git creates checkpoints to the past history: `HEAD@{2}`, `HEAD@{yesterday}`, `HEAD@{2.months.ago}`

### If I want to change multiple previous commits

1. `git rebase -i <commit>` (it can be `HEAD~3` for the three previous commits)
2. Edit the file and remove the commits you don't want to pick
3. `git rebase --continue` or `git rebase --abort` or `git rebase --edit-todo`