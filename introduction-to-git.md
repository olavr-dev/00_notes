# Introduction to version control with Git and GitHub

From the course **100 Days Of Code - 2024 Web Development Bootcamp** by Academind.

## Useful Git commands

- Rename master to main `git branch --move master main`

- List the current status: `git status`

- List changes: `git log`

- Add changes to staging area: `git add .` (Alternatively specify file instead of . for all)

- Commit the changes: `git commit -m "what changed"`

- View branches `git branch`

- Change branch: `git checkout (branch)`

- Make a new branch: `git checkout -b "name of new branch"`

- Remove file from current folder: `git rm (filename)`

- Change index (Revert changes) `git reset --hard HEAD~1` moves the "head" back one commit.

- Delete branch `git branch -D (branch)` (cannot be the one you are currently in.)

- Reset the branch to the latest commit (un-stage files) `git checkout -- .`

- Connect to a remote (GitHub) repository `git remote add origin (url)`

- Push to repository `git push origin main` (pushed to origin on main branch)

- Clone a repository directly into open folder `git clone (url) .`

## Personal Access Tokens

### If you do not want to sign in to GitHub using the browser, you can use a Personal Access Token

> Generate one by going to Github => Settings => Developer Settings => Personal Access Tokens

To delete the token from the computer (to be able to add a new one), run the following commands in the VSCode terminal:

`git credential reject` => Enter

`host=github.com` => Enter

`protocol=https` => Enter

## Collaborating with other people

### Invite other people to work on your private repository by following these steps

> Repository => Settings => Collaborators => Add people

After gaining access, you clone the repository and work on it as if it was your own. Collaborators will have push access.

## Contributing to projects

If you are not a collaborator, you can instead create a fork of the repository.
This will enable you to work on open source projects.

> Repository => Fork

This will give you full access to this project as if it was your own.

You can now clone it to import it into VSCode.

After making your changes or maybe adding features, you can inform the user of the original repository by creating a pull request.

> Repository => Pull requests

Remember to give a detailed description of what changes you made.
