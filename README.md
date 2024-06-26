# *git-practice*

This repository contains a few practice assignments on git.<br/>
First, setup git and create a github account as explained in the slides.<br/>

Execute the following steps to practice various topics covered in the intro to git session<br/>

## Forking a repository

   Fork the repository using the fork icon.<br/> <br/>
   ![](images/fork.png)
    <hr>

## Cloning a forked repository

   Clone the forked repository into a directory of your choice in your local machine using the command `git clone <url_of_forked_repository>` <br/> <br/>
   ![](images/clone.png)
    <hr>

## Branching

   Create a branch with name myFirstBranch using the command `git branch myFirstBranch` <br/> <br/>
   ![](images/git_branch.png)
    <hr>

## Switching to a new branch

   Now switch to the new branch using the command `git checkout myFirstBranch` <br/> <br/>
   ![](images/git_checkout.png) <br/> <br/>
   As shown in the above image, the branch gets changed from main to `myFirstBranch` <br/>

### Note

   The above two steps can be performed at once by using the command `git checkout -b "myFirstBranch"`. This command creates a new branch with the name specified in the quotes and switches to that branch.
    <hr>

## Making changes

   Add a sentence of your choice to the `sample.txt` file (Ex : Hi I am <your_name>) and add a new text file named `new.txt`  
   This is how the cloned repository on your local machine should look after doing the above two changes <br/> <br/>
   ![](images/new_file.png) <br/> <br/>
   The newly added file `new.txt` and any changes made to it will not be tracked, i.e they are not present in git and git does not recognize any changes made to that file. Since `sample.txt` was already tracked when you cloned the repository from github, git will be aware of all the changes made to that file. <br/> <br/>
   But, the newly added sentence to `sample.txt` is unstaged, i.e it is not yet marked for commit. In order to stage it, we have to use the command `git add`
    <hr>

## Checking the difference

   Now, use the commands `git status` and `git diff` and see what happens <br/> <br/>
   ![](images/git_status.png) <br/> <br/>
   The above image says that the new sentence added to the file `sample.txt` is unstaged and the newly added file `new.txt` is untracked.<br/> <br/>
   ![](images/git_diff.png) <br/> <br/>
   When we perform `git diff`, it does not show `new.txt`. This is because `new.txt` is still untracked.
    <hr>

## Stashing your changes

   Now use the command `git stash` followed by `git status`. <br/> <br/>
   ![](images/git_stash.png) <br/> <br/>
   This command is used when we want to have a clean working directory but at the sametime save our changes. All the tracked work gets saved, but the untracked changes remain as it is and they wont be saved. <br/>
   Carefully observe the difference between the current and the previous output of `git status`.  
    Now use the command `git stash pop` <br/> <br/>
    ![](images/git_stash_pop.png) <br/> <br/>
    As we can see, all our changes are back.
    <hr>

## Stashing untracked changes

   Now use the command `git stash -u` followed by `git status`. <br/> <br/>
   ![](images/git_stash_u.png) <br/> <br/>
    This time it even stashes the untracked file.
    Now again, use the command `git stash pop`. You will be able to see both the tracked and untracked changes.
    <hr>

## Staging the changes

   Use the command `git add --all` to stage all the changes <br/> <br/>
   ![](images/git_add.png) <br/> <br/>
  Again use the commands `git status` and `git diff` and see what happens <br/> <br/>
   ![](images/git_status_2.png)
   ![](images/git_diff_2.png) <br/> <br/>
   Since all our changes have been staged, `git diff` does not show anything.
    <hr>

## Committing changes

   Now, commit the changes using `git commit -m "my first commit"` <br/> <br/>
   ![](images/git_commit.png)
    <hr>

## Merging branches

   Switch to the main branch by using the command `git checkout main` <br/> <br/>
   ![](images/git_checkout_2.png) <br/> <br/>
   As shown in the above image, the branch changes from `myFirstBranch` to main <br/>
   Now merge the other branch with main branch using `git merge myFirstBranch` <br/> <br/>
   ![](images/git_merge.png)
    <hr>

## Tracking upstream repository

   Use the command `git remote -v` to see all the tracked github repositories <br/> <br/>
   ![](images/git_remote.png) <br/> <br/>
   As shown in the image, it only tracks the forked repository <br/>
   Use the command `git remote add upstream <url_of_upstream_repo>` to track the upstream repo as well. Then again use the command `git remote -v` to check if the upstream is being tracked.<br/> <br/>
   ![](images/git_upstream.png)
    <hr>

