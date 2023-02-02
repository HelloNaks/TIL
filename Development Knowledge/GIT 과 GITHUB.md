# GIT 과 GITHUB
> "GIT 과 GITHUB는 커피와 카페 같은 관계이다" -노마드 코더-

## GIT 이란?
- 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 분산 버전 관리 시스템이다.
- 소프트웨어 개발에서 소스 코드 관리에 주로 사용되지만 어떠한 집합의 파일의 변경사항을 지속적으로 추적하기 위해 사용될 수 있다.

## GIT의 특징
[Git 홈페이지](https://git-scm.com/about/distributed) 에서 Git의 특징을 다음과 같이 6가지로 정의한다.
1. Branching and Merging
	-	사용자는 메인 코드에서 가지를 생성하여 독립성을 유지한 채로 개발을 진행할 수 있다. 이는 다양한 코드를 개발 또는 테스트 해 볼 수 있는 환경을 제공해준다.
2. Small and Fast
	- Git은 대부분 로컬에서 진행되는 만큼 매번 네트워크에 접속할 필요 없어 네트워크 속도와 관계없이 빠르게 진행 가능하다.
3. Distributed
	- 사용자들은 복사된 프로젝트에서 동시에 작업을 진행할 수 있고, 서버가 다운되어도 사용자 각각은 코드 전체를 가지고 있기 때문에 문제가 발생하지 않는다.
4. Data Assurance
	- Git의 모든 파일은 체크섬 검사를 거치게 되고, 이를 통해 누가 어느 파일을 작업했는지 기록이 남아 버전 히스토리 관리가 가능하다.
5. Staging Area
	- 깃은 준비 영역을 가지고 있다. 수정한 내용을 반영하기 전 단계이다.
	1) 작업 디렉토리에서 반영할 파일을 선택하는 단계, (git add)
	2) 이후 수정한 파일을 실제로 저장소에 반영하는 단계 (git commit)
	※ 한번에 다 진행하려고 할 때 (git commit -a)
6. Free and Open Source
	- 깃은 오픈소스이기 때문에 누구나 무료로 사용 가능하다.
	-	
## 깃허브 란?
- Git의 데이터를 저장하는 서버이다. 비슷한 서비스로는 Gitlab과 Bitbucket가 있다. 

## 깃허브의 추가 기능
깃허브에서는 코드 관리 뿐만 아니라 다른 다양한 기능들을 이용할 수 있다.
1. Github Action : 소프트웨어 워크플로우를 자동화할 수 있도록 도와주는 도구. 코드 검사, 자동 배포 등의 기능을 스크립트로 만들어 사용할 수 있는 CI/CD 도구.
2. Github OAuth : 깃허브 아이디를 이용해 다른 사이트 회원가입이나 로그인 할 수 있는 API 제공.
3. Github Pages : 무료로 정적 사이트를 배포할 수 있는 도구.
4. Github Desktop : 깃허브 소스코드 관리 툴. GUI 형태로 git을 관리.
5. Github Discussions : 일종의 네이버 지식인 같은 개념. 레포지토리 내에서 다양한 토론을 진행.





> 출처
> 노마드 코더 -  [깃. 깃허브. 기초개념 잡아드림. 5분 순삭.](https://www.youtube.com/watch?v=YFNQwo7iTNc)
> gparkkii - [깃, 깃허브 간단요약](https://velog.io/@gparkkii/GitGithub)
> Kyun Heo - [Git 과 Github](https://mfamcs.netlify.app/docs/dev_knowledge/Git%EA%B3%BCGithub)
> zerocho - [Git 과 Github 소개](https://www.zerocho.com/category/Git/post/58045dbc146be6001542a465)
> 
