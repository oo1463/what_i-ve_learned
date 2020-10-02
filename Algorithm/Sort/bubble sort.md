#버블정렬 (bubble sort)
- 서로 인접한 두 원소의 대소를 비교하고, 조건에 맞지 않다면 자리를 교환하며 정렬하는 알고리즘


1. 1회전에 첫 번째 원소와 두 번째 원소를, 두 번째 원소와 세 번째 원소를, 세 번째 원소와 네 번째 원소를, … 이런 식으로 (마지막-1)번째 원소와 마지막 원소를 비교하여 조건에 맞지 않는다면 서로 교환한다.

2. 1회전을 수행하고 나면 가장 큰 원소가 맨 뒤로 이동하므로 2회전에서는 맨 끝에 있는 원소는 정렬에서 제외되고, 2회전을 수행하고 나면 끝에서 두 번째 원소까지는 정렬에서 제외된다. 이렇게 정렬을 1회전 수행할 때마다 정렬에서 제외되는 데이터가 하나씩 늘어난다.


## 시간 복잡도
- 최선 :  O(n^2)
- 평균 :  O(n^2)
- 최악 :  O(n^2)

## 공간 복잡도
O(n)

## 장점
- 구현이 매우 간단
- 다른 메모리 공간 필요 x
- stable 정렬

## 단점
- 시간복잡도가 높아 비효율적
- 교환연산이 많이 일어나게됨 