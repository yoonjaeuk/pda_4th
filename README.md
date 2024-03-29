# 신한 프로디지털아카데미 4기 테스트 공간

이 공간은 신한 프로디지털아카데미 4기 수강생들을 위한 github 테스트 공간입니다. 여기에서는 다양한 테스트를 진행하고 결과를 공유할 수 있습니다.

## 테스트 환경
저희는 ApacheBench를 사용해서 부하 발생 테스트를 했습니다.
우분투에서 아파치를 설치한 후 'ab -n 400 -c 1 http://인스턴스 IPv4'

## 아키텍처
아키텍처는 64비트(x86)과 64비트(Arm)을 사용했습니다.
t4g, m6g 유형은 arm 아키텍처로 t3, m6i 유형은 x86 아키텍처로 테스트 했습니다. 

## AWS EC2 인스턴스 유형 별 성능 테스트 

| 인스턴스-아키텍처 | Time taken for tests | Suc/Total Request | Request per second | Time per Request |  
|---|---|---|---|---|
| T4g.small-Arm | 0.992sec | 400/400 | 403.40[#/sec] | 2.479ms | 
| T3.small-x86 | 0.585sec | 400/400 | 684.08[#/sec] | 1.462ms |
| T4g.large-Arm |  |  |  |  |
| T3.large-x86 | 0.575sec | 400/400 | 695.47[#/sec] | 1.438ms |
| M6g.large-Arm |  |  |  |  |
| M6i.large-x86 | 0.558sec | 400/400 | 717.26[#/sec] | 1.394ms |

## 결과 분석
범용적인 컴퓨팅 요구사항을 위한 인스턴스인 t4g와 t3를 비교해보면,  
t4g는 ARM 기반 아키텍처를 사용하고 t3는 인텔의 x86 아키텍처를 사용한다는 차이점이 있습니다. 
표를 해석해보면 x86 아키텍처를 사용하는 t3 유형의 인스턴스가 t4g보다 처리가 빠르다는 것을 알 수 있습니다.
