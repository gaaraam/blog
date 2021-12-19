---
title: "[git] git을 시작할 때 알아야 할 것들"
date: 2021-12-19
tags: ["git"]

---

(더 추가예정)

## git 

* 코딩할 때 단순히 ctrl + z 를 눌러 이전 상태로 되돌리는 것이 아니라 원하는 시점마다 **깃발을 꽂고(버전을 만들고)** 이들 간에 자유롭게 돌아다닐 수 있ㅆ다. 내가 만든 버전 뿐 아니라 동료가 만든 내 버전으로 이동할 수 있고, 동료와 내 버전을 비교해서 최신본으로 코드를 업데이트할 수 있다.
* git은 cli와 gui로 이용 가능하다.
* git에 코드를 올리는 단계
* 저장소 만들기 -> 초기화(로컬 저장소 생성) -> github 주소를 로컬 저장소에 알려주기 -> 올리길 원하는 것만 선택 ->  선택한 파일들을 한 덩어리로 만들기(커밋) -> 덩어리에 이름 붙여주기 -> 덩어리를 깃허브에 올리기
* 로컬 저장소는 git이 관리하는 세 그루의 나무로 구성되어 있다.
* 첫번째 나무인 작업 디렉토리는 실제 파일들로 이루어져 있고,
* 두번째 나무인 인덱스는 준비영역의 역할을 하며
* 마지막 나무인 HEAF는 최종 확정본(commit)을 나타낸다.
  
## commit

* 커밋이란? **변경 사항 덩어리**를 말한다. 확정본이라고도 할 수 있다.
  
 ```
  git commit -m "fix bug"
 ```

* 커밋은 꾸준히 쌓인다. 줄줄이 기차처럼 연결되어 있다.
* 각각 의미있는 변동사항을 커밋으로 만들어 저장한다.

## push

* 커밋을 공동 원격 저장소에 올리고 싶다면! 푸시를 하세요
* 다른 개발자들이 내 코드를 볼 수 있습니다.

```
  git push origin master
```

* 다른 브랜치를 원하면 master가 아닌 다른 이름을 적어도 무방하다.
* github에 push한다면, 원격 서버의 주소를 git에게 알려줄 필요가 있음

```
  git remote add origin <원격 서버 주소>
```
## pull

* 다른 사람이 개발한 코드를 내 컴퓨터에 받아오고 싶다면! 풀을 하세요
* 로컬저장소를 원격 저장소에 맞춰 갱신하는 것.
  
```
  git pull
```

## branch

* 한 저장소에서 다른 개발자랑 같이 작업하고 싶다면! 브랜치를 만드세요
* 브랜치는 한줄로 쌓던 커밋을 n줄로 쌓게 해주는 것.
* 한 줄에서 작업하면 충돌이 날 수 있다. 똑같은 코드를 동시에 고친다든지 하는?
* n줄로 쌓다가 나중에 합칠 수 있다.
  
```
  git branch branch-name
```

## merge

* 브랜치에서 작업이 끝났어요. 이제 코드를 합치고 싶다! 병합을 하세요
* 브랜치와 브랜치를 합치는 것이 병합입니다.
* 다른 가지에 있는 변경 내용을 현재 내가 머물고 있는 branch에 병합하려면 
```
    git merge branch-name
```

## pull request

* 병합해도 되겠습니까? 병합 요청 편지
* 코드 변경 사항에 댓글을 달 수 있다.
* 피드백을 받고 코드를 수정해서 approve를 받으면 github에서 merge 할 수 있다!

## 여러가지 merge

* merge commit
* fast-foward
* conflict

## 가지치기

* example이라는 branch를 만들고 싶다면
  ```
  git branch example
  ```

* example이라는 branch를 만듦과 동시에 갈아타고 싶다면
  ```
  git checkout -b example
  ```

* 다시 master branch로 복귀하고 싶다면
  ```
  git checkout master
  ```

* branch를 삭제하고 싶다면
  ```
  git branch -d example
  ```

### 출처
[진유림님의 토끼와 거북이 튜토리얼](https://milooy.wordpress.com/2017/06/21/working-together-with-github-tutorial/)
[깃 간편안내서 - 어렵지 않아요!](https://rogerdudler.github.io/git-guide/index.ko.html)

