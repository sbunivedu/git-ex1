# Git Exercise 1
[source](http://jnthn.net/training/git/exercises.pdf)
## Task 1
1. Clone this repository in your Cloud9 workspace.
1. Create a README.txt file.
1. Look at the output of the ```git status``` command; the README you created should appear as an untracked file.
1. Use the ```git add``` command to add the new file to the staging area. Again, look at the output of the ```git status``` command.
1. Now use the ```git commit``` command to commit the contents of the staging area.
1. Create a src directory and add two files to it. Use the ```git status``` command on the repository root path; verify that the new directory appears as untracked.
1. Use the ```git add``` command, but name the directory, not the individual files. Use the ```status``` command. See how both files have been staged. Commit them.
1. Make a change to one of the files. Use the ```git diff``` command to view the details of the change.
1. Next, add the changed file, and notice how it moves to the staging area in the status output. Also observe that the diff command you did before using add now gives no output. Why not? What do you have to do to see a diff of the things in the staging area? (Hint: ```git diff --cached```)
1. Now – without committing – make another change to the same file you changed in step 8.
Look at the status output, and the diff output. Notice how you can have both staged and unstaged changes, even when you’re talking about a single file.
Observe the difference when you use the ```git add``` command to stage the latest round of changes. Finally, commit them. You should now have started to get a feel for the staging area.
1. Use the ```git log``` command in order to see all of the commits you made so far.
1. Use the ```git show``` command to look at an individual commit.
How many characters (from the left) of the commit identifier can you get away with typing at a minimum?
1. Make a couple more commits, at least one of which should add an extra file.

## Stretch Task
1. Use the ```git rm``` command to remove a file. Look at the status afterwards. Now commit the deletion.
1. Delete another file, but this time do not use git to do it; e.g. if you are on Linux, just use the normal (non-git) ```rm``` command.
1. Look at the status. Compare it to the status output you had after using the git built-in rm command. Is anything different? After this, commit the deletion.
1. Use the ```git mv``` command to move or rename a file; for example, rename README to README.txt. Look at the status. Commit the change.
1. Now do another rename, but this time using the operating system’s command to do so. How does the status look? Will you get the right outcome if you were to commit at this point?
(Answer: almost certainly not, so don’t.) Work out how to get the status to show that it will not lose the file, and then commit. Did git at any point work out that you had done a
rename?
1. Use ```git help log``` to find out how to get git to display just the most recent 3 commits. Try it.
1. Imagine you want to see a ```git diff``` that summarizes all that happened between two commit identifiers. Use the diff command, specifying two commit identifiers joined by two dots (that is, something like abc123..def456). Check the output is what you expect.

## Task 2

1. Run the ```git status``` command. Notice how it tells you what branch you are in.
1. Use the ```git branch``` command to create a new branch.
1. Use the ```git checkout``` command to switch to it.
1. Make a couple of commits in the branch – perhaps adding a new file and/or editing existing ones.
1. Use the ```git log``` command to see the latest commits. The two you just made should be at the top of the list.
1. Use the ```git checkout``` command to switch back to the master branch. Run ```git log``` again. Notice your commits don’t show up now. Check the files also – they should have their original contents.
1. Use the checkout command to switch back to your new branch. Use ```git log --pretty=format:"%h %s" --graph``` to take a look at the commit graph; notice it’s linear.
1. Now checkout the master branch again. Use the ```git merge``` command to merge your branch in to it. Look for information about it having been a fast-forward merge. Look at git log, and
see that there is no merge commit. Take a look in ```git log --pretty=format:"%h %s" --graph``` and see how the graph is linear.
1. Switch back to your branch. Make a couple more commits.
1. Switch back to master. Make a commit there, which should edit a different file from the ones you touched in your branch – to be sure there is no conflict.
1. Now merge your branch again.
1. Look at git log. Notice that there is a merge commit. Also look in ```git log --pretty=format:"%h %s" --graph```. Notice the graph now shows how things forked, and then were joined up again by a merge commit.
## Stretch Task
1. Once again, checkout your branch. Make a couple of commits.
1. Return to your master branch. Make a commit there that changes the exact same line, or lines, as commits in your branch did.
1. Now try to merge your branch. You should get a conflict.
1. Open the file(s) that is in conflict. Search for the conflict marker. Edit the file to remove the conflict markers and resolve the conflict.
1. Now try to commit. Notice that git will not allow you to do this when you still have potentially unresolved conflicts. Look at the output of status too.
1. Use the add command to add the files that you have resolved conflicts in to the staging area. Then use commit to commit the merge commit.
1. Take a look at git log and ```git log --pretty=format:"%h %s" --graph```, and make sure things are as you expected.
1. If time allows, you may wish to...
* Delete everything but your ```.git``` directory, then do a checkout command, to prove to yourself that this really will restore all of you current working copy.
* Create a situation where one branch has changed a file, but the other branch has deleted it. What happens when you try to merge? How will you resolve it?
* Look at the help page for merge, and find out how you specify a custom message for the merge commit if it is automatically generated.
* Look at the help page for merge, and find out how to prevent git from automatically committing the merge commit it generates, but instead give you chance to inspect it and merge it yourself.
