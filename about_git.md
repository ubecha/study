Git, GitHub
==================================================

Git
--------------------

### 설치

- client install 
- [git site](https://git-scm.com/)
- [document](https://git-scm.com/book/ko/v2/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EB%B2%84%EC%A0%84-%EA%B4%80%EB%A6%AC%EB%9E%80%3F)

git command
--------------------

```cmd
git init
```

initialize a Git repository. It has an empty repository in /.git/

the repository is a hidden directory where Git operates. (로컬 데이터베이스 개념)

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

`git add` 명령은 파일을 새로 추적할 때도 사용하고 수정할 파일을 Staged 상태로 만들 때도 사용한다.
Merge 할 때 충돌난 상태의 파일을 Resolve 상태로 만들때도 사용한다.
add의 의미는 프로젝트에 파일을 추가한다기 보다는 다음 커밋에 추가한다고 받아들이는게 좋다.

`git add` 명령을 실행한 후에 또 파일을 수정하면 git add 명령을 다시 실행해서 최신 버전을 Staged 상태로 만들어야 한다.

```cmd
git commit -m "Add memo"
```

store our staged changes in the reposoitory

```cmd
git log
```

browse them to see what we changed

```cmd
git remote add origin https://github.com/ubecha/study.git
```

after create github repository, to push our local repo to the GitHub server we'll need to add a remote repository
git remoe add [단축이름] [url] 의미.

```cmd
git clone https://github.com/ubecha/study.git
```

`git clone`은 사실 다른 명령어를 몇 개 실행한다. 디렉토리를 만들고 디렉토리로 들어가고 나서 `git init` 명령으로 빈 Git 저장소를 만든다. 그다음 입력한 URL을 `origin` 이라는(기본값) 이름의 리모트로
추가하고(git remote add) git fetch 명령으로 리모트 저장소에서 데이터를 가져온다. 마지막으로 최종 커밋을 워킹 디렉토리에 Checkout 한다(git checkout).

```cmd
git push -u origin master
```

-u option 을 사용하는 이유는 파라미터를 기억하고 다음번엔 git push 만 입력하면 되게

정리를 하자면, 결국 staging area 에 파일들을 add, remove 하고 나서 특정 작업이 끝나고 나서 commit 을 하면서
memo 를 추가해서 어떤 작업에 어떤 파일들이 이용되었는지 tagging 한 후에, 원격저장소에는 push 를 이용해서 올리는거라 보면 된다.

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

용어정리
--------------------------------

- **저장소(Repository)**: 작업자가 변경한 모든 내용을 추적하는 공간. 일종의 로컬 데이터베이스 개념
- **작업트리(Working Tree)**: 저장소의 어느 한 시점을 바라보는 작업자의 현재 시점
- **체크아웃(Checkout)**: 작업자의 작업트리를 저장소의 특정 시점과 일치하도록 변경하는 작업
- **스테이징영역**: 저장소에 커밋하기 전에 커밋을 준비하는 위치 (변경사항을 적용하기 전에 한번 더 변경사항을 정리하고 다듬을 수 있는 기회를 제공. 변경사항을 추가하기 위해서는 git add 를 사용. 커밋 예정인 변경사항이 있다고 보면 된다.)
- **브랜치(branch)**: 하나의 개발 라인을 의미. 이러한 브랜치에는 HEAD(branch head)라는 것이 있는데 이는 한 개의 브랜치 내에서 가장 최근에 커밋이 된 내용을 의미.
- **master**: master 브랜치는 복사해온 저장소 내의 HEAD 의 복사본
- **origin**: git 가 복사해 온 저장소를 가리키기 위해 기본적으로 사용하는 이름.