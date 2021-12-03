# Branch

## Branch 사용법

- master : branch 이름,마지막 커밋

```
$ git branch  # branch는 포인터(화살표)의 의미를 가짐
* master 
```

- 새로운 commit이 진행되면 , master는 최신 commit으로 자동적으로 이동됨. 이름표의 위치가 계속 바뀜
- branch를 새로 만든다? =새로운 이름표를 만든다

```
$ git branch b1  # branch가 하나 추가되었다는 뜻
# 즉, master와 b1 총 두개의 branch가 생김
# (HEAD -> master, b1) 이런 식의 결과값이 나오게 됨
```

```
$ git branch b2		# b2 생성
$ git branch -d b2  # b2 삭제
```

```
$ git switch b1 #b1으로 branch를 바꿈
```



- b1 branch 상태에서 b1.txt를 만들고 커밋까지 진행하면 -> b1 상태에서만 존재하게 됨 (master에서는 저 파일 확인 불가)
- b1와 master branch는 평행 세계라고 생각해도 됨





## Branch는 왜 사용할까?

- **master** : 완성된 프로그램, 발표 가능한 슬라이드, publish된 논문 등 working product 
  - 즉 누구라도 쓸 수 있는 상태, 세상에 공개 가능한 product
  - 새로운 개발 시 많은 과정들이 생기는데, commit을 해야하긴 하지만? 확정을 시킬 순 없음(확정된 상태가 아니니까!)
- 먼 미래에 `master로 병합(merge)`될 새로운 branch를 계속 만들어가면서 최종본 만드는 것
- 개발 시 문제가 생겨서 만들었던 branch 과정을 없던 일로 한 번에 없애버리기 위함이기도 함 -> 원래 master로 넘어가면 되거든
- 어째뜬 최종 목표는 `master와 병합(merge)`하는 것임



## master와의 병합(merge)

```
$ git merge b1  #branch가 master인 상태일 때 실시
```

- Fast-forward : b1의 커밋으로 master가 화살표를 움직임(굳이 추가 커밋을 할 필요 없이 시점만 이동함)

  ```
  9c3e788 (HEAD -> master, b1) b1 내용 추가
  ```



###  병합 시 충돌

- 같은 branch가 같은 파일을 수정함!

  ```
  CONFLICT (content): Merge conflict in README.md
  Automatic merge failed; fix conflicts and then commit the result.
  ```

  - 이 경우는 수동으로 수정해주면 됨(직접 삭제 또는 선택)

    ```
    $ git log --oneline --graph
    *   3872369 (HEAD -> master) 충돌 해결
    |\  
    | * b0a442f (b2) 수정 by b2
    * | 54c935b 수정 by master
    |/  
    *   f2320ad Merge branch 'b1'
    |\  
    | * 451e47a (b1) 최종 완성
    | * 83c22e1 검수 완료
    | * 6049a5a b1 추가 작업
    * | f5c9f0c 긴급 수정
    |/
    * 9c3e788 b1 내용 추가
    * 1772d24 add b1.txt
    * d6f4c4e MESSAGE
    * 7e318b7 신입사원
    * 74234dd adding
    * 693436c add heading
    ```



### 병합 후 남아 있는 branch 처리

- 수명이 다 한 branch는 삭제가 일반적

  ```
  $ git branch -d b1 ## branch 삭제
  ```

  ```
  $ git log --oneline --graph
  *   3872369 (HEAD -> master) 충돌 해결
  |\  
  | * b0a442f 수정 by b2
  * | 54c935b 수정 by master
  |/  
  *   f2320ad Merge branch 'b1'
  |\  
  | * 451e47a 최종 완성
  | * 83c22e1 검수 완료
  | * 6049a5a b1 추가 작업
  * | f5c9f0c 긴급 수정
  |/
  * 9c3e788 b1 내용 추가
  * 1772d24 add b1.txt
  * d6f4c4e MESSAGE
  * 7e318b7 신입사원
  * 74234dd adding
  * 693436c add heading
  * b5e6bb3 first commit
  ```



# 협업 과정

1. Clone

```
$ git clone <URL> [파일명]
```

```
$ git remote -v
origin  https://github.com/heewon330/branch-collabo.git (fetch)
origin  https://github.com/heewon330/branch-collabo.git (push)
## 원본이기 때문에 origin이라고 설정되어 있음

$ git log
commit 3de584ffdf86962919ebc830119d0d6fbbe28af4 (HEAD -> master, origin/master, origin/HEAD)
```



2. 각각의 branch를 생성 

- 원본(origin)이 있기 때문에 master는 건들이면 안됨

```
$ git switch -c feature/login ## A's branch
$ git switcch -c feature/signup ## B's branch
```

3. 각자 수정하고 각각의 branch에 push하기

```
$ git push origin feature/login ## feature/login이라는 브랜치에 푸쉬
```

```
$ git log --oneline --graph
*   2a086b0 (HEAD -> master, origin/master, origin/HEAD) Merge pull request #2 from heewon330/feature/signup
|\  
| * 28f0b6a (origin/feature/signup, feature/signup) signup middle
| * e8c8c50 signup 중간완성
* |   8470d4b Merge pull request #1 from heewon330/feature/login
|\ \  
| |/
|/|
```

