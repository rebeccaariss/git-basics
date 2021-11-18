# git-basics
The most frequently used Git commands &amp; workflows boiled down to the absolute basics

Study notes for the *Git + GitHub + Open Source Projects* section of [Andrei Neagoie's](https://twitter.com/AndreiNeagoie) [The Complete Web Developer in 2022: Zero to Mastery](https://www.udemy.com/course/the-complete-web-developer-zero-to-mastery/)

*Please note that this information reflects my current understanding of Git & GitHub and might have some mistakes! I am still learning and would appreciate any feedback or edits to this file. Feel free to open a request for corrections.*

## Basic Git Workflow
For adding updates and any changes to a project repository
1. **git status**
2. **git add ______** either " **.** " (all files in working directory) *or* "**filename.ext**"
3. **git commit -m “message here”**
4. **git push** (to repository) (when this command is executed, pull request is automatically created on GitHub repo)
5. From the GitHub repository *Pull Requests* tab, you can then *open* this pull request and leave a more detailed message for your teammates (for example: "*Name*, I have changed *feature* to accomplish *x*. What do you think?")

## Other Frequently Used Commands & Tips
- **git clone** for your first time accessing a project (to clone copies of the project files to your local)
- **git pull** to see most recent changes by others. This will likely be one of the first things you do in the morning at work!
- Remember that the **master** branch has been renamed to **main** recently.

## Workflow for Working on a New Branch
1. **git branch** to see working branch (highlighted with " * ") as well as other existing branches
2. **git branch newbranchname** to create a new branch
 - **git branch** again to confirm that your new branch is now listed
3. **git checkout newbranchname** to switch from initial branch to newly created branch
4. Once you've finished your work on the project, repeat the basic workflow for any changes you made (**status**, **add**, **commit**, **push**).

## A Note on Pull Requests:
A pull request is not always made to your own computer (re: using **git pull** to start your work day).
**Merging** to the *main branch* (or *production*) happens *as a result of a pull request* which has been approved by a team member who has the authority to approve requests. Effectively, the changes you have made while working on a new feature from a side branch will be "pulled" into the main branch.

Here's that workflow again in plain English:
1. Pull request is made by developer who has made changes to project within side branch
2. Senior developer (most likely) reviews the changes and can suggest edits (they can even leave comments on specific lines requiring changes)
 - If editing is required, side branch dev makes the necessary changes before initiating another pull request
 - This inner cycle repeats until the code is ready to be added to the main branch
3. Senior developer approves the changes and clicks the big green button (from the GitHub UI) to merge changes onto main branch
4. Do it all over again!

Think of pull as "pulling changes" from one place to another. **git push** is not the ultimate end to a workflow. Remember that the pull request (“PR”) initiated by that **git push** command should ideally be further addressed on GitHub by the initiator (whose responsibilty is to open a pull request and add a more detailed message).

## Final Review of Basic Team Workflow:
- Project repositories hosted on GitHub will have a main branch (the code that is in production) and several side branches (side branches represent new features or changes to existing code which developers are actively working on)
- Whenever you are working on something, you'll create a side branch with the title of the feature you're developing
- Every once in awhile you'll want to **pull main** and **merge main** so that you're not missing out on any additions from other teammates
- Once you're done with your feature on the side branch, you make a pull request by running **git push**
- Then you'll go to the GitHub page for the pull request where you will add additional context in a message
- Your teammates will review your code
- If they want you to make some changes, you'll make the changes and then run **git add**, **git commit**, and **git push** again
- Code is reviewed again; cycle repeats until everyone is satisfied
- When that's all done, someone clicks the "**Merge pull request**" button to merge the changes into the main branch for deployment to the actual product/website
- Once the merge is complete, everyone on the team should be running **git pull** to ensure that they have all the relevant changes for work on their local files
