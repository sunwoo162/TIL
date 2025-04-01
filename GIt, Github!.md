# GIt과 GIthub
## 1. branch란 무엇인가
```
브랜치란?(가지)
하나의 줄기에서 뻗어나온 과정들을 의마하며, 저장공간에서 또 다른 가상의 저장공간을 생성하는 것
하나의 프로젝트를 여러 갈래로 나눠 관리할 수 있게 해주는 기능이다.
메인 코드와 분리하여 작업할 때 유용하게 쓰인다.
```
## 2. branch 사용하기

-1 브랜치 리스트 확인하기
```
git branch
```
-2 브랜치 만들기
```
git branch 브랜치 이름
```
-3 브랜치 삭제하기
```
git branch -d 브랜치이름
```
-4 브랜치 바꾸기
```
git checkout [-b] 브랜치이름
```
-5 두 브랜치의 커밋 상태 차이 보기
```
git log [-p] 브랜치1..브랜치2
```
-6 브랜치들의 커밋 상태 보기
```
git log --barnches --decorate --graph --oneline
* --barnches : 각 브랜치가 어떤 커밋을 가르키고 있는지 알려준다.
* --decorate : 브랜치의 참조 정보를 알려준다.
* --graph : 커밋 이력을 텍스트 기반 그래픽으로 표현한다.
* --oneline : 그래프의 상황을 간결하게 보여준다.
```
-7 각 브랜치의 현재 상태 비교
```
git diff
```
-8 브랜치 병합
```
git merge 브랜치1
1. Gast-forward
2. 3-way Merge
```
## 3. github 명령어들
-1 현재 상태 확인
```
git status
```
-2 전체 로그 확인
```
git log
```
-3 git 저장소 생성하기
```
git init
```
-4 저장소 복제 및 다운로드
```
git clone [https:~~~]
```
-5 저장소에 코드 추가
```
git add
git add*
```
-6 커밋에 파일의 변경 사항을 한번에 모두 포함
```
git add -A
```
-7 커밋 생성
```
git commit -m"message"
```
-8 변경 사항 원격 서버 업로드(push)
```
git push origin master
```
-9 원격 저장소의 변경 내용을 현재 디렉토리로 가져오기(pull)
```
git pull
```
-10 변경 내용을 merge 하기 전에 바뀐 내용 비교
```
git diff [브랜치 이름][다른 브랜치 이름]