## Pushing changes

   Now push all the changes onto your forked github repository using `git push origin main`
   ![](images/git_push.png) <br/> <br/>

Open your forked github repository and check whether all the changes have been updated. <br/>

## Log

`git log` is used to display the commit history of the repository. Try using this command and you will be able to see the commit history of the repository.

```bash
git log
```

However, the output of the above command may be too verbose. You can use the following command to see a more concise output.

```bash
git log --all --decorate --oneline --graph
```

In the current state, you should see a commit history that looks like this:

![Commit Log](/content/images/log_mid.png)

Of course, the commit hashes and messages might be different in your case.

Feel free to use the above command to visualize the commits that you are making.

## Rebase

`git rebase` is used to reapply commits on top of another base tip. This is useful to maintain a linear project history.

Do the following steps for a rebase:

1) Create a new branch called `mySecondBranch` (try to recall how to create a new branch). And don't forget to switch to the new branch.
2) Add a new text file called `new2.txt` and add some text to it. Add and commit these changes.
3) Similarly, add a new text file called `new3.txt` and add some text to it. Add and commit these changes.
4) Now, switch back to the `main` branch and add another text file called `new4.txt` and add some text to it. Add and commit these changes.

   If you have followed the steps correctly, you should have a commit history that looks like this:

    ![Commit Log 1](/content/images/log_rebase_1.png)

    You can verify this by using the `git log` command.
5) Now, rebase `mySecondBranch` onto `main` using the following commands:

    ```bash
    git checkout mySecondBranch
    git rebase main
    ```

6) Verify that your commit history now looks like this:

    ![Commit Log 2](/content/images/log_rebase_2.png)

    You can use the `git log` command to verify this.

    Notice that the commit history is now linear, and the commits from `mySecondBranch` have been reapplied on top of the `main` branch. However, the commit hashes will be different before and after the rebase.

### Rebase vs Merge

In cases where we want to combine the changes from one branch to another, we can use either `rebase` or `merge`.

| Merge                                                            | Rebase                                                         |
| ---------------------------------------------------------------- | -------------------------------------------------------------- |
| Creates a new commit that combines the changes from two branches | Reapplies the commits from one branch on top of another branch |
| Creates a non-linear commit history                              | Creates a linear commit history                                |
| Preserves the commit history of both branches                    | Rewrites the commit history of the branch being rebased        |

Consider this example:

![Current State](/content/images/cur_state.png)

You have two branches, `main` and `branch1`. You have made some changes in `branch1` and want to combine these changes with the `main` branch.

If we merge `branch1` with `main` using the following commands:

```bash
git checkout main
git merge branch1
```

The commit history will look like this:

![Merge State](/content/images/merge_state.png)

Notice that the commit history is non-linear, and the changes from `branch1` have been combined with the `main` branch by creating a **new** commit. This is a three-way merge.

Instead, if we had rebased `branch1` onto `main` using the following commands:

```bash
git checkout branch1
git rebase main
```

The commit history would have looked like this:

![Rebase State](/content/images/rebase_state.png)

Notice that the commit history is linear, and the changes from `branch1` have been reapplied on top of the `main` branch. In order to get `main` up to date with the changes in `branch1`, we can now merge `branch1` with `main`.

```bash
git checkout main
git merge branch1
```

**Remember:** Now, it would be a fast-forward merge and the linear commit history would be maintained.

![Rebase->Merge State](/content/images/rebase->merge_state.png)

## Cherry-pick

`git cherry-pick` is used to apply the changes introduced by some existing commits. It is useful when you want to apply a one or more commits from one branch to another.

At this point, if you are on `main`, you will **not** have the `new2.txt` and `new3.txt` files.

If you switch to `mySecondBranch`, you will have the `new2.txt` and `new3.txt` files as well as the `new4.txt` file.

Now, consider the following scenario:

You want the `new3.txt` file to be added to the `main` branch, but you do not want the `new2.txt` file to be added.

To achieve this, you can use the `git cherry-pick` command.

1) Use `git log` to find the commit hash of the commit where you added `new3.txt`.

    In the example below, the commit hash is `a96bd72`.

    ![Commit Log 2](/content/images/log_rebase_2.png)

    Note: The commit hash will be different in your case.

