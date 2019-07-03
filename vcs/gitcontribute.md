# Beginners guide to contributing to a Github project #

The following is a guide to help you begin contributing to the IoT Mars Rover project.

TL:DR - skip to the summary

**Step 1**. Set up a working copy on your computer

Firstly you need a local fork of the the project, so go ahead and press the “fork” button (top right corner) in Jamie's GitHub repo **(https://github.com/jricho/marsroverv1.0)**. This will create a copy of the repository in your own GitHub account and you’ll see a note that it’s been forked underneath the project name. This location will typically be called Origin by git.

Clone your fork locally - This creates a copy of your GitHub repository (above) on your local machine. This is where you will do your development and testing and make pull requests back to the Upstream repository. Find the “Clone or download” green button in the right hand column and use that to clone locally using HTTPS in a terminal (make sure you in the working directory you wish to use on your laptop).

$ git clone https://github.com/*yourusername*/marsroverv1.0.git

Change into the new project's directory:

$ cd marsroverv1.0

Finally, in this stage, you need to set up a new remote that points to the original project (me) so that you can grab any changes and bring them into your local copy. Firstly click on the link to the original repository – it’s labeled “Forked from” at the top of the GitHub page. This takes you back to the projects main GitHub page, so you can find the “HTTPS clone URL” and use it to create the new remote, which we’ll call upstream.

$ git remote add *upstream* https://github.com/jricho/marsroverv1.0.git

$ git remote -v (*to check setup*)

You should now have two remotes for this project on disk:

1. **origin** which points to your GitHub fork of the project. You can read and write to this remote.
2. **upstream** which points to my GitHub repository. You can only read from this remote.

Now, you could try pushing changes to the original repository using *git push* at this point, but it will probably fail because you don’t have permission to push changes directly to the repository. Besides, it **really wouldn’t be a good idea**. That’s because other people might be working on the project as well, and how in the world would we keep track of everyone’s changes? That’s where branches come in.

**Step 2**. Do some work - Branch!

**The number one rule is to put each piece of work on its own branch**. The project only has a master branch, so we will branch from that.

For this example, we’ll be adding documentation, so we branch from master:

*Firstly we ensure we’re on the master branch.*

$ git checkout master

*Then the git pull command will sync our local copy with the upstream project and the git push syncs it to our forked GitHub project.*

$ git pull upstream master && git push origin master

*Finally we create our new branch. You can name your branch whatever you like (but we should agree on a naming standard).* This branch should be created whilst in the subdirectory that you wish your file to exist in the upstream project.

$ git checkout -b *yourname*

Create a file

$ touch *yourname.md*

Check for changes

$ git status

Add file to staging area

$ git add *yourname.md*

Commit your changes

$ git commit -m "*write a commit message that means something*"

Push the changes you made in the branch to origin

$ git push origin *yourname*

**Step 3 - Opening a Pull Request**

GitHub makes this part incredibly easy. Once you push a new branch up to your repository, GitHub will prompt you to create a pull request. The maintainers of the original project (me) can use this pull request to pull your changes across to their repository and, if they approve of the changes, merge them into the main repository.

**Step 4 - Cleaning up after a Merged Pull Request**

If the maintainer accepts your changes and merges them into the main repository, then there is a little bit of clean-up for you to do. First, you should update your local clone by using;

$ git pull upstream master

This pulls the changes from the original repository's (indicated by *upstream*) master branchto your local cloned repository.

You can then delete the branch (remembering short lived branch strategy)

$ git branch -d *yourname*

Then update the master branch in your forked repo

$ git push origin master

And push the deletion of the branch to your GitHub repo

$ git push --delete origin *yourname*

And that’s it! You’ve just successfully created a feature branch, made some changes, committed those changes to your repository, pushed them to GitHub, opened a pull request, had your changes merged by the maintainers, and then cleaned up.

##Step 5 - Keeping your Fork in Sync##

By the way, your forked repository doesn’t automatically stay in sync with the original repository; you need to take care of this yourself. After all in a healthy open source project, multiple contributors are forking the repository, cloning it, creating feature branches, committing changes, and submitting pull requests.

To keep your fork in sync with the original repository, use these commands:

$ git pull upstream master

$ git push origin master

This pulls the changes from the original repository (the one pointed to by the upstream Git remote) and pushes them to your forked repository (the one pointed to by the origin remote). (Hopefully that makes a little bit of sense to you by now.)

## Summary ##

If you are already familiar with Github and workflow, just follow this summary

1. Fork the project & clone locally.
2. Create an upstream remote and sync your local copy before you branch.
3. Branch for each separate piece of work.
4. Do the work, write good commit messages.
5. Push to your origin repository.
6. Create a new PR (pull request) in GitHub.
7. Respond to any code review feedback.