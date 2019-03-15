# Typical Workflow for Completing a User Story

1. Open story detail page in Taiga.
2. Assign yourself to story.
3. Set status to `In progress`. As any subtasks progress, move the through the sprint taskboard accordingly.
4. Make sure title and acceptence criteria are complete and good quality.
5. Add all known subtasks.
6. Update/verify the use case scenarios and diagrams to properly reflect your story.
7. Update/verify user manual entry related to your story.
8. If you have not already cloned the repository from Github, clone it to the directory of your choice. e.g. `git clone <repo url>`
9. If you have already cloned the repo, update it with `git pull`. Do this from the `master` branch. If you are not on the `master` branch, switch to it using `git checkout master`.
10. Create a temporary local branch where you will work on implementing the User Story. Name it the same as the ID of the User Story. `git checkout -b <User Story ID>`. This command will create a new local branch and switch to that branch.
11. Update/verify the acceptance tests for your story.
12. TDD cycle
      1. Update/verify the unit tests for your story.
      2. Implement the code to satisfy your story's requirements.
      3. Refactor.
13. Stage your code changes, by running `git add <path to unstaged file>`. If you want to stage multiple files, you can separate them by a space. The path argument also accepts regular expressions, as well as directories. For example, a commonly used command is `git add .`, which will stage all files in the current directory.
14. Commit your changes with `git commit -m "<commit message>"`. Your commit message should include the User Story ID as well as any relevant information. You can also enter a more detailed and structured commit message by omitting the `-m` argument. This will open a text editor (typically Vi), where you can enter a commit message. The first line will be treated as a title and should be followed by a blank line. The remaining lines will be treated as the message. Any line preceded by a `#` will be ignored and not included in the message. Using the Vi editor may require extra knowledge so quick commits with the `-m` argument are acceptable.
15. Push your changes to the remote repository on GitHub with `git push origin <temporary branch name>:<temporary branch name>`. e.g. `git push origin GRP3-4453:GRP3-4453`.
16. Visit the repository page on github.com.
17. Click on the link that shows `"<x> branches"`. You will see all of the available branches.
18. Click on the button that shows `"New pull request"`.
19. Ensure that the base branch is `master` and the compare branch is the one that you just created.
20. Ensure that the title is the same as the branch name.
21. Click the button that shows `"Create pull request"`.
22. The pull request is now available for a code review from another team member.

# Code Review Workflow

1. Visit the repository page on github.com.
2. Click the link that shows `"Pull requests"`.
3. Click on the pull request that you will be reviewing.
4. Perform the code review by looking at the code changes. Do this by clicking the link that shows `"Files changed"`. Leave comments as necessary.
5. If the code change is at all significant, checkout the branch locally and run the application and unit tests to verify that everything works as intended by the User Story. Do this with `git checkout origin/<branch name>`.
6. Click the button that shows `"Review Changes"`. Either select the `"Approve"` radio button or the `"Request changes"` radio button.
7. Click the button that shows `"Submit review"`.

# Actions after your code has been reviewed

1. Respond to any requested changes by discussing them in the pull request comments on the `"Conversation"` tab, or by implementing those changes locally.
2. Stage, commit, and push those changes to the same branch as the pull request. The pull request will be updated automatically.
3. If there are no requested changes, but instead there is an approval, go to the `"Conversation"` tab of the pull request and click arrow to the right of the button that shows `"Merge pull request"`. Select the `"Squash and merge"` option. This will combine all of your commits into 1 for the entire User Story.
4. After verifying that all of the tests pass in the `master` branch, delete the branch that you used for the pull request. Do this by visiting the repository page on GitHub, clicking the link that shows `"<#> branches"`, then clicking the trash can icon next to the branch you wish to delete. Affirm any confirmation dialogs.
5. Switch to your local `master` branch with `git checkout master`, then pull in your newly merged changes with `git pull`.
6. Delete the local branch that you used for this pull request with `git branch -D <branch name>`. You can see all of your local branches with `git branch`.
