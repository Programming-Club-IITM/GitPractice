# git-practice

This repository contains a few practice assignments on git.<br/>
First, setup git and create a github account as explained in the slides.<br/>

Execute the following steps to practice various topics covered in the intro to git session<br/>
# 1) Forking a repository 
   Fork the repository using the fork icon.<br/> <br/>
   ![](images/fork.png)
    <hr>
# 2) Cloning a forked repository 
   Clone the forked repository into a directory of your choice in your local machine using the command `git clone <url_of_forked_repository>` <br/> <br/>
   ![](images/clone.png)
    <hr>
# 3) Branching
   Create a branch with name myFirstBranch using the command `git branch myFirstBranch` <br/> <br/>
   ![](images/git_branch.png)
    <hr>
# 4) Switching to a new branch
   Now switch to the new branch using the command `git checkout myFirstBranch` <br/> <br/>
   ![](images/git_checkout.png) <br/> <br/>
   As shown in the above image, the branch gets changed from main to my first branch <br/>
    <hr>
   # Note : 
   The above two steps can be performed at once by using the command `git checkout -b "myFirstBranch"`. This command creates a new branch with the name specified in the quotes and switches to that branch.
    <hr>
# 5) Making changes
   Add a sentence of your choice to the sample.txt file. (Ex : Hi I am <your_name>) <br/>
   Add a new text file named new.txt <br/>
   This is how the cloned repository on your local machine should look after doing the above two changes <br/> <br/>
   ![](images/new_file.png)
    <hr>
# 6) Checking the difference 
   Now, use the commands `git status` and `git diff` and see what happens <br/> <br/>
   ![](images/git_status.png) <br/> <br/>
   The above image says that the new sentence added to the file sample.txt is unstaged. It means that those changes are in git but they are not marked for commit. <br/>
   But, the newly added file new.txt is untracked. This means that this file is not in git and any changes made to it won't be recognized by git <br/>
   ![](images/git_diff.png) <br/> <br/>
   When we perform `git diff`, it does not show new.txt. This is because new.txt is still untracked.
    <hr>
# 7) Stashing your changes
   Now use the command `git stash` followed by `git status`. <br/> <br/>
   ![](images/git_stash.png) <br/> <br/>
   This command is used when we want to have a clean working directory but at the sametime save our changes. All the tracked work gets saved, but the untracked changes remain as it is and they wont be saved. <br/>
   Carefully observe the difference between the current and the previous output of `git status`.  
    Now use the command `git stash pop` <br/> <br/>
    ![](images/git_stash_pop.png) <br/> <br/>
    As we can see, all our changes are back.
    <hr>
# 8) Stashing untracked changes
   Now use the command `git stash -u` followed by `git status`. <br/> <br/>
   ![](images/git_stash_u.png) <br/> <br/>
    This time it even stashes the untracked file.
    Now again, use the command `git stash pop`. You will be able to see both the tracked and untracked changes.
    <hr>
# 9) Staging the changes
   Use the command `git add --all` to stage all the changes <br/> <br/>
   ![](images/git_add.png)
  Again use the commands `git status` and `git diff` and see what happens <br/> <br/>
   ![](images/git_status_2.png)
   ![](images/git_diff_2.png) <br/> <br/>
   Since all our changes have been staged, `git diff` does not show anything.
    <hr>
# 10) Committing changes
   Now, commit the changes using `git commit -m "my first commit"` <br/> <br/>
   ![](images/git_commit.png)
     <hr>
# 11) Merging branches
   Switch to the main branch by using the command `git checkout main` <br/> <br/>
   ![](images/git_checkout_2.png) <br/> <br/>
   As shown in the above image, the branch changes from myFirstBranch to main <br/>
   Now merge the other branch with main branch using `git merge myFirstBranch` <br/> <br/>
   ![](images/git_merge.png) <br/> <br/>
      <hr>
# 12) Tracking upstream repository
   Use the command `git remote -v` to see all the tracked github repositories <br/> <br/>
   ![](images/git_remote.png) <br/> <br/>
   As shown in the image, it only tracks the forked repository <br/>
   Use the command `git remote add upstream <url_of_upstream_repo>` to track the upstream repo as well. Then again use the command `git remote -v` to check if the upstream is being tracked.<br/> <br/>
   ![](images/git_upstream.png)
     <hr>
# 13) Pushing changes
   Now push all the changes onto your forked github repository using `git push origin main`
   ![](images/git_push.png) <br/> <br/>
 
 Open your forked github repository and check whether all the changes have been updated.
 <hr>
