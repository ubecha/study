Git, GitHub
==================================================

Git
--------------------

### git install

- client install 
- [git site](https://git-scm.com/)

git command
--------------------

```cmd
git init
```

initialize a Git repository. It has an empty repository in /.git/

the repository is a hidden directory where Git operates.

```cmd
git status
```

to see what the current state of our project is

untracked is Git sees that file is a new file

```cmd
git add octocat.txt
or
git add '*.txt'
```

add it to the staging area, start tracking changes made to octocat.txt

not in repository yet. we could add or remove files from the stage before we store them in the repository

Remember, staged files are files we have told git that are ready to be committed

```cmd
git commit -m "Add memo"
```

store our staged changes in the reposoitory 

```cmd
git log
```

browse them to see what we changed

After GitHub repository
---------------------------

```cmd
git remote add origin https://github.com/ubecha/study.git
```

to push our local repo to the GitHub server we'll need to add a remote repository

### Pushing Remotely

```cmd
git push -u origin master
```

- *origin* : the name of our remote
- *master* : the default local branch name
- *-u* : tells Git to remember the parameters, next time simply run git push

정리를 하자면, 결국 staging area 에 파일들을 add, remove 하고 나서 특정 작업이 끝나고 나서 commit 을 하면서
memo 를 추가해서 어떤 작업에 어떤 파일들이 이용되었는지 tagging 한 후에, 
원격저장소에는 push 를 이용해서 올리는거라 보면 된다.

```cmd
git diff HEAD
```

take a look at what is different from out last commit

```cmd
git diff --staged
```

to see the changes you just staged

```cmd
git reset octodog.txt
```

unstage files

```cmd
git checkeout -- octocat.txt
```

get rid of all the changes since the last commit for octocat.txt

```cmd
git branch clean_up
```

create a branch called clean_up
two local branches : master, clean_up

```cmd
git checkout clean_up
```

switch branches using the git checkout 

```cmd
git merge clean_up
```

after git checkout master, we're already on the master branch
you have to merge your changes from the clean_up branch into the master branch

```cmd
git branch -d clean_up
```

delete a branch