# Git Commands

## init
- 현재 디렉토리를 git 저장소로 만듭니다.
- 지정한 디렉토리를 git 저장소로 만듭니다.
~~~
git init

git init gitfth
~~~

## add
- git이 파일을 추적하도록 명령합니다.
~~~
git add file.name
~~~

## status
- 프로젝트 폴더의 상태를 확인합니다.

## config
- 버전을 만든 사람에 대한 정보를 설정
- ~/.gitconfig 파일에 저장되고 1번만 해주면 된다.
~~~
git config --global user.name "닉네임"
git config --global user.email "이메일"
~~~

## commit 
- 커밋.
~~~
git commit 

git commit -a //변경사항 전부 commit

git commit -am //변경사항 전부, 커밋메세지 바로 입력가능

git commit - amend // 커밋 메시지 수정
~~~

## log
- 변경사항 확인하기
~~~
git log -p //버전간의 차이점을 출력

git log --reverse // 로그를 거꾸로 출력하기
~~~

## diff
- 버전간의 차이점 비교
~~~
git diff '버전id'..'버전id2'

git diff // add하기 전과 후 파일내용 비교
~~~

## reset
- 이전 버전으로 돌아가기
~~~
git reset --hard '버전id' // hard는 파일도 변경
~~~

## revert 
- 버전 id 커밋을 취소한 내용을 새로운 버전으로 만드는 명령
~~~
git revert '버전id'
~~~
참고 http://www.popit.kr/  

## --help
- 설명보기
~~~
git --help
~~~

## checkout
- 해당 커밋으로 체크아웃하기(되돌리기)
~~~
git checkout '버전id'

~~~

## clone 
- git 의 소스코드를 지역 저장소로 가져오기
~~~
git clone https://github.com/git/git.git
~~~

## remote 
- local 저장소에 commit 을 한 상태에서 원격 저장소와 연결
~~~
git remote add origin https://github.com/Min-92/CommandsForMe.git
~~~

## push 
- 원격저장소에 파일 업로드
~~~
git push -u origin master  // 원격저장소 origin master 에 동기화

git push
~~~

## pull
- 원격저장소에서 로컬로 동기화
~~~
git pull
~~~