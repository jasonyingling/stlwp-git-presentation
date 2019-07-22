# Git in WordPress Development
## What is Git?
Git is a version control system that makes it easier for multiple people to develop software as well enable the ability to revert and branch off the codebase.

## Why Git?
Open source software that is developed and iterated on by a large number people. (e.g. WordPress)

Allowing for parallel development along a codebase. (e.g. hot fixes to software during other on-going development work)

```
# Demo Notes
// Start up Local by Flywheel and SSH into server
// Build out a plugin to create a repo for
wp scaffold plugin stl-wp
```

## Initializing Git
Create a repository on a service like Github or BitBucket. If from an existing codebase don’t initialize with .gitignore or readme.md.

From an existing codebase run `git init`

Grab the git repo URL and run `git remote add origin {repo_url}`

Note: `origin` in the above example is a `name` for the remote. You can add different remotes add different names if you’d like. `origin` is the default to use.

```
# Demo Notes
// Displays remote URLs
git remote -v
```

## Creating a .gitignore file
The `.gitignore` tells git files you don’t want to version

Common items:
* Media files (they can get large)
* Hidden files
* Development files (node_modules)
* System files (.DS_Store)
* Sensitive information (wp-config.php, API Keys, etc.)

## README.md
Readme files are great for giving others instructions on how to use your tool. Written in Markdown.

## Adding Files
`git add .` to add all changes to stage for a commit

## Committing Files
`git commit -am “message”` to create a commit along with a nice message. Be descriptive. You’ll thank yourself down the road.

## Pushing
`git push origin master` pushes to the `master` branch of the remote named `origin`.

## Pulling
`git pull origin master` pulls the latest of the `master` branch.

## Fetching
`git fetch` will pull down new branches that were created since you cloned the repository.

## Merge conflicts
Oh noes! A merge conflict. Let’s fix it.

`git mergetool`

## Cloning Repos
You can clone repos through SSH or HTTPS. Using HTTPS requires to constantly enter your password. I recommend SSH.

To do that add your SSH key. [Adding a new SSH key to your GitHub account - GitHub Help](https://help.github.com/en/enterprise/2.15/user/articles/adding-a-new-ssh-key-to-your-github-account)

`git clone {repo_url}`

Using `.` to clone contents into a directory.

## Branching
`git checkout -b {branch}` to create a new branch off the current branch.

## Pushing Branches
`git push origin {branch}`

## Submitting Pull Requests
Push up from a fork and submit a pull request. 

Or submit a branch and make a pull request to another branch.

Any new commits to a branch with an open PR will automatically be added into that PR.

## Reverting
Reverting creates a commit that is opposite of an existing commit.
`git log`

`git revert {sha}`

## Resetting
`git reset --hard origin/{branch}`

## Forking
Show fork in Github.

Now you can branch, push and submit PRs to other people’s code

Note: Don’t push to a branch you may update while a PR sits open. Any new commits to a branch with an open PR will auto-update to add those commits.

## Tagging
`git tag {tag}` to create tagged versions of a project

## Releases
Show creating release on GitHub.

## Pro Tips
`git stash` and `git stash apply`

`git diff > ~/my_changes.whatever` and `git apply ~/my_changes.whatever` Note: haven’t used this yet

Symlinking for plugin / theme development.
