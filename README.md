# Git (for real this time)

In labs up to this point, you've been using GitHub to record and commit your work. As you learned in lecture, GitHub is merely a hosting service (with some other nice features) for Git. In this lab, we'll be walking through the *real* git.

## Clone
As you've done before, everything Git related usually starts with a clone. Once you have created your copy of the Lab 4 repository (lab-4-<GitHub username>), run the command `git clone https://github.com/Purdue-CS193/lab-4-<GitHub username>`. As we know, all this command does is to download a copy of the *remote* repository to your *local* machine. 

Now if you run `ls`, you should see a directory called `lab-4-<GitHub username>`. `cd` into this directory and run `ls` again and you should see all the same files that GitHub shows in the browser for this repository. 

## Status
One of the most frequently used git commands is `git status`. Any time you are inside a git repository (i.e. your current directory or one of its parents is an initialized git repository), you can run `git status` to see what precisely what state your repository is in. 

Make sure you are in the lab 4 directory and try running `git status`. The output of this command tells you many things. 
The first line `On branch master` tells you that you are currently working from the `master` branch of the repository (more on branches later).
The second line `Your branch is up to date with 'origin/master'` tells you that your local repository (the files stored on your computer) are in the same state as the files stored remotely on the GitHub repository.
The third line `nothing to commit, working tree clean` tells you that you have not made any changes to the files in the repository at this point. 

### Task 1: Sync Local with Remote

