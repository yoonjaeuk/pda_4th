# 신한 프로디지털아카데미 4기 테스트 공간

이 공간은 신한 프로디지털아카데미 4기 수강생들을 위한 github 테스트 공간입니다. 여기에서는 다양한 테스트를 진행하고 결과를 공유할 수 있습니다.

## 💻테스트 환경
저희는 ApacheBench를 사용해서 부하 발생 테스트를 했습니다.  
우분투에서 아파치를 설치한 후 'ab -n 400 -c 1 http://인스턴스퍼블릭 IP주소' 명령어를 실행해서 400명의 사람이 동시 접속 없이 페이지에 접속한다고 가정한 상황을 테스트를 합니다. 

## ⚙아키텍처
아키텍처는 64비트(x86)과 64비트(Arm)을 사용했습니다.
t4g, m6g 유형은 arm 아키텍처로 t3, m6i 유형은 x86 아키텍처로 테스트 했습니다. 

## 🔎AWS EC2 인스턴스 유형 별 성능 테스트 

| 인스턴스-아키텍처 | Time taken for tests | Suc/Total Request | Request per second | Time per Request |  
|---|---|---|---|---|
| T4g.small-Arm | 0.992sec | 400/400 | 403.40[#/sec] | 2.479ms | 
| T3.small-x86 | 0.585sec | 400/400 | 684.08[#/sec] | 1.462ms |
| T4g.large-Arm |  |  |  |  |
| T3.large-x86 | 0.575sec | 400/400 | 695.47[#/sec] | 1.438ms |
| M6g.large-Arm |  |  |  |  |
| M6i.large-x86 | 0.558sec | 400/400 | 717.26[#/sec] | 1.394ms |

## 📈결과 분석
ARM 기반 아키텍처를 사용하는 t4g와 인텔의 x86 아키텍처를 사용하는 t3를 비교해보겠습니다. 
표를 해석해보면 x86 아키텍처를 사용하는 t3 유형의 인스턴스가 크기에 상관없이 t4g보다 처리가 빠르다는 것을 알 수 있습니다.
구글링을 했을 땐 t4g 인스턴스가 t3 모델보다 40% 나은 성능에 20% 더 저렴하다고 하는데 결과값은 반대로 나왔습니다.  

동일한 유형에서 인스턴스 크기에 따라 비교를 해보면 인스턴스의 크기가 클수록 처리속도가 빨라지는 것을 알 수 있습니다. 
