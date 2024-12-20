# 🧩 Git, GitHub 간단 정리

## Git❓
- git은 파일의 상태를 저장하는 프로그램이다.
- commit한 시점의 파일들의 상태를 저장해놓는다고 생각하면 된다. (branch를 옮겼을 때에도 마찬가지)

## Git, GitHub ❓
- 정말 간단하게 github은 원격 저장소이고, git은 local version 관리 프로그램이다 !
- **git**에서 마음껏 version 관리를 해놓은 **commit들**을 push해서 **github**에 저장한다. 

## Stage ❓
- commit시키기 전 파일들에게 마음의 준비를 시켜주는 장소임.. 🙏
- Stage에 올라간 파일들은 commit대기중인 파일들인 것.

<br>

## ⌨️ 명령어

<br>

### 🛠 git 설정 & 초기화

```
# git version 확인 !

$ git --version
```

```
# 🌱 git 저장소 초기화. 초기화 하면 [ .git ] 이라는 폴더가 생기며 version관리 시작가능 !

$ git init
```

> note. --global 옵션을 빼고 입력하게되면 Repository단위로 설정하는것 입니다.
```
# 🌏 git 글로벌 설정 목록 조회 

$ git config --global --list
```

```
# 글로벌 사용자 설정

$ git config --global user.name "User name"
```

```
# 글로벌 이메일 설정

$ git config --global user.email "git@gmail.com"
```

```
# 기본 브랜치를 main으로 설정

$ git config --global init.defaultBranch main
```

```
# 자주 사용하는 명령어 alias 설정

$ git config --global alias.c checkout
```

```
# alias 설정 해제

$ git config --global --unset alias.c
```

```
# alias 조회

$ git config --global --get-regexp alias
```

### ☁️ 원격 저장소와 연결하기
```
# 🚀 local git과 원격 저장소(GitHub)의 repository와 연결한다. 

$ git remote add origin https://github.com/github-user/github-repository.git
```
> note. 여기서 origin은 원격 repository의 별칭이다.

```
# 💎 github-user의 github-repository 저장소 복제하기

$ git clone https://github.com/github-user/github-repository.git
```
```
# 👀 현재 local 저장소와 연결된 원격 저장소 url 확인

$ git remote -v
```

### 🧑🏻‍💻 파일 상태 다루기,상태 확인하기 원격 저장소에 올리기

``` 
# 👀 현재 상태 확인 commit할 파일이 있는지 add할 파일이 있는지

$ git status
```

```
# 👆 전체 파일 stage에 올리기 dot, --all option 대신에 파일명을 쓰면 해당 파일만 올라감
$ git add .

$ git add --all
```

```
# 👇 전체 파일 unstage. 스테이지에서 내리기. dot 대신에 특정 파일만 내릴수도 있음.
$ git reset HEAD .
```

```
# 📸 stage에 올라간 파일,디렉토리 commit하기. 현재 상태를 저장한다. (현재 시점을 사진 찍는것과 같은 느낌.)

$ git commit -m "commit message"
```

``` 
# 👀 commit log 확인하기

$ git log
```

```
# $ git log 를 통해 commit hash code를 복사하여 해당 📸 시점으로 돌아가기. hash code만 있으면 앞, 뒤로 원하는 시점으로 돌아갈 수 있음.
# --hard option 말고 다른 option들도 있습니다.

$ git reset --hard 91f61e82b0175d49c4fceda57d8b9133432f124f
```

```
# 🚀 commit한 내용들을 원격 저장소 main branch에 밀어넣기.

$ git push origin main
```

```
# 원격 저장소 main branch의 코드들을 local repository에 동기화한다. 

$ git pull origin main
```

### 🌱 Branch

```
# 🌱 branch 생성하기
# 현재 커밋 상태부터 branch가 생성되며 생성 이후로는 하나의 큰 줄기에서 뻗어나가는 가지처럼 갈라진다.
# 갈라진 가지들, branch들은 각자의 삶을 살다가 pull request를 통해 merge하면 다시 합칠 수 있음 !

$ git branch <branchname>
```

``` 
# 👀 현재 branch 확인하기

$ git branch
```

```
# 👉 branch 이동하기 !

$ git checkout branch002
```

```
# branch 삭제하기

$ git branch -d branch002
```

```
# 원격(remote) branch checkout하기

$ git checkout -t origin/feature/test-branch
```

### tag 🏷️

```
# remote에 없는 local tag삭제

$ git tag -l | xargs git tag -d && git fetch -t
```