2) Make sure you are on the `main` branch and use the following command to cherry-pick the commit:

    ```bash
    git cherry-pick <<commit_hash>>
    ```

3) Verify that the changes have been applied to the `main` branch by using the `git log` command. You can also verify this by checking that you now have the `new3.txt` file in the `main` branch, but not the `new2.txt` file.

    ![Commit Log 3](/content/images/log_cherrypick_1.png)

## Interactive Rebase

`git rebase -i` is used to interactively rebase commits. This is useful when you want to modify, delete, or combine commits.

Consider the following scenario:

1) Switch to `mySecondBranch`. Add a new text file called `new5.txt` and add some text to it. Add and commit these changes.
2) Edit the `new2.txt` file and add some more text to it. Add and commit these changes.
3) Now, you should have the following commit history:

    ![Commit Log 4](/content/images/log_irebase.png)

4) You want to rebase `mySecondBranch` onto `main`, but you have already cherry-picked the commit that added `new3.txt` to the `main` branch.

    Now, you want the `new2.txt` file in your main branch, but it has two commits associated with it. You want to combine these two commits into a single commit. Moreover, you do not want the `new5.txt` file anymore.

    Checkout to `mySecondBranch`:

    At this point, if you wanted to modify the commit history of `mySecondBranch`, you can use: `git rebase -i HEAD~4`. Notice that `HEAD` refers to the current commit (the latest commit on `mySecondBranch`), and `HEAD~4` refers to the commit which is four commits **before** the current commit (in this case, the first commit on `mySecondBranch`). This command will not rebase onto `main`, but rather onto the commit denoted by `HEAD~4`. In this case, it will rebase onto itself, effectively allowing you to modify the commit history of `mySecondBranch` by interacting with the last 4 commits on `mySecondBranch`. Note that you need to be careful to not rebase with a number greater than 4 if you have committed for a maximum of 4 times in the current branch, else the commits in `main` before this branch will also be pulled in and will clutter the commit history.

    But for now, since you actually want to rebase onto `main`, you can use the following command:

    ```bash
    git rebase -i main
    ```

    You could also use a combination of `git rebase -i HEAD~4` followed by `git rebase main` to achieve the same result. But for now, let's stick to the above command.

    A new file will open and you will see that it has a list of commits that are being rebased. You can modify this list to combine, delete, or edit commits.

    In your case, you might see something like this:

    ![Interactive 1](/content/images/interactive1.png)

    **Note:** `git` doesn't show the commit that `added new3.txt`. This is because you have already cherry-picked this commit onto the `main` branch. `git` is smart enough to know that this commit is already present in the `main` branch and does not need to be rebased. If we had used `git rebase -i HEAD~4`, this commit would have been included in the list.

5) You need to edit this file to combine the two commits that added `new2.txt`. To do this, change the word `pick` to `drop` corresponding to the commit that `added new5.txt` and change the word `pick` to `squash` for the commit that `modified new2.txt`.

    In case you are in the `vi` or `vim` editor, and you do not know how to use it, you can press `i` to enter insert mode, make the necessary changes, press `Esc` to exit insert mode, and then type `:wq` to save and exit.

    After editing, the file should look like this:

    ![Interactive 2](/content/images/interactive2.png)

6) Save and close the file. You will be prompted to enter a new commit message for the combined commit.

    ![Interactive 3](/content/images/interactive3.png)

    Edit the commit message and save and close the file.

    ![Interactive 4](/content/images/interactive4.png)

    The rebase should now be complete, and you should have the following commit history:

    ![Commit Log Final](/content/images/log_final.png)

    Notice that the `new5.txt` file is no longer present, and the two commits that modified `new2.txt` have been combined into a single commit.

7) Finally, now that `mySecondBranch` is ready, you can merge it with the `main` branch. As you have already done a fast-forward merge, you can now try doing a three-way merge.

    Switch to the `main` branch and use the following command to merge `mySecondBranch` with `main`:

    ```bash
    git merge mySecondBranch --no-ff
    ```

    Git will open an editor to enter a commit message. You can use the default message by saving and closing the file.

    You should now have the following commit history:

    ![Commit Log Post](/content/images/log_post.png)

Now that you have completed all the steps, you can push the changes to your forked repository using the `git push origin main` command

---

Open your forked github repository and check whether all the changes have been updated.
<hr>
