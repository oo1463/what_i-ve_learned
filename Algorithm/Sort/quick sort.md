# 퀵 정렬 (quick sort)

- 분할 정복(divide and conquer) 알고리즘 기법을 사용

1. 배열 가운데서 하나의 원소를 고른다. 이렇게 고른 원소를 피벗(pivot) 이라고 한다.

2. 피벗 앞에는 피벗보다 값이 작은 모든 원소들이 오고, 피벗 뒤에는 피벗보다 값이 큰 모든 원소들이 오도록 피벗을 기준으로 배열을 둘로 나눈다. 이렇게 배열을 둘로 나누는 것을 분할(Divide) 이라고 한다. 분할을 마친 뒤에 피벗은 더 이상 움직이지 않는다.

3. 분할된 두 개의 작은 배열에 대해 재귀(Recursion)적으로 이 과정을 반복한다.

- 재귀 호출이 한번 진행될 때마다 최소한 하나의 원소는 최종적으로 위치가 정해지므로, 이 알고리즘은 반드시 끝난다는 것을 보장할 수 있다.

```

int data[100000]

void quickSort(int i, int j) {
	if(i>=j) return;

	int pivot = data[(i+j)/2];
	int left = i;
	int right = j;
	
	while(left <= right) {  // divide 
		while(data[left] < pivot) left++;
		while(data[right] > pivot) right--;
		if(left <= right) {
			swap(data[left], data[right]);
			left++; right--;
		}
	}

	quickSort(i, right);  // conquer
	quickSort(left, j);
}
```


## Quick Sort 개선

- 피벗 값이 최소나 최대값으로 지정되어 파티션이 나누어지지 않았을 때 시간복잡도는 O(n^2)
- 피벗의 위치를 조정해 줌으로써 개선 가능


## 시간복잡도

- 최선 : O(nlog₂n)
- 평균 : O(nlog₂n)
- 최악 : O(n^2)


## 공간복잡도
O(n)


## 장점

- 다른 O(nlog₂n) 정렬 알고리즘보다 빠르다
- 추가적인 메모리 공간이 필요하지 않다


## 단점

- unstable 정렬이다
- 정렬된 배열에서는 오히려 수행시간이 길어질 수 있다