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
```
