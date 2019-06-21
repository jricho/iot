# Beginners guide to contributing to a Github project #

The following is a guide to help you begin contributing to the IoT Mars Rover project.

TL;DR - skip to the summary

**Step 1**. Set up a working copy on your computer

Firstly you need a local fork of the the project, so go ahead and press the “fork” button in GitHub. This will create a copy of the repository in your own GitHub account and you’ll see a note that it’s been forked underneath the project name. This location will typically be called Origin by git.

Clone your fork locally - This creates a copy of your GitHub repository (above) on your local machine. This is where you will do your development and testing and make pull requests back to the Upstream repository. Find the “Clone or download” green button in the right hand column and use that to clone locally using SSH in a terminal (make sure you in the working directory you wish to use).

$ git clone git@github.com:*yourusername*/iot.git

**Note:** SSH URLs provide access to a Git repository via SSH, a secure protocol. To use these URLs, you must generate an SSH keypair on your computer and add the public key to your GitHub account. For information on setting up an SSH keypair, see [Generating an SSH key](https://help.github.com/en/articles/generating-an-ssh-key)

Change into the new project's directory:

$ cd marsroverv1.0

Finally, in this stage, you need to set up a new remote that points to the original project (me) so that you can grab any changes and bring them into your local copy. Firstly clock on the link to the original repository – it’s labeled “Forked from” at the top of the GitHub page. This takes you back to the projects main GitHub page, so you can find the “SSH clone URL” and use it to create the new remote, which we’ll call upstream.

$ git remote add upstream git@github.com:jricho/marsroverv1.0.git

$ git remote -v (*to check setup*)

You should now have two remotes for this project on disk:

1. origin which points to your GitHub fork of the project. You can read and write to this remote.
2. upstream which points to the main project’s GitHub repository. You can only read from this remote.

**Step 2**. Do some work - Branch!

**The number one rule is to put each piece of work on its own branch**. The project only has a master branch, so we will branch from that.

For this example, we’ll be adding documentation, so we branch from master:

$ git checkout master
$ git pull upstream master && git push origin master
$ git checkout -b hotfix/readme-update

Firstly we ensure we’re on the master branch. Then the git pull command will sync our local copy with the upstream project and the git push syncs it to our forked GitHub project. Finally we create our new branch. You can name your branch whatever you like, but it helps for it to be meaningful.



