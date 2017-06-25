#### How to fetch a file from another branch to the current one
`git checkout branch_name -- filename` - from [Safia Abdalla](https://twitter.com/captainsafia/status/864246151767261184)

#### How to show a gitk-like tree with git command line?
`git log --graph --decorate`

#### How to delete remote branch named `kyle`
`git push origin :kyle`

#### How to remove untracked files from git (all but those in .gitignore)?
`git clean -x`

#### How to undo a git commit?
`git reset --hard HEAD~1`

#### How to undo a pushed commit?
`git push -f origin last_known_good_commit:branch_name`

#### Undo all changes from last commit
`git reset --HARD`

#### Show `git log` with diffs
`git log -p`

One of the more helpful options is -p, which shows the diff introduced in each commit. You can also use -2, which limits the output to only the last two entries: $ git log -p -2
