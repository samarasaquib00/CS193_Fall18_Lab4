# Git (for real this time)

In labs up to this point, you've been using GitHub to record and commit your work. As you learned in lecture, GitHub is merely a hosting service (with some other nice features) for Git. In this lab, we'll be walking through the *real* git.

## Clone
As you've done before, everything Git related usually starts with a clone. Once you have created your copy of the Lab 4 repository (`lab-4-<GitHub username>`), run the command `git clone https://github.com/Purdue-CS193/lab-4-<GitHub username>.git`. As we know, all this command does is to download a copy of the *remote* repository to your *local* machine. 

Now if you run `ls`, you should see a directory called `lab-4-<GitHub username>`. `cd` into this directory and run `ls` again and you should see all the same files that GitHub shows in the browser for this repository. 

## Status
One of the most frequently used git commands is `git status`. Any time you are inside a git repository (i.e. your current directory or one of its parents is an initialized git repository), you can run `git status` to see precisely what state your repository is in. 

Make sure you are in the lab 4 directory and try running `git status`. The output of this command tells you many things. 

The first line `On branch master` tells you that you are currently working from the `master` branch of the repository (more on branches later).

The second line `Your branch is up to date with 'origin/master'` tells you that your local repository (the files stored on your computer) are in the same state as the files stored remotely on the GitHub repository.

The third line `nothing to commit, working tree clean` tells you that you have not made any changes to the files in the repository at this point. 

## Task 1: Sync Local with Remote

It is important to understand how useful git and GitHub can be for collaboration. For a moment, let's pretend that you and someone else are both working on solving Lab 4 together. We will simulate someone else pushing changes to Lab 4 while you are working on it locally. To do this, make sure you have already cloned the Lab 4 repo onto your local machine. Next, in your web browser, navigate to your Lab 4 repository in GitHub. 

TODO 1 : Open the `answers.txt` file and under `Part 1`, write a message to yourself. This can be anything you want. Go ahead and commit this message to the `master` branch. Again, make sure this change is made from GitHub in your web browser!! 

Now, locally in your terminal, run `git status` again in the Lab 4 directory. Notice the output this time! Wait.... it's still the same. Why does `git status` tell us  `Your branch is up to date with 'origin/master'` if we just made a change to the `master` branch in GitHub?

Even though we made a change to a file in the remote server (GitHub), we need to tell git that it needs to `fetch` new information from the remote server before it will know that we made a change. Run `git fetch` in the Lab 4 directory and then `git status` again. This time notice how git tells you  `Your branch is behind 'origin/master' by 1 commit, and can be fast-forwarded.
(use "git pull" to update your local branch)` This means that there is one commit (the message you wrote to yourself) on the branch `origin/master` that is not in your current branch. Let's get this commit into your current branch! Just like git tells you, run `git pull` to `pull` the new changes from the remote branch into your local branch. If you run `git status`, you should see that everything is up to date again (also look at `answers.txt` and see that your message is now there!).

TODO 2 : Open `answers.txt` on your local computer (NOT FROM GITHUB) with a text editor and fill out the remaining question for Task 1

## Task 2: Make a Commit

Now that we've made a change to `answers.txt` we need to actually commit this change. Run `git status` in the Lab 4 directory. Notice how git lists the `Changes not staged for commit`. As expected, `answers.txt` is listed as a file that we have changed. To `commit` the change, we need to first `stage` `answers.txt` so it is read to be committed.To do this, run `git add answers.txt` and then run `git status` again. git now tells us that `Changes to be committed:` includes `answers.txt`. Perfect! We are now ready to make our commit. Run `git commit` and in the text editor that pops up, write a detailed commit message such as "Added description for 'git fetch' in answers.txt". After you save your commit message and exit the text editor, your commit is complete! Now if we go back to GitHub, we should see this change right???? WRONG! Remember from Task 1 that syncing your local git repository with the remote server (GitHub) is not automatic! To `push` your local changes to the remote server, run `git push`. Now check the GitHub Lab 4 repository again. BAM! There are your fancy new changes. 

TODO 3 : Open `answers.txt` on your local computer (NOT FROM GITHUB) with a text editor and answer the question for Task 2, then repeat the steps we just did to commit this change and push it to GitHub.







