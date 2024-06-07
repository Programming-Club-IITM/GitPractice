# git-practice

This repository contains a few practice assignments on git.<br/>
First, setup git and create a github account as explained in the slides.<br/>

Execute the following steps to practice various topics covered in the intro to git session<br/>
1) Fork the repository using the fork icon.<br/>
   ![](images/fork.png)
2) Clone the forked repository into a directory of your choice in your local machine using the command git clone <url_of_forked_repository> <br/>
   ![](images/clone.png)
3) Create a branch with name myFirstBranch using the command git branch <br/>
   ![](images/git_branch.png)
4) Now switch to the new branch using the command git checkout myFirstBranch<br/>
   ![](images/git_checkout.png) <br/>
   As shown in the above image, the branch gets changed from main to my first branch <br/>
5) Add a sentence of your choice to the sample.txt file. (Ex : Hi I am <your_name>) <br/>
6) Add a new text file named new.txt <br/>
   This is how the cloned repository on your local machine should look after doing the above two changes <br/>
   ![](images/new_file.png)
7) Now, use the commands git status and git diff and see what happens <br/>
   ![](images/git_status.png)
   ![](images/git_diff.png) <br/>
   When we perform git diff, it does not show new.txt. This is because new.txt is still untracked. <br/>
8) Use the command git add --all to stage all the changes <br/>
   ![](images/git_add.png)
9) Again use the commands git status and git diff and see what happens <br/>
   ![](images/git_status_2.png)
   ![](images/git_diff_2.png) <br/>
   Since all our changes have been staged, git diff does not show anything <br/>
10) Now, commit the changes using git commit -m "my first commit" <br/>
   ![](images/git_commit.png)
11) Switch to the main branch by using the command git checkout main <br/>
   ![](images/git_checkout_2.png) <br/>
   As shown in the above image, the branch changes from myFirstBranch to main <br/>
12) Now merge the other branch with main branch using git merge myFirstBranch <br/>
   ![](images/git_merge.png)
13) Now push all the changes onto your forked github repository using git push origin main <br/>
   ![](images/git_push.png)
 
 Open your forked github repository and check whether all the changes have been updated. <br/>
