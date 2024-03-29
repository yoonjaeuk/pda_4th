# 테스트 환경
* Anaconda를 설치하여 파이썬 코드를 서버에서 실행시켰습니다.
* os는 ubuntu를 사용했습니다.
* 인스턴스 유형은 t2.micro와 t2.medium를 사용
* AMI는 amd64입니다.
## 성능 측정
* 크롤링 속도
* 코테 콛의 실행 시간
## 범위와 역할
* 김민중 팀원
  * t2.medium 인스턴스를 사용
  * 크롤링에 해당하는 파이썬 코드 작성
* 이재인 팀원
  * t2.micro 인스턴스를 사용
  * for문을 사용한 파이썬 코드 문제 작성
## 결과 분석
|유형|t2.micro(초)|t2.medium(초)|이슈|해결|
|-------|-------|-----|----|---|    
|크롤링|19.5328|19.7202|t2.medium이 20배 느리게 나오는 문제|리전 동기화(t2.micro(한국),t2.medium(미국북부->한국))|  
|for문|119.37|111.98|.|.|
