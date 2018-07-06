>작성중 

# 실무에 사용할 코드리뷰 방법 알아보기

## 1. github을 기반으로 한 코드 리뷰 방법
>코드스쿼드에서 진행한 강의
>https://www.youtube.com/watch?v=a5c9ku-_fok

~~~
프로젝트 원본 저장소 = A 저장소
ryan의 저장소 = B 저장소
A 저장소에 생성될 브랜치 = ryan branch
B 저장소에 생성될 작업용 브랜치 = ryantest1 branch 
~~~

1. A 저장소에 브랜치 "ryan" 생성
2. A 저장소의 ryan 브랜치를 B 저장소로 fork 해오기
3. B 저장소에서 local로 ryan 브랜치만 clone -> `git clone -b ryan --single-branch 브랜치url`
4. 모든 브랜치 확인 -> `git branch -a`
4. local에서는 ryan 브랜치를 master로 생각하고 작업용 branch 추가하기 -> `git checkout -b ryantest1`
5. 변경된 내용 확인 -> `git status`
6. 변경된 내용 commit 준비 -> `git add .`
7. commit 하기 -> `git commit -m "커밋 내용"`
8. origin에 ryantest1 push -> `git push origin ryantest1`
9. B 저장소에서 A 저장소로 pull request (github 에서)
10. A 저장소에서는 코드리뷰 후 merge
11. A 저장소의 최신화된 ryan 브랜치와 local의 구식 ryan 브랜치의 버전을 맞춰주어야 함
  - ryan 브랜치로 이동 -> `git checkout ryan`
  - local에서 A 저장소를 원격저장소로 추가 -> `git remote add upstream(이름명명가능) A저장소url`
  - upstream의 ryan 브랜치만 내 local로 가져오기 `git fet