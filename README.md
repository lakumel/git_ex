오랜만에 다시 해보는 레파지토리 연습으로 그냥 간단하게 깃 연습을 하는 것 보다는 명령어를 복사해서 붙여넣는 방법이 있긴 하지만은 그것은 실력이 생기고 나서 해보고 일단은 깃 연습은 아래와 같이 되어 있는 걸로 알고 있다.


# GIT 명령어

기본 브랜치 (Default Branch) : main 
      - GitHub (MS에서 인수) :	master(인수하기 전의 이름) ------>main(인수 후의 이름)
      - Git       :설치시에 기본 브랜치 이름 :main

Commit	<==특정 시점의 내용을 백업, 그 시점으로 되돌릴 수 있다.
      - 하나의 기능이 완성되었을때,
      - "기능명_날짜 _누가"    <== 커밋의 설명을 넣어줘야 그 상태로 돌아갈 수 있다.

스테이지(stage) 영역 : Commit 할 데이터를 위치 시키는 영역
레파지토리 (Repository) 영역 :   Commit 된 데이터가 위치하는 영역 


## 1. 깃을 초기화 하는 명령어 : 해당 폴더에서 git으로 컨트롤 하겠다.
	- 버전을 관리할 폴더에서 선언
	- .git     :Local Repository	<==commit 한 정보가 저장 
$ git init 

## 2. 글로벌 설정 : git을 설치 후 한번만 셋팅 , 사용자명, 사용자 메일주소
        - git 설치후, 1번만 셋팅

$git config --global user.name "자신의(영문)이름"<br>
$git config --global user.email "자신의 메일 주소"<br>


## 3.스테이징(Staging)영역에 모든 파일을 추가 (Working Directory ===>Stage Area)
$git add .  <=현재 폴더의 모든 파일을 스테이징 영역에 등록

        --스테이징 영역에 등록된 파일을 보는 명령어
           $git status
        -- 초록색 : 스테이지 영역에 등록된 파일
        -- 빨간색 : 스테이지 영역에 등록되지 않는 파일

## 4.로컬 레파지토리에 백업파일을 생성 : commit   <==stage 영역에 등록된 파일만 커밋

$git commit -m "로그인 기능완성_2023_4_28_Woosung Yang"

     --커밋된 정보를 보는 명령어 
       $git log


## 5.로컬 레파지토리의 정보를 원격 레파지토리에 전송하기 위해서 origin 변수에 GitHub에 원격 레파지토리 주소를 등록
	: git remote add origin "원격레파지토리주소"
$git remote add origin "https://github.com/lakumel/project1.git"


## 6.로컬 레파지토리의 내용을 원격 레파지토리로 전송 : git push 

$ git push origin main         <== 로컬의 main 브랜치의 커밋된 내용을 원격 레파지토리로 전송


# GitHub에 계정 만들기
 -github.com

## 레파지토리(repository) 생성, (로그인)
  github.com/new


===================================

## 경로의 파일을 github에 올리기:/c/git/Sample_web

1. 깃 초기화 하기<br>
 $ git init<br>

2.로컬의 작업디렉토리의 모든 파일을 stage 영역에 올림.<br>
	$git add . <br>
 
3.스테이지 영역에 등록된 파일을 commit (Local repository 에 등록)<br>
	$git commit -m "Front-End 첫 번째 commit _ 2023_04_28"<br>

4.github에서 원격 레파지토리 생성(github.com/new) : 레파지토리 이름, public<br>
	https://github.com/lakumel/web.git<br>
 
5.origin 변수에: 원격 레파지 토리 등록<br>
	$git remote add origin "gitHub의 원격 레파지토리 등록"<br>
 
6.로컬 레파지토리의 commit 정보를 원격(깃 허브) 레파지토리(origin)에 전송<br>
	$ git push origin main<br>

