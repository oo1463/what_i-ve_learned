#중앙처리장치(CPU) 작동 원리

## 연산장치 (ALU)
- 산술연산과 논리연산 수행 (따라서 산술논리연산장치라고도 불림)

- 연산에 필요한 데이터를 레지스터에서 가져오고, 연산 결과를 다시 레지스터로 보냄


## 제어장치

- 명령어를 순서대로 실행할 수 있도록 제어하는 장치

- 주 기억장치에서 프로그램 명령어를 꺼내 해독, 명령어 실행에 필요한 제어 신호를 기억장치, 연산장치, 입출력 장치로 보냄

## 레지스터

- 고속 기억 장치

- 명령어 주소, 코드, 데이터, 연산 결과 등을 임시로 저장

- 범용 레지스터, 특수목적 레지스터로 구분

PC (program counter) - 다음에 수행할 명령어 주소를 저장


## CPU의 동작 과정

1. 주기억장치는 입력장치에서 입력받은 데이터 또는 보조기억장치에 저장된 프로그램 읽어옴
2. CPU는 프로그램을 실행하기 위해 주기억장치에 저장된 프로그램 명령어와 데이터를 읽어와 처리하고 결과를 다시 주기억장치에 저장 (fetch - decode - execution)
3. 주기억장치는 처리 결과를 보조기억장치에 저장하거나 출력장치로 보냄
4. 제어장치는 1~3 과정에서 명령어가 순서대로 실행되도록 각 장치를 제어

명령 사이클 : fetch - decode - execute - store - writeback

- i-time(instruction time): Fetch & Decode 수행시간
- e-time(execution time): Execute & Decode 수행시간


## pipelining
    cpu의 작동을 parallel 하게 만들자
    fetch - decode - execute - store   - writeback
            fetch  - decode  - execute - store   - writeback
                     fetch   - decode  - execute - store   - writeback
                                fetch  - decode  - execute - store   - writeback
                                         fetch   - decode  - execute - store     - writeback

#### pipelining hazard

- Structure hazard : memory access가 동시에 일어나는 경우 (메모리의 접근은 한 time에 한번만 일어날 수 있음)
```
해결방법 : stall ( 쉬어가자)
, 추가적인 ALU를 만든다
```    
   
- Data hazard : 데이터의 read,write 순서가 엇갈려 생기는 hazard
```
해결방법 : forwarding (bypassing)
stall
```

- Control hazard : 분기문에서 발생하는 hazard (분기문이 나왔을 경우 다음 한 사이클에서 어떤 명령어를 실행시켜야 할까?)

```
predict not taken 분기제어문이 항상 false라고 생각하고 다음 명령어를 fetch
predict taken 분기 제어문이 항상 true라고 생각하고 분기 될 명령어를 fetch
```
 