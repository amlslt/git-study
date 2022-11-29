# 오픈소스 소프트웨어 수업 정리
## add
> 깃의 add 명령어는 워킹 디렉토리의 파일을 스테이지 영역에 등록한다는 의미입니다.
> <pre>git add . [전체 파일과 폴더를 모두 등록]
> git add <파일이름> [지정된 파일이나 폴더를 등록] </pre>

## commit
>  커밋은 변화된 내용을 영구적으로 깃 저장소에 기록하는 기능입니다.
> 커밋을 하려면 반드시 tracked 상태로 변경해야하고,<br> 각 커밋을 구별할 수 있는 메세지를 같이 넣어야 합니다.
> <pre>git commit -m "<커밋 메세지>" [커밋과 동시에 커밋 메세지 작성]
> git commit -am "<커밋 메세지>" [커밋과 add를 동시에 실행] </pre>

## log
> 커밋한 후 커밋 기록(목록)을 확인할 수 있는 명령어입니다.
> 커밋 이력은 시간순으로, 내림차순으로 나열합니다.
> <pre>git log [커밋이력 전체보기]
> git log --oneline [커밋이력 한줄보기]
> git log --oneline --graph --all [커밋이력과 브랜치의 흐름을 간단한 그림으로 보기]</pre>

## show
> 특정 커밋의 상세정보를 확인하는 명령어입니다.
> <pre> git show <커밋아이디></pre>

## clone
> 원격 저장소를 로컬 저장소에 복제하는 기능
> <pre>git clone <원격 저장소 주소></pre>

## push
> 로컬 저장소의 변경 내용을 원격 저장소에 전송하는 기능
> <pre>git push <원격저장소 별칭> <브랜치이름></pre>

## pull 
> 원격 저장소의 변경 내용을 서버에서 내려받는 기능.<br>
> 원격 저장소가 clone되어있고, 원격저장소에서 변경사항이 있어야합니다.
> <pre>git pull</pre>

## fetch/merge
### fetch
> 원격저장소에서 코드를 수동으로 내려받는 기능입니다<br>
> 내려받은 후 현재 브랜치와 자동병합을 하지 않습니다.
> <pre>git fetch <원격저장소 주소></pre>

### merge
> fetch는 데이터를 내려받기만 할 뿐 자동 병합은 하지않습니다.<br>
> 내려받은 커밋을 로컬 저장소에 병합하는 기능이 merge입니다.
> <pre>git merge <원격저장소별칭/브랜치이름></pre>

## branch
> 브랜치는 저장 공간 하나에서 가상의 또다른 저장공간을 만드는 것입니다.<br>
> 브랜치는 기존 폴더를 복제하는것과는 다르게 가상 폴더를 사용하여 개발 작업을 구분합니다.
### 브랜치의 특징
1. 가상 폴더는 빠르게 공간이동이 가능합니다.
2. 가상 폴더를 이용하면 원본 폴더와 독립적인 개발 작업을 할 수 있습니다.
3. 작업 이후에 코드를 합치는 작업을 좀 더 쉽게 병합할 수 있습니다.
4. 다양한 버전 관리 도구도 브랜치를 지원합니다.

> <pre>git branch [브랜치 목록 보기]
> git branch <브랜치이름> [브랜치 생성]
> git checkout <브랜치이름> [브랜치를 떠나 다른 브랜치로 이동]
> git switch <브랜치이름> [브랜치 이동]
> git branch -d <브랜치이름> [브랜치 삭제]
> git branch -D <브랜치이름> [브랜치 강제 삭제]</pre>

## Fast-Forward merge/3-way merge/rebase
### Fast=Forward merge
> 빨리 감기라는 의미로, 혼자 개발할 때 사용하는 병합방식이다<br>
> 병합할 대상이 현재 커밋의 뿌리일때 main브랜치에서 병합을 할 수 있다.<br>
> <pre>현재 브랜치가 main(master)일때
>git merge <브랜치이름></pre>

### 3-way merge
> 여러 개발자가 협력을 할때 사용하는 병합방식이다.<br>
> 두개의 브랜치 조상이 같을 때 새로운 커밋에 기존 커밋을 합체한다<br>
> 앞선 merge와는 다르게 충돌 가능성 존재
> <pre>git merge <브랜치명> --no-ff
>git merge <브랜치명> --edit [커밋 메세지 직접 작성]
>git reset --hard HEAD^ [병합 취소]</pre>

### rebase
> merge와 다르게 다른 브랜치 기준에서 현재 브랜치를 병합하는 방식이다
> <pre>현재와 다른 브랜치로 이동
> git rebase <브랜치명>
> git rebase --abort [rebase 취소]
> git rebase -i HEAD~3 [커밋 묶기]</pre>

## reset/revert
> 커밋을 기준으로 이전 코드로 되돌리는 방법<br>
> 기록한 커밋을 취소한다.
> <pre>git reset <옵션> <커밋ID>
git reset --hard orig_head [reset 이후 다시 원상태로 되돌리기]
</pre>
> > <pre><b>옵션<b>
soft:스테이지 영역을 포함한 상태로 복원
mixed: 기본옵션
hard: 실제 파일이 삭제된 이전 상태로 복원</pre>
### revert
> 지정 커밋이력을 취소하고 이전상태로 돌아가는 기능<br>
> 현재 이력에 되돌아간 이력까지 추가된다.
> <pre>git revert HEAD [현재 커밋을 리버트]
> git revert <커밋ID> [다른 커밋을 취소]
> git revert --mainline <숫자> <커밋ID> [리버트로 병합 취소]</pre>
