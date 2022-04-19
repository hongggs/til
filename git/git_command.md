# git

## 내가 보려고하는 git 명령어 정리

1. git init: 무조건 처음에 써야하는 명령어(이 폴더 안에서 버전 관리를 시작)
2. git status: 버전 관리가 되고있는 지금 폴더의 상태를 알려줘(수정한 파일 등의 상태)
3. git add "fileName": working directory에서 staging area로 로 옮김
      * staging area: 버전이 될 후보 모아둔 곳
4. git rm –cached "fileName": staging area에서 다시 working directory로 내림
5. git add . : 현재 working directory에 있는 모든 변경사항을 다 staging area로 옮김
6. git commit -m “commit message”: staging area에 올라간 파일들을 버전으로 만듦(local 저장소로 옮김)
      
      - commit message에 유의미한 변화에 대한 간단한 설명을 작성
      - git commit: 길고 자세한 commit message작성 가능
      - git commit –amend: commit 수정
7. git log: 지금까지 만들어진 commit 내용 확인
8. git commit -am “commit message”: commit과 add 동시에

      - 한 번이라도 commit을 한 경우에만 사용가능함
9. <github에 push하기>

      1) 추가할 버전이 있는 폴더에서 사용
 	2) git remote add origin <url>: 원격저장소와 로컬저장소를 연결

                  - 원격저장소를 더하는데 더하는 원격 저장소 이름은 origin이고 url은 이거야!
      	            * origin은 단축이름
      3) git branch -M main 
 	4) git push -u origin main: 내 repository에 있는 main브랜치를 origin의 main브랜치로 push

            - -u: 디폴트 설정, 이후 git push로 등록하면 무조건 origin main과 상호작용
10. git reset <옵션> "commit": Working directory, Staging area, Repository에서 만든 내용 취소 

            어디까지 되돌릴까?:                        옵션
            수정한 것 까지 전체(전체삭제):            --hard HEAD^
            add한 것 까지(staging area까지 삭제):  (--mixed) HEAD^
            commit한 것만:                      --soft HEAD^
            
            * HEAD: 가장 최근 버전
            * ^ : 하나 되돌리기
11. git branch: branch 목록 보기
12. git branch "branchName": branch 만들기
13. git checkout "branchName": 속한 branch 바꾸기
14. git checkout -b "branchName": branch를 새로 만듦과 동시에 이동
15. git merge "branchName": 현재 속한 branch에 합치려는 branch(branchName)에서 작업한 내용을 합침
16. git diff <비교대상commit> <기준commit>: 패치간 차이점 알 수 있음
      
      - commit log에서 확인가능한 hashcode사용
      - HEAD HEAD^ 사용가능(가장최근commit 가장최근commit의 하나 이전 commit)
      - 이외에도 branch간, 원격저장소와 현재 branch 등 다양하게 비교 가능
17. git revert <되돌리고 싶은 commit>: git reset과 비슷하지만 되돌린 버전 이후에 만들어진 버전들이 유지되고 revert된 새로운  commit이 추가되는 형태
18. git remote: 내 로컬 repository와 상호작용 하고있는 원격 저장소들의 목록을 조회
      
      - git remote -v: 단축이름과 url 같이 보기
19. git remote rm <원격저장소이름> : 연결된 원격저장소 삭제
20. git pull (origin main): origin을 내 repository의 main브랜치로 갖고와라(merge)
21. git fetch (origin main): origin을 내 repository의 main브랜치를 가지고오는데 동기화시키지는 마라(merge X) 
      
      - git checkout origin/main(= git checkout FETCH_HEAD)으로 접근해 확인 가능 
22. git clone "url": "url"에 있는 원격저장소 내용을 현재 디렉토리에 복사해오기
      
      - origin 자동 생성
23. rebase <base가 될 branch> : base를 바꿔 합침 
      
      - merge와 달리 쓸데없는 commit이 생기지 않아서 history 관리에 용이


