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
