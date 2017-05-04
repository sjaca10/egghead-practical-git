# egghead-practical-git
Implementation of Practical Git course to improve git use.

# README from course

A collection of utility functions

# Examples

```
getRandomElement([1, 2, 3])
//=> 2
```

```
getRandomNumber(1, 10);
//=> 4
```

```
getURLSlug('My Favorite Songs');
/ => 'my-favorit-songs
```
# Git commands used in the project and a little explanation

```
$ git init
```
initializes and empty git repository

```
$ git remote add origin git@github.com:user/repo.git
```
origin: name of the remote, the repo  will have a remote set up on the repo

```
$ git remote -v
```
shows the URLs were added like remotes to the repo

```
$ git clone git@github.com:user/repo.git
```
download to the specified or default folder a repository from the remote given in the URL, the cloned repo gets all files from the remote and the .git config folder

```
$ git status
```
tell us the status of the repo, if it's clean, has uncommited changes, new or deleted files or directories or has commited changes

```
$ git add -A
```
add all the files and directories to the stage, it's a previous step of commit to define which files will be included in the commit

```
$ git commit -m "Message"
```
Create a commit with the files and directories in the staging area with the message (-m) specified

```
$ git push
```
Send the commited changes to the remote repository to store and versioning them

```
$ git pull
```
download and apply the changes commited by other developers/contributors of the repository, `git pull` is the short version of the proccess of execute the commands:

```
$ git fetch
```
which grab the lastest changes from the remote repository and store them withou apply them to the local repository

and

```
$ git merge
```
which combine the lastest changes from the remote repository with the local repository

```
$ git branch new-feature
```
create a new branch (`new-feature`) generated from the branch where the command is executed

```
$ git branch
```
list all branches, the current branch is marked by '*'

```
$ git checkout new-feature
```
changes the current branch to the specified branch (`new-feature`)

```
$ git checkout -b new-feature-2
```
it is a shortcut for the commands `git branch new-feature-2` and `git checkout new-feature-2`, this means that create a new branch `new-feature-2` and move to the new branch

```
$ git checkout -
```
like in UNIX based systems the `-` means the last, so with this command we can change to the last branch where we were

```
$ git merge url-slugs
```
combine the current branch and the specified branch together into the current branch

```
$ git branch -d url-slugs
```
delete the local `url-slugs` branch


When we try to merge and a same line has been edited by more than one author then a conflict is generated. To identify the conflict we could execute `git status` and the file(s) with status `both modified` must be fixed. When we open the file with a conflict, we could find something like:

```
<<<<<<< HEAD
    ...code
=======
    ...more code
>>>>>>> 251398d53a0b4dba7ee0c24b3c64de6c85ae2d1f
```

the code between `<<<<<<< HEAD` and `=======` is our new code that we modified and the code between `=======` and `>>>>>>> 251398d53a0b4dba7ee0c24b3c64de6c85ae2d1f` is the code from the remote.


```
$ git add -A
$ git stash
```
git has returned our working directory to the state of the previous commit and our uncommited changes have been saved temporarily in the .git folder locally

```
$ git stash apply
```
this brought back the uncommited changes we had saved, if a conclit is generated it must be solved in the same way that the conflicts was saved in `git merge`

```
$ git log
```
open up a terminal pager that shows up the commits information from the last to the first commit, we can use some shortcuts to move through the terminal pager:
`q` to quit
`j` or `down arrow` to move down in the log
`k` or `up arrow` to move up in the log
`PageUp` or `ctrl + f` to move forward
`PageDown` or `ctrl + b` to move backward
`/` to search some word and `n` to move to the next occurrence and `N` to the previous occurrence

```
$ git log --oneline
```
shows the log in a single line, with only the hash and the commit message

```
$ git log --decorate
```
shows the log with all references of the commits

```
$ git log --graph
```
display an ask-er graph of the branch structure of each commit

```
$ git log -p
```
display the commit information and the modifications made in every commit

```
$ git log --stat
```
shows the number of insertions and deletions for each commit change (statistics)

```
$ git log -3
```
shows the last 3 commits in log format

```
$ git log --after="yesterday"
$ git log --after="30 minutes ago"
$ git log --after="last tuesday"
$ git log --after="last week"
$ git log --after="2 weeks ago"
$ git log --after="3-15-17"
$ git log --after="3/15/17"
```
shows the commits that have happened between now and yesterday, the `after` keyword could be replaced by `since`

```
$ git log --before="yesterday"
```
shows the commits that have happened between yesterday and the init of history, the `before` keyword could be replaced by `until`

```
$ git log --author="Javier"
```
shows all the commits that have the word Javier in the author or email data

```
$ git log --author="sjaca\|Javier"
```
shows all the commits authored by sjaca or Javier

```
$ git log --grep="regex"
```
shows all the commits that have the `regex` regular expression in the commit message

```
$ git log -S"Math"
```
shows all the commits that have the `Math` word modified inside the changed files

```
$ git log -GMath\|Random
```
shows all commits that match with the regular expression `Math\|Random` inside the changed files

```
$ git log -i --author="javier"
```
shows all the commits made by the author `javier` ignoring the capitalization (-i ignore case)

```
$ git log --no-merges
```
shows the commits without the merges commits

```
$ git log master..branch
```
shows the commits that exists in both references (master and branch branch)

```
$ git log file.extension
```
shows the commits related with the file file.extension

```
$ git diff
```
shows the difference between two references, by default last commit versus the current working directory

```
$ git diff --stat
```
shows the statistics of the difference between the default references

```
$ git diff --cached
```
shows the difference between the references: working directory and staging area

```
$ git diff HEAD
```
display the changes between both the working directory and the staged changes compared with our last commit

```
$ git diff branch
```
display the difference in the branch

```
$ git diff origin/master getRandom.js
```
shows the difference for an specific branch and an specific file

```
$ git blame myfile
```
display the commit, author and date which modified every line in the file myfile

```
$ git tag v1.0.0
```
create a tag with the label v1.0.0, create a reference to a commit that can't be changed, usually combined with semantic versioning

```
$ git tag
```
display all the tags existing in the repo
