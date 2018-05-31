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