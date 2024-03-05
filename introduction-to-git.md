# Introduction to version control with Git and GitHub

From the course **100 Days Of Code - 2024 Web Development Bootcamp** by Academind.

## Useful Git commands

- Rename master to main `git branch --move master main`

- List the current status: `git status`

- List changes: `git log`

- Add changes to staging area: `git add .` (Alternatively specify file instead of . for all)

- Commit the changes: `git commit -m "what changed"`

- View branches `git branch`

- Change branch: `git checkout` + name of branch

- Make a new branch: `git checkout -b "name of new branch"`

- Remove file from current folder: `git rm` + name of file

- Change index (Revert changes) `git reset --hard HEAD~1` moves the "head" back one commit.

- Delete branch `git branch -D` + name of branch to delete. (cannot be the one you are currently in.)

- Reset the branch to the latest commit (un-stage files) `git checkout -- .`

- Connect to a remote (GitHub) repository `git remote add origin` + url of the depository at GitHub

- Push to repository `git push origin main` (pushed to origin on main branch)

## Personal Access Tokens

To delete the token from the computer (to be able to add a new one), run the following command in VSCode terminal:

`git credential reject`

`host=github.com`

`protocol=https`
