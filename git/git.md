# Git Bash

## Git Bash 설치

https://git-scm.com/download/win

## Git Bash란?

- `Command Line Interface(CLI)` - 명령을 줄글로 치는 인터페이스
- `인터페이스` : 두 환경이 만나는 접점 (ex, HDMI, 키보드 마우스 등등)
- *sh script(쉘 스크립트)*라는 명령어(언어) 사용

### 함수

| 함수명                | 함수 의미                                                    | 추가                                                         |
| --------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| touch                 | 파일 생성                                                    |                                                              |
| mkdir                 | 폴더 생성                                                    |                                                              |
| cd = change directory | 파일 선택, 언제든지 홈 폴더로 돌아갈 수 있음                 | cd .. : 위로 가기                                            |
| ls                    | 파일 목록 확인                                               |                                                              |
| rm -r 폴더명          | 폴더 삭제                                                    | 폴더 삭제를 위해 -r 옵션을 붙입니다. (r은 recursive의 약자인데, 순회하면서 모든 내용을 삭제한다는 뜻입니다.) |
| code .파일            | 지금 들어가는 파일을 vscode로                                |                                                              |
| ~                     | 홈폴더(=계정명 폴더)의 의미를 갖고 있음                      | 내 노트북에선 user로 설정되어 있음                           |
| /                     | 최상단  root                                                 |                                                              |
| *                     | 와일드 카드, 전체 선택                                       | *.txt는 텍스트 형태의 모든 파일을 의미                       |
| -a                    | 옵션-all                                                     | 숨김 파일 폴더까지 전부 보여줌                               |
| .파일이름             | 히든 파일, 파일명 앞에 `.`로 시작 시                         | 윈도우에선 보이지만 리눅스에선 안보임                        |
| mv                    | 1. 파일을 폴더 내로 이동할 때 사용 2. 기존에 파일이 존재하던 폴더 이름 변경(목적지 없는 파일일 시) | "mv aaa.txt CLI/" 입력하면 aaa.txt 파일이 CLI 폴더 내로 이동합니다. |
| start 파일            | 파일 열기                                                    | 리눅스 체계에선 open 사용.                                   |
| start .               | 홈폴더 열기                                                  |                                                              |
| .                     | 내 위치                                                      |                                                              |



# Visual Studio Code

## Visual Studio Code 설치

https://code.visualstudio.com/docs/?dv=win

https://code.visualstudio.com/docs/?dv=osx

설정된 폴더가 깃이 관리할 폴더가 될 것임!



# VSCode로 Git 사용하기

 ctrl + L 누르면 화면 위로 올림

 ctrl + S :저장(필수)



**NEVER**

1. ~에서 `$ git init` 진행 
2. 리포 안에 리포 만들기
3. `$ git init 입력 전 확인할 점`
   1. ~ 인지
   2. (master) 떠 있는지 확인





- git init # :git 저장소 관리 시작하기
  - (master) : 리포가 됐다는 뜻
  - 상위는 해당사항 없고 하위는 자동적으로 관리대상 되는 것
- git status
  - commit (버전) =snapshot : 기록을 남긴다!

- git commit -m 'first commit' : first commit이라고 메시지 남겨 놓는단 뜻

- 첫번째 커밋 성공!

  - root commit이 중요

  - log를 통해 나의 커밋 확인





- 초기화 시점에 1회 입력

```
$git init # 초기화 시점에 1회 입력
```

- 작업하며 계속 입력(핵심)

```
$git add <filename>
$ git commit -m 'MESSAGE' # 메모 적어놓는 것
```

- 모니터링 명령어

```
git status #현재 상황
git log    #commit log
```



- 변경사항 -> **스테이징된 변경사항**
  - `git add README.md`  입력 후 변경됨



`광고 촬영 현장과 비교하자면?`

- 코드를 짠다 = 분장, 메이크업을 한다

- 스테이지로 모델을 보낸다 (스테이징)
- 사진을 찍어서 저장한다(커밋)



```
$ git restore --staged <file>... # 스테이지에서 내리고 싶다면 사용
```

빨 - 커밋 안된다

초 -커밋 가능



- $ git log 가 길어지면 마지막에` : `나옴 -> q  입력



 $ git remote add origin [주소] # 깃허브와 연결

 $ git push -u origin master  # 수동으로 깃허브에 보내주기

 clone 내용 추가

 원격 저장소의 내용 받아오기
 ```sh
 $ git pull origin master
 ```

 # Git 사용법2

```
$ git remote add origin <URL>
```

- 딕셔너리로 생각해보면, origin(원격저장소 이름)이 키, url이 벨류

- url에다가 오리진으로 저장해놓는 것 (사진을 다른 클라우드에 저장하는 개념)



```
$ git remote -h  # remote 도움말

$ git remote remove <name>    # 이 때 네임은 키값(오리진 등)

$ git push origin master  #오리진이 등록된 곳이 마스터가 됨

$ git log --oneline  # commit 상태를 요약적으로 보여줌(그냥 log가 더 상세)
```

- 커밋에 들어갔는지 항상 확인해야함!



![image-20211203094455718](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20211203094455718.png)

- 내 깃허브(원격저장소)에는 밑(빨간 글씨)에만 업로드 되어 있단 뜻!

  

모든걸 원격 저장소에 올리기 위해선??

```
$ git push origin master
```



![image-20211203094831681](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20211203094831681.png)

- 내 컴퓨터와 원격저장소가 동일하다라는 뜻!



- 비어있는 폴더는 굳이 git이 관리를 하지 않음

- 홈폴더에는 절대 마스터키 있음 안됨~~~

  

| 위치 표시 | 설명      |
| --------- | --------- |
| .         | 내 위치   |
| ..        | 상위 위치 |





## 프로젝트 초기화 진행

### README.md 와 .gitignore 파일 생성

![image-20211203103135840](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20211203103135840.png)



### git secret 파일 설정

![image-20211203104246990](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20211203104246990.png)

- .gitignore에 파일명 작성 시 무시됨.
- .gitignore파일은 필수로 만들어야 함.

ctrl+a :전체선택

![image-20211203104834935](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20211203104834935.png)

- .gitignore 파일에 추가하면 필요 없는 파일들 무시됨



### 원격 저장소에 추가

![image-20211203105314167](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20211203105314167.png)

- 프로젝트 초기화

  

1. remote 저장소 생성 @github.com

2. 생성한 원격 저장소 등록

```
$ git remote add origin <URL>
```

3. 등록된 저장소 다시 확인

```
$ git remote -v
```

4. 지금까지의 commit push

```
$ git push origin master
```



## 만약 다른 컴퓨터에서 진행하려면?

![image-20211203131439525](git-notetaking.assets/image-20211203131439525.png)
