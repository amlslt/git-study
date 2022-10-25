## 용어
- glt = 바보, 가치없는사람
- 원격 저장소 = 원격서버에서 관리하는 저장소 타인의 저장소 포함, 여러사람과 공유가능
- 병합 = 두 소스코드를 합치는것
- 커밋(commit) = 차일이나 폴더의 추가, 변경사항을 기록하는것
- 푸시(push) = 자신의 로컬저장소의 파일을 원격저장소에 업로드하는것
- 풀(pull) = 원격저장소의 변경사항을 로컬저장소에 저장하는것
- 페치(fetch) = 원격저장소의 변경사항을 내리받으나 병합은 하지 않는것
- 브랜치(branch) = 분기된 하나의 갈래
- 포크(fork) = 다른사람의 원격저장소를 가져와 자신의 원격저장소로 만드는것
- 풀 리퀘스트(pull request) = 포크한 원격저장소의 변경사항을 가지고 오는것
- 워킹 디렉토리 = 작업하고있는 공간
- 스테이징 에어리얼 = 임시공간
- 리포지토리 = 실제로 저장하고 기록하는 공간
- HEAD = 커밋을 가리키는 참조 포인터
- 

## 로컬 사용자 설정 (글로벌)
- 사용자 이름설정 = git clone --global user.neme "amlslt"
- 사용자 이메일 설정 = git clone --global user.email "khm66256625@gmail.com" 
- 폴더 만들기 = mkdir 폴더이름
- 폴더 이동 = cd 폴더이름
- 폴더 초기화 = git init
- 깃 목록 보기 = ls .git
- 환경설정 내용 보기 = cat .git/config
- 소스코드 작성 = code 이름.py
- 스테이지 상태 확인 = git status
- 저장소 복제 = git clone 깃허브 주소/ 새폴더이름
- 워킹 디렉토리의 파일을 스테이지 영역에 등록 = git add 파일이름
- add를 삭제 = git rm --cached 파일이름
- 수정된 파일이력 기록 = git commit -m 커밋메세지(커밋과 동시에 메세지작성) git commit -am 커밋메세지(add와 동시에 커밋, 커밋메세지 작성)
- 커밋 기록 확인 = git log
- 워킹디렉토리와 스테이징 에어리어간의 변경사항 비교 = git diff
- 워킬 디렉토리와 마지막 영역과의 변경사항 비교 = git diff HEAD
- 원격 저장소 별칭 출력 = git remote
- 원격 저장소에 연결 = git remote add origin(저장소 별칭) 저장소주소
- 원격 저장소 목록확인 = git remote -v
- 더 자세한 원격저장소 정보 = git remote show 원격저장소별칭
- 원격 서버 삭제 = git remote rm 원격저장소별칭
- 원격 서버에 변경사항 저장 = git push 원격저장소별칭 브랜치이름
- 원격 저장소 복제 = git clone 원격저장소주소
- 서버의 변경사항 내려받기 = git pull 
- 서버의 변경사항 내려받으나 병합은 안하기 = git fetch 원격저장소주소
- 브랜치 목록 보기 = git branch

## 브랜치 생성
1. 새 폴더만들기
2. 새 파일 작성
3. add와 commit하기
4. git branch 브랜치이름

## 
