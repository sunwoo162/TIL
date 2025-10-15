# Git명령어
## 1.Git으로 작업 할 때 어떤 파일이 변경 되었는지 확인할 수 있는 명령어
```
git status
```
## 2. 파일 만들기
```
git add "파일이름"  // 명령어
git add .			// 폴더 내에 있는 파일 전체 add
```
## 3. commit하기
```
git commit -m "Commit message"  // 명령어
```
## 3. 커밋 내역 확인
```
git log
```
## 4. 로컬환경에 이미 git repository가 있을 경우
```
or push an existing repository from the command line 부분에 있는 순서대로 진행
```
```
git remote add origin [repository 주소]
git remote -v
git push -u orign master
```
## 5. GitHub 유저네임과 비밀번호 입력
