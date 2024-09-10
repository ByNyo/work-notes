git commit 

git commit <file/folder> -m <comment> 

git commit –a -m <comment> // Commits all 

Commits a change of a specific file or folder to the local repo. 

git pull 

git pull <remote> 

git pull –rebase <remote> 

Pulls/gets the current remote repo and copies it to the local repo as well as copying it to your designated folder. 

git push 

git push 

git push <remote> <branch> 

git push --set-upstream <remote> <branch> 

Pushes the local repo into the remote repo. 

git checkout 

git checkout <branch> // Switches branch 

git checkout –b <branch> // Creates new branch 

git checkout –b <new-branch>  <existing-branch> // Creates new branch and copies existing over the new one. 

git stash 

git stash // Saves uncommited changes for later use 

git stash pop // Removes changes from stash and applies them to working copy 

git stash apply // Apply changes to working copy and keeps stash for different use (e.g. multiple branches where you want to use the stash) 

Git stash –u // Stash untracked files (a file that was never commited to git aka. local repo) 

git rebase 

git rebase // Moves or combines a sequence of commits to a new base 

git branch <new-branch> // Makes a new branch 

git branch –d <branch> // Deletes the specified branch 

git branch –D <branch> // Deletes(Forced) the specified branch 

git branch –m <branch> // Renames branch to specified name 

git branch // Lists all branches of your repository 

git branch -a // Lists all remote branches 

git switch <branch> // Switches active branch to the specified one 

git remote 

git remote add <new-remote> <githublink+.git> // Adds a remote repository 

git remote set-url <remote> https://username:token@github.com/username/repository.git