# CPU 성능 측정방법

<br/><br/>
## 성능 측정 요소 3가지
1. Response Time(응답시간)
2. Throughput(처리량)
3. Energy efficiency(에너지 효율성)

CPU 성능 =  1/CPU 실행시간
<br/><br/><br/>

## performance equation 용어

1. IC(Instruction Counts) : 명령어 수
2. CPI(Clock cycles per instruction) : 명령어당 클럭 사이클 수(명령어마다 실행시간이 다르므로 CPI는 프로그램이 실행한 모든 명령에 대해 평균값을 구한 것입니다.)
3. Clock rate(cycles per second)  (예: 1Hz = 1cycle/sec)
4. T(ck): cycle time으로 clock rate의 역수

<br/><br/>

## CPU 성능 향상

1. 클럭속도를 높인다.

2. CPI를 줄인다

3. 명령어의 수를 줄인다.

하나의 요소를 향상시키는 것은 다른 요소를 나쁘게 만들 수 있으니 균형을 잘 잡아야 합니다.

<br/><br/>

## 병렬 프로그래밍

CPU 성능속도는 계속해서 올라가지 않으며 다중코어를 사용해서 병렬프로그래밍을 하는 방식으로 CPU의 성능을 높이고 있습니다.

병렬 프로그래밍으로 인해 context switching 등에 발생하는 비용도 만만치 않다

코어의 개수를 늘리면 늘릴 수록 병렬 프로그래밍에 들어가는 비용이 exponent 스케일로 커진다

모든것이 trade off
<br/><br/>

## 암달의 법칙 
     병렬 프로그래밍으로 CPU 성능을 향상시킬 수 있는 부분의 한계
     
 ![ex_screenshot](./암달의_법칙.jfif)
 
 - 병렬화 속도를 늘리지 말고 병렬화 되지 않는 부분의 속도를 개선해라
 <br/><br/>

## MIPS

![ex_screenshot](./MIPS.jfif)

문제점 :
1. MIPS는 명령어 실행속도를 의미하지 명령어 하나가 얼마나 많은 일을 수행하는지 알 수 없습니다.

2. 같은 컴퓨터에서도 어떤 프로그램을 실행하느냐에 따라 MIPS값을 달라집니다.

3. 가장 큰 문제는 성능이 좋은 것이 나쁜 결과가 나올 수 있습니다.