7.github pages 를 사용해서 웹 서버를 구동해서 글로벌하게 서비스 :Front-End : HTML, CSS, Javascript <br>
  해당프로젝트 ===> settings ===> pages ==>main(브랜치선택)==>save(클릭)<br>
  2분뒤 : https://lakumel.github.io/web/<br>


<실습>web2, web3, web4, web5	<==GitHub 프로젝트에 전송후 github pages를 사용해서 글러벌하게 출력

# README.md , .gitignore 파일

   --README.md 	: 깃허브에서 프로잭트의 설명을 넣는 파일<br>
   --gitignore	:로컬 레파지토리의 불필요한 파일을 서버로 전송 하지 않도록 설정<br>
	--개발시 컴파일된 파일, 설정 파일<br>
	--gitignore.io	<br>
		운영체제  개발환경(IDE)  프로그래밍 언어	
		 Windows	    EClips		java		<== Local Repository 에는 존재하지만 
							GitHub에는 전송할 필요가 없는 파일을 자동으로 만들어준다.


# git clone  :원격의 github의 공개된 레파지토리의 모든 내용을 자신의 시스템으로 복사 
#git clone "원격레파지토리주소"



#학원 : Host OS(Windows 10) 
1. git 설치 ==>github 로드했음.

2. 집에서 push한 파일을 pull 해서 가져와야 한다.    pull  : 원격 레파지토리의 변경된 내용을 Local 시스템으로 가지고 온다.

3. 주의 : pull을 반드시 먼저 실행한 후 로컬의 내용을 커밋하고 push	    <==안 그러면 꼬여버린다.
	$git pull origin main

push:로컬의 내용을 서버로 올릴때

서버의 내용을 로컬로 가져올떄 pull
(git pull origin main)



#집    :VM(windows 11)
 --크롬 설치
 --git 설치 (git-scm.com)


  1.원격 레파지토리의 전체 프로젝트 파일을 로컬 컴퓨터로 클론 
    $git clone "https://github.com/lakumel/web.git"

  2.집의 시스템에서 새로운 파일을 생성후 github로 전송시 commit ==> push 

  3. 주의 : pull을 반드시 먼저 실행한 후 로컬의 내용을 커밋하고 push	    <==안 그러면 꼬여버린다.
	$ git pull origin main 


### origin 변수의 값을 확인<br>
$git remote	<==변수출력<br>
$git remote add origin "원격레파지토리주소"	<==등록<br>
$git remote show origin	<==origin 변수의 값을 출력<br>
$git remote remove origin	<==origin 변수에 등록된 값을 삭제<br>

============================================

### GitHub에서 초기화 된 경우 : .git      <== Repository(커밋된 정보를 저장)<br>
  it_test    <==GitHub에서 초기화된 경우 : .git        <==깃허브에서 커밋이 적용되어 있다.<br>
  -README.md<br>
  -.ignore<br>
  -깃라이센스<br>


  인경우 Local Repository 에서 Clone 으로 동기화 해야함.<br>
  git clone "원격레파지토리주소"	<== origin 변수에 레파지토리 주소가 자동으로 저장<br>

### GitHub에서 초기화가 안된경우  : 1.레파지토리 이름, 2.public / private 두가지만 설정해서 만든 경우<br>
  it_test2<br>

  로컬에서 초기화를 시키고 커밋하고,push 를 사용해서 업로드<br>
  1.git init    <==.git<br>
  2.git add .    <==현재 폴더의 모든 파일을 stage 영역에 등록<br>
  3.git commit -m "첫 번째 커밋 입니다."	<==stage에 등록된 파일을 컷밋(백업)<br>
  4.git remote add origin"원격레파지토리주소" 		<==origin 변수에 원격 레파지토리 주소를 저장함<br>
  5.git push origin main		<==main 브렌치의 내용을 원격 github에 전송 <br>



## Local 시스템에서 수정(변경) 사항이 생긴 경우
 -- 커밋(Local) ==>Push  (remote) 

## Remote 에서 수정(변경) 사항이 발생된 경우 
 -- 커밋 (Remote)   ==>pull (local)
